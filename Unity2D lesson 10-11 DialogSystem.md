# Unity 2D

## Lesson 10-11: Підготовка папки зі скриптами

На першому скріншоті видно, що в папці `Assets > Scripts > DialogSystem` уже створені всі основні файли для системи діалогу. Саме тут зручно тримати все, що стосується NPC, діалогів і менеджера показу тексту.

![Крок 1](https://media.discordapp.net/attachments/917547349864230912/1484617888143773747/image.png?ex=69bee1a7&is=69bd9027&hm=487e41db64a4cb4dabda1c9a9dd083b6a4531fcf297a7f29f37cb22ba1f6c30c&=&format=webp&quality=lossless)

У цій папці знаходяться такі файли:

`Dialogue`  
`DialogueLine`  
`DialogueManager`  
`DialogueTrigger`  
`NPCController`

Це і є основа майбутньої системи.

---

# 📦 СКРІПТИ (З ПОЯСНЕННЯМ)

## 📄 Dialogue.cs

```csharp
using UnityEngine; // підключаємо Unity для ScriptableObject

[CreateAssetMenu(fileName = "NewDialogue", menuName = "Dialogue/Dialogue")] // додає пункт Create → Dialogue
public class Dialogue : ScriptableObject // створюємо asset для діалогу
{
    public DialogueLine[] lines; // масив реплік
}
```

---

## 📄 DialogueLine.cs

```csharp
using UnityEngine; // підключаємо Unity

[System.Serializable] // щоб Unity показував це в інспекторі
public class DialogueLine // одна репліка
{
    public string speakerName; // ім’я персонажа

    [TextArea(2, 5)] // велике поле тексту
    public string text; // текст репліки
}
```

---

## 📄 DialogueManager.cs

```csharp
using System.Collections.Generic; // для Queue
using UnityEngine; // база Unity
using UnityEngine.UI; // для Text

public class DialogueManager : MonoBehaviour // менеджер діалогу
{
    public static DialogueManager Instance; // глобальний доступ

    public GameObject dialoguePanel; // панель
    public Text speakerText; // ім’я
    public Text dialogueText; // текст

    private Queue<DialogueLine> lines = new Queue<DialogueLine>(); // черга

    private void Awake() // при старті
    {
        Instance = this; // зберігаємо інстанс
        dialoguePanel.SetActive(false); // ховаємо панель
    }

    private void Update() // кожен кадр
    {
        if (dialoguePanel.activeSelf && Input.GetKeyDown(KeyCode.Space)) // якщо відкрито і пробіл
        {
            ShowNextLine(); // наступна репліка
        }
    }

    public void StartDialogue(Dialogue dialogue) // старт діалогу
    {
        dialoguePanel.SetActive(true); // показуємо UI
        lines.Clear(); // очищаємо

        foreach (var line in dialogue.lines) // додаємо всі репліки
        {
            lines.Enqueue(line);
        }

        ShowNextLine(); // перша репліка
    }

    public void ShowNextLine() // наступна
    {
        if (lines.Count == 0) // якщо кінець
        {
            EndDialogue(); // закриваємо
            return;
        }

        var line = lines.Dequeue(); // беремо наступну

        speakerText.text = line.speakerName; // ім’я
        dialogueText.text = line.text; // текст
    }

    public void EndDialogue() // кінець
    {
        dialoguePanel.SetActive(false); // ховаємо
    }
}
```

---

## 📄 DialogueTrigger.cs

```csharp
using UnityEngine;

public class DialogueTrigger : MonoBehaviour, IInteractable // NPC взаємодія
{
    public Dialogue dialogue; // діалог

    public void Interact(GameObject interactor) // при натисканні E
    {
        Debug.Log("Interacted by: " + interactor.name); // лог
        DialogueManager.Instance.StartDialogue(dialogue); // запуск
    }
}
```

---

## 📄 NPCController.cs

```csharp
using UnityEngine;

public class NPCController : MonoBehaviour
{
    public Animator animator; // аніматор
    public float detectionRadius = 3f; // радіус
    public Transform player; // гравець

    private bool isPlayerNear = false; // стан

    private void Update()
    {
        float distance = Vector2.Distance(transform.position, player.position); // дистанція

        if (distance <= detectionRadius) // якщо близько
        {
            if (!isPlayerNear)
            {
                isPlayerNear = true;
                animator.SetBool("CanTalk", true); // включає анімацію
            }
        }
        else
        {
            if (isPlayerNear)
            {
                isPlayerNear = false;
                animator.SetBool("CanTalk", false); // назад idle
            }
        }
    }
}
```

---

## Крок 2. Додавання NPC на сцену та підготовка анімації

На другому скріншоті видно NPC на сцені з назвою `NPC_Dialog`. Також відкрито вкладку Animation, де обирається кліп для персонажа. Тут готується анімація, яка буде вмикатися, коли персонаж знаходиться поруч і з ним можна поговорити.

![Крок 2](https://media.discordapp.net/attachments/917547349864230912/1484619083012898866/image.png?ex=69bee2c4&is=69bd9144&hm=323c7a9fc171185ffaa661208ef3a77b59ada88efbc4cb4425d563f4d44c8c36&=&format=webp&quality=lossless&width=1601&height=856)

На цьому етапі важливо, щоб NPC уже був окремим об’єктом на сцені, мав спрайт і Animator. У списку кліпів видно анімації персонажа. Саме з них буде побудовано поведінку для станів спокою та стану готовності до діалогу.

---

## Крок 3. Створення параметра CanTalk в Animator

На третьому скріншоті показано вікно Animator. Тут створюється параметр `CanTalk`. Саме він перемикає NPC між звичайним станом і станом, коли персонаж реагує на наближення гравця.

![Крок 3](https://media.discordapp.net/attachments/917547349864230912/1484619717145530368/image.png?ex=69bee35b&is=69bd91db&hm=bfd448a03a2bf67b02ae250f6728a93a4e67d4a362a55ffa7a5c3342f8496719&=&format=webp&quality=lossless&width=1630&height=856)

Усередині Animator є два стани:

`Idle`  
`Talk`

Між ними створюються переходи. Для переходу з `Idle` у `Talk` використовується умова, коли `CanTalk = true`. Це означає, що гравець підійшов досить близько.

---

## Крок 4. Налаштування переходу Idle → Talk

На четвертому скріншоті відкриті налаштування переходу з `Idle` у `Talk`. Тут використовується умова `CanTalk = true`.

![Крок 4](https://media.discordapp.net/attachments/917547349864230912/1484620099251081257/image.png?ex=69bee3b6&is=69bd9236&hm=574838a30f463e00df39501a04c924685b58344b2b32dd3ef3e19d344009661d&=&format=webp&quality=lossless&width=1376&height=869)

На цьому кроці перевіряється, щоб перехід відбувався саме по умові, а не випадково. Це дозволяє NPC міняти поведінку лише тоді, коли гравець підійшов до нього.

---

## Крок 5. Налаштування переходу Talk → Idle

На п’ятому скріншоті відкрито зворотний перехід. Тут використовується умова `CanTalk = false`.

![Крок 5](https://media.discordapp.net/attachments/917547349864230912/1484620270005260358/image.png?ex=69bee3df&is=69bd925f&hm=c65c6c3ca796f2730e89a496670322ee5913d5ee70c186853f9a133ab1b58982&=&format=webp&quality=lossless)

Коли гравець відходить від NPC, параметр повертається у false, і персонаж переходить назад у `Idle`. Таким чином створюється проста, але зрозуміла реакція NPC на присутність гравця.

---

## Крок 6. Створення Canvas для діалогу

На шостому скріншоті показано створення нового UI Canvas через меню Unity. Саме в ньому буде розміщена панель діалогу.

![Крок 6](https://media.discordapp.net/attachments/917547349864230912/1484620489648242838/image.png?ex=69bee413&is=69bd9293&hm=f552ae45a412a84753cde646d0d51416bc4f657617cd7e6af13973ff46fb6205&=&format=webp&quality=lossless&width=1647&height=856)

Після створення Canvas він стане контейнером для всього інтерфейсу діалогу. Це окремий UI шар, який відображається поверх ігрової сцени.

---

## Крок 7. Налаштування Canvas

На сьомому скріншоті видно новий `DialogCanvas`. У нього налаштований режим відображення `Screen Space - Camera`, а також прив’язана `Main Camera`.

![Крок 7](https://media.discordapp.net/attachments/917547349864230912/1484620940934516797/image.png?ex=69bee47f&is=69bd92ff&hm=0579b68cbd5c7de39cf4d38c032d3173c3057a85cbad6d60e6c0ff9f138d347c&=&format=webp&quality=lossless)

Це означає, що UI діалогу буде коректно відображатися через основну камеру гри. Такий варіант добре підходить для 2D сцени, де треба бачити інтерфейс поверх ігрового поля.

---

## Крок 8. Створення панелі та текстів усередині Canvas

На восьмому скріншоті показана структура `DialogCanvas`. Усередині нього створено `Image`, а вже в ньому два текстові елементи:

`Name (Text)`  
`Line (Text)`

![Крок 8](https://media.discordapp.net/attachments/917547349864230912/1484621791153356963/image.png?ex=69bee549&is=69bd93c9&hm=d1cce77b9e8b5ec5f48b4212b1768cf18848cd7b5caf9168e2f1d02ce79fb17b&=&format=webp&quality=lossless&width=1872&height=795)

`Image` виконує роль фону діалогу.  
`Name (Text)` показує ім’я мовця.  
`Line (Text)` показує саму репліку.

Саме ця структура згодом буде підключатися до менеджера діалогів.

---

## Крок 9. Створення об’єкта DialogueManager на сцені

На дев’ятому скріншоті створений порожній об’єкт `DialogueManager (Empty)`. На нього додається компонент `DialogueManager`, а в поля цього компонента прив’язуються елементи з Canvas.

![Крок 9](https://media.discordapp.net/attachments/917547349864230912/1484621921394884628/image.png?ex=69bee569&is=69bd93e9&hm=100eae4f96901ed3fb951033279dc76a05d40f21aef2f7145fa787f1c3fe4d84&=&format=webp&quality=lossless)

На цьому етапі важливо правильно підключити:

`Dialogue Panel` → `Image`  
`Speaker Text` → `Name (Text)`  
`Dialogue Text` → `Line (Text)`

Тепер менеджер знає, який саме UI відкривати та куди записувати ім’я і текст.

---

## Крок 10. Створення окремої папки для asset діалогів

На десятому скріншоті видно, що в папці `DialogSystem` створюється окрема папка `DialogsNPC`.

![Крок 10](https://media.discordapp.net/attachments/917547349864230912/1484622008825417789/image.png?ex=69bee57d&is=69bd93fd&hm=d52d405d165ccafff056b4044c75d0c61da23de7b99c42b2a3d7e1a9a58f6211&=&format=webp&quality=lossless&width=1017&height=960)

Це зручно для порядку в проєкті. У цій папці будуть зберігатися всі ScriptableObject діалоги для NPC.

---

## Крок 11. Створення нового діалогу через Create

На одинадцятому скріншоті показано меню Create, де є пункт `Dialogue > Dialogue`.

![Крок 11](https://media.discordapp.net/attachments/917547349864230912/1484622638687977604/image.png?ex=69bee614&is=69bd9494&hm=493731720033d45ad788698a3f3a02bd28f8df3e8dae90d1c34c6a50ff1372b4&=&format=webp&quality=lossless&width=1560&height=856)

Саме тут створюється новий asset діалогу. Після створення можна дати йому зрозумілу назву, наприклад під конкретного NPC.

---

## Крок 12. Заповнення реплік у ScriptableObject

На дванадцятому скріншоті відкритий створений діалог. Видно масив `Lines`, у якому вже додані кілька реплік з різними іменами та текстом.

![Крок 12](https://media.discordapp.net/attachments/917547349864230912/1484623183884583115/image.png?ex=69bee696&is=69bd9516&hm=1593e8078bdb02ab9003bfc315e906ce75861869f8c0362151a773b293d2d922&=&format=webp&quality=lossless&width=1872&height=829)

Тут по черзі записуються всі рядки діалогу.  
Кожен елемент це одна репліка.  
Для кожної репліки задається:

ім’я того, хто говорить  
текст репліки

Таким способом діалог стає повністю редагованим через інспектор, без жорсткого запису в коді сцени.

---

## Крок 13. Підключення компонентів до NPC

На тринадцятому скріншоті знову відкрито `NPC_Dialog`. У Inspector видно два важливі компоненти:

`NPC Controller (Script)`  
`Dialogue Trigger (Script)`

![Крок 13](https://media.discordapp.net/attachments/917547349864230912/1484623520356106411/image.png?ex=69bee6e6&is=69bd9566&hm=0a2d100aeaf04cd5230f956c2e1d2a658c0b32141d302ce96deeecd89b2c2ef1&=&format=webp&quality=lossless&width=1872&height=759)

У `NPC Controller` потрібно вказати:

Animator  
Player  
Detection Radius

У `Dialogue Trigger` потрібно вказати:

Dialogue

Саме тут NPC отримує посилання і на анімацію наближення, і на конкретний діалог.

![Крок 13.1](https://media.discordapp.net/attachments/917547349864230912/1484623650232467587/image.png?ex=69bee705&is=69bd9585&hm=72c77a61aa97874a9a2d44212eef1b33bb04dc18f043363093d98a27ffb0c514&=&format=webp&quality=lossless&width=1872&height=534)

Перенесіть для активації діалога діалог у відповідне місце.
---

## Крок 14. Прив’язка Player, Animator і правильного шару Interactable

На чотирнадцятому скріншоті видно підсумкове налаштування. У `NPC_Dialog` вибраний шар `Interactable`. Також до `NPC Controller` уже прив’язаний гравець і Animator.

![Крок 14](https://media.discordapp.net/attachments/917547349864230912/1484626723181170748/image.png?ex=69bee9e1&is=69bd9861&hm=72a01bab7e0fa5d3114c2fd95a81d9294df5331a36e39f8d13b680fb283a5b07&=&format=webp&quality=lossless)

Це фінальний крок з боку Inspector.

Після цього система працює так:

NPC знаходиться на шарі, який бачить система взаємодії  
NPC має колайдер для виявлення  
NPC реагує на наближення через Animator  
NPC має підключений ScriptableObject діалогу  
UI діалогу вже прив’язаний до менеджера

---

## Результат

Після проходження всіх цих кроків виходить така логіка:

гравець підходить до NPC  
NPC змінює анімацію, бо гравець поруч  
натискання клавіші взаємодії запускає діалог  
з’являється панель з іменем і текстом  
перехід між репліками відбувається через керування, яке вже налаштоване в менеджері діалогу

---

## Готова структура сцени

У фіналі в сцені є такі головні частини:

`NPC_Dialog` з Animator, Collider, NPCController і DialogueTrigger  
`DialogCanvas` з Image, Name Text і Line Text  
`DialogueManager` як окремий керуючий об’єкт  
`DialogWithNPC1` як ScriptableObject asset з репліками

---

## Що вийшло

У підсумку зібрана повноцінна базова система діалогу для Unity 2D, де:

NPC можна анімувати при наближенні  
діалоги зберігаються окремими assets  
інтерфейс діалогу винесений у Canvas  
менеджер централізовано показує ім’я й текст  
кожному NPC можна прив’язати свій окремий діалог