# Unity 2D

## Lesson 8-9: Interact with Object, Chest UI and Rewards

---

## Мета уроку

У цьому уроці ми:

- налаштуємо систему взаємодії з об'єктами через клавішу `E`
- створимо окремий шар `Interactable`
- підготуємо скриню (Collider + Layer + Animator)
- зробимо UI скрині з трьома слотами предметів
- підключимо скрипти `IInteractable`, `PlayerInteractionSystem`, `Chest`, `ChestUI`, `ChestSlot`, `ChestItem`

---

## Що буде в результаті

Після уроку гравець зможе:

- підійти до скрині
- натиснути `E`
- запустити анімацію відкриття
- отримати меню з 3 випадковими нагородами
- натиснути на нагороду і застосувати її

---

## Частина 1. Створення шару `Interactable`

### Крок 1. Додати новий шар

![Create Interactable Layer](https://media.discordapp.net/attachments/917547349864230912/1479550770134257714/image.png?ex=69ac7288&is=69ab2108&hm=f7aba7c58f51c4814771b953127e23ada288f9650dd368c096f767c633dc0ede&=&format=webp&quality=lossless)

У будь-який вільний `User Layer` впишіть:

`Interactable`

Цей шар потрібен, щоб `Raycast` перевіряв тільки інтерактивні об'єкти.

### Крок 2. Відкрити налаштування Layer

![Add Layer Menu](https://media.discordapp.net/attachments/917547349864230912/1479550620686880799/image.png?ex=69ac7264&is=69ab20e4&hm=39f351ff1b7c2cb8f20acc56f7693b42ec1c8f05ffaeb33d7ed2eb340f03045f&=&format=webp&quality=lossless)

У `Inspector` зверху знайдіть поле `Layer`.

1. Натисніть випадаючий список `Layer`
2. Оберіть `Add Layer...`

---

## Частина 2. Підготовка об'єкта скрині

### Крок 1. Додати скриню у сцену

![Chest Object](https://media.discordapp.net/attachments/917547349864230912/1479552283950973119/image.png?ex=69ac73f1&is=69ab2271&hm=e07e640268a3ed12c762f56fd0c397af78ac269b20f5c83be72440ce6f914952&=&format=webp&quality=lossless)

Перетягніть спрайт скрині з `Project` у `Hierarchy` або прямо в `Scene`.

Перейменуйте об'єкт у:

`Chest`

### Крок 2. Додати Collider

1. Виділіть `Chest`
2. Натисніть `Add Component`
3. Додайте `Box Collider 2D`

`Is Trigger` залишайте вимкненим (за вашим поточним підходом через `Raycast2D`).

### Крок 3. Встановити правильний Layer

![Chest Layer](https://media.discordapp.net/attachments/917547349864230912/1479552680967012456/image.png?ex=69ac744f&is=69ab22cf&hm=fb22a54b2e06527ee75fe677ee1fa55dfc42fb9c5e0afed43e59262da4bd4ced&=&format=webp&quality=lossless)

У `Inspector` встановіть для `Chest`:

`Layer = Interactable`

---

## Частина 3. Анімації скрині

![Chest Animations](https://media.discordapp.net/attachments/917547349864230912/1479553007195783421/image.png?ex=69ac749d&is=69ab231d&hm=3d9b9fec5a11816bbcc0fe576a39bdf47165691754c14728314ac00cb17f9aec&=&format=webp&quality=lossless)

Створіть 3 кліпи:

- `ChestClose`
- `ChestOpen`
- `ChestIdle`

Рекомендована логіка:

- `ChestIdle` або `ChestClose` як стартовий стан
- при взаємодії перехід у `ChestOpen`
- після завершення відкриття перехід у кінцевий стан відкритої скрині

---

## Частина 4. Створення UI скрині

### Крок 1. Створити Canvas

![Create Canvas](https://media.discordapp.net/attachments/917547349864230912/1479554374555664505/image.png?ex=69ac75e3&is=69ab2463&hm=58bbe75064c05a36b704bfb5ea048c1fe11243ab386a8213982f942ec3df4e70&=&format=webp&quality=lossless)

У `Hierarchy`:

`Right Click -> UI -> Canvas`

### Крок 2. Створити корінь UI

![Create ChestUiRoot](https://media.discordapp.net/attachments/917547349864230912/1479554374907858985/image.png?ex=69ac75e3&is=69ab2463&hm=1e21f85790c0c98e687e52ad44050b958d6374d2189f0f2600c4fc3812b43048&=&format=webp&quality=lossless)

Всередині Canvas створіть порожній об'єкт:

`ChestUiRoot`

### Крок 3. Створити Panel

![Create Panel](https://media.discordapp.net/attachments/917547349864230912/1479554373305766049/image.png?ex=69ac75e3&is=69ab2463&hm=a38843d6aa5c21bcbbaa436422537c771a902a67838de4984962608d01145e62&=&format=webp&quality=lossless)

Всередині `ChestUiRoot`:

`Right Click -> UI -> Panel`

### Крок 4. Створити 3 слоти предметів

![Chest UI Slots](https://media.discordapp.net/attachments/917547349864230912/1479555257364254954/image.png?ex=69ac76b6&is=69ab2536&hm=12a1c0824c89f9f6a583296419e88f8278dd93b69ef52a5dba47a83919109439&=&format=webp&quality=lossless)

У `Panel` створіть 3 елементи `Image`:

- `Slot1 Image`
- `Slot2 Image`
- `Slot3 Image`

У кожен слот додайте:

- `Button (Legacy)`
- `Text (Legacy)`

---

## Частина 5. Скрипти уроку

![Скрипти взаємодії](https://media.discordapp.net/attachments/917547349864230912/1479556442791870545/image.png?ex=69ac77d0&is=69ab2650&hm=df66d5abb7a22392884df09e6faef80b5570d3e445e0deba430756c5b4d7463b&=&format=webp&quality=lossless)

У папці `Assets/Scripts/Interactable` мають бути:

- `IInteractable.cs`
- `PlayerInteractionSystem.cs`
- `Chest.cs`
- `ChestUI.cs`
- `ChestSlot.cs`
- `ChestItem.cs`

Код використовуємо ваш поточний (оновлений у проєкті).

---

## Частина 5.1. Код скриптів для копіювання

### IInteractable.cs

```csharp
using UnityEngine;

public interface IInteractable
{
    void Interact(GameObject player);
}
```

### PlayerInteractionSystem.cs

```csharp
using UnityEngine; // підключаємо бібліотеку Unity

public class PlayerInteractionSystem : MonoBehaviour // створюємо компонент системи взаємодії
{
    public float interactionDistance = 1.2f; // дистанція перевірки взаємодії
    public LayerMask interactionLayer; // шар об'єктів з якими можна взаємодіяти

    private IInteractable currentTarget; // змінна для збереження знайденого об'єкта

    void Update() // метод викликається кожен кадр
    {
        DetectInteractable(); // перевіряємо чи є перед гравцем інтерактивний об'єкт

        if (currentTarget != null && Input.GetKeyDown(KeyCode.E)) // якщо об'єкт знайдений і натиснута клавіша E
        {
            currentTarget.Interact(gameObject); // викликаємо взаємодію
        }
    }

    void DetectInteractable() // метод пошуку об'єктів
    {
        RaycastHit2D hit = Physics2D.Raycast( // створюємо промінь
            transform.position, // початок променя
            transform.right, // напрямок променя
            interactionDistance, // максимальна дистанція
            interactionLayer // перевіряємо тільки потрібний шар
        );

        if (hit.collider == null) // якщо об'єкт не знайдений
        {
            currentTarget = null; // очищаємо змінну
            return; // завершуємо метод
        }

        currentTarget = hit.collider.GetComponent<IInteractable>(); // отримуємо компонент взаємодії
    }

    void OnDrawGizmosSelected() // малюємо допоміжну лінію у сцені
    {
        Gizmos.color = Color.yellow; // встановлюємо колір

        Gizmos.DrawLine( // малюємо лінію перевірки
            transform.position, // початок
            transform.position + transform.right * interactionDistance // кінець
        );
    }
}
```

### Chest.cs

```csharp
using UnityEngine; // підключаємо бібліотеку Unity

public class Chest : MonoBehaviour, IInteractable // клас скрині який підтримує взаємодію
{
    public Animator animator; // посилання на Animator скрині
    public ChestUI chestUI; // посилання на UI скрині

    private bool opened; // змінна яка перевіряє чи була скриня вже відкрита

    public void Interact(GameObject player) // метод який викликається системою взаємодії
    {
        if (opened) return; // якщо скриня вже відкрита нічого не робимо

        opened = true; // позначаємо що скриня відкрита

        if (animator != null) // перевіряємо чи існує Animator
            animator.SetTrigger("Open"); // запускаємо анімацію відкриття

        Invoke(nameof(OpenUI), 0.6f); // відкриваємо UI через невелику затримку
    }

    void OpenUI() // метод відкриття меню скрині
    {
        chestUI.Show(); // показуємо UI
        chestUI.GenerateItems(); // генеруємо випадкові предмети
    }
}
```

### ChestItem.cs

```csharp
using UnityEngine; // підключаємо бібліотеку Unity

public enum ChestItemType // перелік можливих типів предметів
{
    HP, // предмет відновлення здоров'я
    Power, // предмет збільшення сили
    Coins // предмет який дає монети
}

[System.Serializable] // дозволяє Unity серіалізувати цей клас
public class ChestItem // клас предмета скрині
{
    public ChestItemType type; // тип предмета
    public int value; // значення бонусу

    public ChestItem(ChestItemType type, int value) // конструктор класу
    {
        this.type = type; // записуємо тип предмета
        this.value = value; // записуємо значення бонусу
    }
}
```

### ChestUI.cs

```csharp
using UnityEngine; // підключаємо Unity
using System.Collections.Generic; // підключаємо роботу зі списками

public class ChestUI : MonoBehaviour // створюємо клас керування UI скрині
{
    public GameObject uiRoot; // кореневий об'єкт меню скрині
    public ChestSlot[] slots; // масив слотів предметів

    private List<ChestItem> generatedItems = new List<ChestItem>(); // список згенерованих предметів

    void Start()
    {
        Hide();
    }

    public void Show() // метод показу UI
    {
        uiRoot.SetActive(true); // активуємо меню
    }

    public void Hide() // метод приховування UI
    {
        uiRoot.SetActive(false); // вимикаємо меню
    }

    public void GenerateItems() // генерація предметів у скрині
    {
        generatedItems.Clear(); // очищаємо попередні предмети

        for (int i = 0; i < 3; i++) // створюємо три предмети
        {
            ChestItemType type = (ChestItemType)Random.Range(0, 3); // випадково вибираємо тип предмета

            int value = 0; // значення бонусу

            if (type == ChestItemType.HP) // якщо предмет HP
                value = Random.Range(10, 35); // випадкове відновлення здоров'я

            if (type == ChestItemType.Power) // якщо предмет Power
                value = Random.Range(1, 8); // випадковий бонус сили

            if (type == ChestItemType.Coins) // якщо предмет Coins
                value = Random.Range(10, 80); // випадкова кількість монет

            ChestItem item = new ChestItem(type, value); // створюємо предмет

            generatedItems.Add(item); // додаємо предмет у список

            slots[i].SetItem(item, this); // передаємо предмет у відповідний слот UI
        }
    }

    public void ApplyItem(ChestItem item) // метод застосування предмета
    {
        GameObject player = GameObject.FindGameObjectWithTag("Player"); // знаходимо гравця у сцені

        PlayerHealt health = player.GetComponent<PlayerHealt>(); // отримуємо компонент здоров'я
        PlayerAttack attack = player.GetComponent<PlayerAttack>(); // отримуємо компонент здоров'я

        if (item.type == ChestItemType.HP) // якщо предмет HP
            health.Heal(item.value); // додаємо здоров'я

        if (item.type == ChestItemType.Power) // якщо предмет Power
            attack.damage += item.value; // повідомлення у консоль

        if (item.type == ChestItemType.Coins) // якщо предмет Coins
            Debug.Log("Coins +" + item.value); // повідомлення у консоль

        Hide(); // закриваємо меню після вибору предмета
    }
}
```

### ChestSlot.cs

```csharp
using UnityEngine; // підключаємо Unity
using UnityEngine.UI; // підключаємо систему UI

public class ChestSlot : MonoBehaviour // клас одного слота предмета
{
    public Text label; // текст який показує назву предмета
    public Button button; // кнопка вибору предмета

    private ChestItem item; // предмет який знаходиться у слоті
    private ChestUI chestUI; // посилання на UI скрині

    public void SetItem(ChestItem item, ChestUI chestUI) // метод налаштування слота
    {
        this.item = item; // зберігаємо предмет
        this.chestUI = chestUI; // зберігаємо посилання на UI

        label.text = item.type + " +" + item.value; // відображаємо текст предмета

        button.onClick.RemoveAllListeners(); // очищаємо старі події кнопки
        button.onClick.AddListener(OnClick); // додаємо нову подію натискання
    }

    void OnClick() // метод який викликається при натисканні кнопки
    {
        chestUI.ApplyItem(item); // передаємо предмет у систему UI
    }
}
```

---

## Частина 6. Підключення скриптів у Inspector

### Крок 1. PlayerInteractionSystem

![](https://media.discordapp.net/attachments/917547349864230912/1479558719770464296/image.png?ex=69ac79ef&is=69ab286f&hm=3db38e32749d2beb3d5409a4ad0569c59c982e28db9c7bac10362b98ad12b3b8&=&format=webp&quality=lossless)

На об'єкт гравця (або дочірній об'єкт взаємодії) додайте `PlayerInteractionSystem`.

Заповніть:

- `Interaction Distance = 1.2`
- `Interaction Layer = Interactable`

### Крок 2. ChestSlot

![](https://media.discordapp.net/attachments/917547349864230912/1479559203721842800/image.png?ex=69ac7a63&is=69ab28e3&hm=2a33fcad970819fdb7c55cd2aba99dacf088ddc1f6b9a67820f200bb84a5dcae&=&format=webp&quality=lossless)

Для кожного `Slot Image` додайте `ChestSlot`.

Заповніть поля:

- `Label` -> `Text (Legacy)`
- `Button` -> `Button (Legacy)`

### Крок 3. ChestUI

![](https://media.discordapp.net/attachments/917547349864230912/1479559460308516975/image.png?ex=69ac7aa0&is=69ab2920&hm=c2f73a5041f7e95cbd49da1e7ae5318b79329957a66ab8c2b2877414acd6efae&=&format=webp&quality=lossless)

На об'єкті (наприклад `Script`) з компонентом `ChestUI` заповніть:

- `Ui Root` -> `ChestUiRoot`
- `Slots` -> усі 3 об'єкти слотів (`Slot1`, `Slot2`, `Slot3`)

---

## Частина 7. Додатково: заповнення `ChestSlot`

![](https://media.discordapp.net/attachments/917547349864230912/1479560360511148154/image.png?ex=69ac7b76&is=69ab29f6&hm=ef602055cb5f161a494c33cc11b501faefa81caf8a66392d5d0523a3a6aa2e68&=&format=webp&quality=lossless)

Повторіть налаштування `Label` і `Button` для кожного слота.

Приклад того, що буде у тексті кнопки після генерації:

- `HP +25`
- `Coins +40`
- `Power +3`

---

## Частина 8. Підключення `Chest` до скрині

![](https://media.discordapp.net/attachments/917547349864230912/1479562071527002163/image.png?ex=69ac7d0e&is=69ab2b8e&hm=cdffc06f19ecb2941e02ecb563ab343723228a37d4c119ccd6d781e9d0c0edd1&=&format=webp&quality=lossless)

На об'єкт `Chest` додайте компонент `Chest (Script)`.

Заповніть:

- `Animator` -> `Chest (Animator)`
- `Chest UI` -> об'єкт із `ChestUI (Script)`

---

## Частина 9. Налаштування Animator

![](https://media.discordapp.net/attachments/917547349864230912/1479562799050129500/image.png?ex=69ac7dbc&is=69ab2c3c&hm=ab41538af8bc200249bb2cbe675f6fe420db34f81dbcab95785181ef225f8f00&=&format=webp&quality=lossless)

Перевірте стани в `Animator`:

- `ChestIdle`
- `ChestOpen`
- `ChestClose`

Налаштуйте переходи відповідно до вашої логіки відкриття.

![](https://media.discordapp.net/attachments/917547349864230912/1479563209068384307/image.png?ex=69ac7e1d&is=69ab2c9d&hm=428466e7a63a04a56f4609961d827450c780a8d369783837a086b594059a184c&=&format=webp&quality=lossless)

Якщо використовуєте параметр `Open`, перевірте:

- у `Parameters` є `Open`
- у `Conditions` переходу задано `Open = true`

---

## Перевірка роботи

1. Запустіть сцену
2. Підійдіть до скрині
3. Натисніть `E`
4. Перевірте відкриття анімації
5. Перевірте появу UI
6. Натисніть на один із 3 предметів
7. Переконайтесь, що ефект застосувався, а UI закрився

---

## Типові помилки

- Скриня не реагує на `E`:
перевірте `Layer = Interactable` і `Interaction Layer` у гравця

- UI не відкривається:
перевірте, чи в `Chest` заповнено поле `Chest UI`

- Кнопки не працюють:
перевірте `Label` і `Button` у кожному `ChestSlot`

- Бонуси не застосовуються:
перевірте на Player компоненти `PlayerHealt` і `PlayerAttack` (у вашій поточній реалізації)

---

## Домашня робота

- Додайте підказку `Press E to interact` біля скрині
- Зробіть різну рідкість нагород (`Common`, `Rare`, `Epic`)
- Додайте SFX відкриття скрині та SFX кліку по нагороді
