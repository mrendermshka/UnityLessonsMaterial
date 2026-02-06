
# Урок Unity 2D Parkour
## Крок 1. Пошук безкоштовних ассетів в Unity Asset Store

---

## Мета кроку

Підготувати базу для створення 2D паркур гри:
- знайти **оточення (Environment)**
- знайти **персонажа (Character)**
- обидва пакети повинні бути **безкоштовні**

---

## Перехід в Unity Asset Store

Перейдіть за посиланням:
https://assetstore.unity.com/

---

## Крок 1. Обрати категорію 2D

В Asset Store відкрийте:

```

2D → Environments

```

Приклад:

![AssetStore 2D Environments](https://media.discordapp.net/attachments/917547349864230912/1469365441221627980/image.png?ex=698764b4&is=69861334&hm=3c28f55949e1985670c54df00598d7eeab2754fc762444b7134c235c06e224b3&=&format=webp&quality=lossless)

---

## Крок 2. Вибрати безкоштовні ассети

У фільтрах справа увімкніть:

```

Pricing → Free Assets

```

Приклад:

![Free Assets Filter](https://media.discordapp.net/attachments/917547349864230912/1469365583240761627/image.png?ex=698764d6&is=69861356&hm=b6ac1618b96455a7a3af95c7477152697151f9508b96cfbdadf52b90bcfe56ab&=&format=webp&quality=lossless)

---

## Крок 3. Завантажити Environment Pack

Виберіть будь-який пак, який вам подобається:
- Pixel Forest
- Platformer Tiles
- Parallax Backgrounds
- Nature Pixel Pack
- або будь-який інший

Головне:
- стиль повинен подобатись
- пак безкоштовний

---

## Крок 4. Завантажити Character Pack

Перейдіть:

```

2D → Characters

```

Приклад:

![AssetStore 2D Characters](https://media.discordapp.net/attachments/917547349864230912/1469365862757699665/image.png?ex=69876519&is=69861399&hm=8fdf23ad3f013196e7678d31d609798f1a6564348cc1b3fb55a16f024fcb73e7&=&format=webp&quality=lossless)

---

## Що потрібно знайти

### Environment Pack
Використовується для:
- платформ
- землі
- дерев
- фону
- декорацій

### Character Pack
Використовується для:
- гравця
- анімацій бігу
- стрибків
- idle анімації

---

## Важливо

Обидва пакети повинні бути:
- FREE
- 2D
- підходити під один стиль (бажано)

---

# Крок. Створення нового 2D проекту в Unity

## Що потрібно зробити

1. Відкрийте **Unity Hub**

2. Перейдіть у вкладку  
   **Projects**

3. Натисніть  
   **New Project**

---

## Приклад

![Create Project Screen](https://media.discordapp.net/attachments/917547349864230912/1469367281317449914/image.png?ex=6987666b&is=698614eb&hm=b0a010fc207256d98532d95d12c263ca1672d949b44d38b9e4c675cdeee39df5&=&format=webp&quality=lossless)

---

## Налаштування проекту

Виберіть:

**Template:**  
`2D (Built-In Render Pipeline)`

**Editor Version:**  
Рекомендовано LTS версію (наприклад 2022 LTS)

**Project Name:**  
Введіть назву вашого проекту

**Location:**  
Виберіть папку, де буде збережений проект

---

## Завершення

Натисніть кнопку:

```

Create Project

```
# Крок. Імпорт ассету з Asset Store в Unity

## Що потрібно зробити

1. Поверніться на сторінку ассету в **Unity Asset Store**

2. Натисніть кнопку  
**Add to My Assets**

![Add To My Assets](https://media.discordapp.net/attachments/917547349864230912/1469366391076425728/image.png?ex=69876597&is=69861417&hm=3c29fbc67c32ef0195f013cf95ed07681bbda2aca883b4dc634f4e60faf7343a&=&format=webp&quality=lossless)

---

3. Натисніть  
**Open in Unity**

---

4. Якщо браузер запитає, натисніть  
**Відкрити Unity Editor**

---

## В Unity

5. Відкриється Package Manager

Знайдіть ваш ассет і натисніть:

**Download**

![Download Asset](https://media.discordapp.net/attachments/917547349864230912/1469367086940688626/image.png?ex=6987663d&is=698614bd&hm=eefb31beded0307e4f7979213e242c69b21599e1f2decfab2be7671ca1c43c14&=&format=webp&quality=lossless)

---

6. Після завантаження натисніть:

**Import**

![Import Asset](https://media.discordapp.net/attachments/917547349864230912/1469367086626373632/image.png?ex=6987663c&is=698614bc&hm=b5e6c1938b9e4d3e7fbcd411015f52eee84ee8edc3d3854c3579bb8e22d7e163&=&format=webp&quality=lossless)

---

7. У вікні імпорту натисніть:

**Download**

![Import Window](https://media.discordapp.net/attachments/917547349864230912/1469368412403663019/image.png?ex=69876779&is=698615f9&hm=c8ad3050b0de14b295cb4c3f530b6b5d56cd265b511f2e8084449ac69bdd41f8&=&format=webp&quality=lossless)

**Import**

![Import Window](https://media.discordapp.net/attachments/917547349864230912/1469368412819034306/image.png?ex=69876779&is=698615f9&hm=baad22efda3d8bc6273f00abbfabbfaca0a4aa55c1efafb452f7c4cb807572a8&=&format=webp&quality=lossless)

та ще раз імпорт

![Import Window](https://media.discordapp.net/attachments/917547349864230912/1469370781669523641/image.png?ex=698769ad&is=6986182d&hm=388c0fcfd4780c366cc91606d55d2dbc4dd5e6c6655514ea7c22d9a5234c5c89&=&format=webp&quality=lossless)

---

## Важливо

Повторіть ці ж кроки для другого ассету з Asset Store.

---

Після імпорту ассет зʼявиться у папці **Assets** у вашому проекті.


# Крок. Панелі Unity Editor та створення міні паркуру

## Що потрібно зробити

Вивчіть основні панелі Unity Editor та створіть просту сцену міні паркуру з імпортованих ассетів.

---

## Приклад розташування панелей

![Unity Panels](https://cdn.discordapp.com/attachments/917547349864230912/1469371492062990458/image.png?ex=69876a57&is=698618d7&hm=b33f5072c6afe5c7d5e19d9c13071a023118fe0bdf804cddfc2fd586ac032076&)

---

## Основні панелі

### Hierarchy
Показує всі обʼєкти сцени.  
Тут видно камеру, спрайти платформ та інші обʼєкти.

---

### Scene
Робоча область сцени.  
Тут розташовуються платформи та будується рівень.

---

### Inspector
Показує налаштування вибраного обʼєкта.  
Тут можна змінювати позицію, масштаб, матеріали, спрайти.

---

### Project
Містить всі ассети проекту.  
Звідси перетягуються спрайти в сцену.

---

## Завдання

Створіть міні паркур:

1. Перетягніть кілька платформ (Grass / Tiles) у Scene  
2. Розташуйте їх на різній висоті  
3. Зробіть платформу старту і платформу фінішу  
4. Розташуйте платформи так, щоб між ними можна було стрибати

---

Головна задача:  
Зрозуміти, яка панель за що відповідає, і навчитися розкладати рівень зі спрайтів.


# Крок. Додавання персонажа на сцену

## Що потрібно зробити

Додайте персонажа зі скачаного Character Pack на сцену.

---

## Як додати персонажа

1. Відкрийте панель **Project**

2. Знайдіть папку з персонажем  
(зазвичай Character / Player / Sprites)

3. Знайдіть спрайт персонажа (Idle або Base)

4. Перетягніть спрайт:
- або в **Scene**
- або в **Hierarchy**

---

## Що відбудеться

Unity автоматично:
- створить GameObject
- додасть Sprite Renderer
- відобразить персонажа на сцені

---

## Після додавання

Перевірте:

- Персонаж видно в Scene
- Персонаж видно в Game View
- Персонаж знаходиться на платформі
- Масштаб виглядає нормально

---

Головна задача:  
Персонаж повинен стояти на платформі і бути видимим в камері.

# Крок. Додавання фізики персонажу та платформам

## Що потрібно зробити

Додайте фізику персонажу та колайдери платформам.

---

## Додати компоненти персонажу

1. Виділіть персонажа в **Hierarchy**

2. В панелі **Inspector** натисніть:
```

Add Component

```

3. Додайте:
- **Rigidbody 2D**
- **Polygon Collider 2D**

---

## Приклад

![Rigidbody and Polygon Collider](https://cdn.discordapp.com/attachments/917547349864230912/1469372645668814869/image.png?ex=69876b6a&is=698619ea&hm=9b6b3f12e0c6411c18c565c7956aa0308e450f4c31317f25d7879996c3ebc54c&)

---

## Що роблять ці компоненти

### Rigidbody 2D
Додає фізику:
- гравітацію
- падіння
- рух через фізику

---

### Polygon Collider 2D
Створює форму зіткнення по формі спрайта.

---

## Додати колайдери платформам

1. Виділіть кожен блок (Grass / Tile)

2. Натисніть:
```

Add Component

```

3. Додайте:
- **Box Collider 2D**

---

## Результат

Персонаж:
- падає вниз через гравітацію
- стоїть на платформах

Платформи:
- мають зону зіткнення
- тримають персонажа

---

Головна задача:  
Персонаж повинен падати і стояти на платформах.

# Крок. Налаштування Collider під форму спрайта

## Що потрібно зробити

Перевірте форму Collider персонажа.  
Якщо зелена обводка не співпадає зі спрайтом, її потрібно відредагувати.

---

## Як виглядає Collider

Зелена обводка навколо персонажа це зона зіткнення.

![Collider Example 1](https://media.discordapp.net/attachments/917547349864230912/1469372906298413146/image.png?ex=69876ba8&is=69861a28&hm=3f6d3e0bd907a9e4b6f90822884bb78f16ac8d1faab649b6a44f4134cf96890a&=&format=webp&quality=lossless)

---

## Якщо Collider не співпадає зі спрайтом

Причини можуть бути:
- Collider створився не точно
- У спрайта є прозорий фон
- Форма персонажа не прямокутна

---

## Як виправити

1. Виділіть персонажа
2. В Inspector знайдіть **Polygon Collider 2D**
3. Натисніть кнопку:
```

Edit Collider

```

![Edit Collider Button](https://media.discordapp.net/attachments/917547349864230912/1469372906730557440/image.png?ex=69876ba8&is=69861a28&hm=3857d34490750cfb5e79047ecf5981507e0b2421f03e2f7e374370d246f1a27c&=&format=webp&quality=lossless)

---

## Після натискання Edit Collider

Можна:
- рухати точки колайдера
- додавати точки
- видаляти точки
- повторити форму персонажа

---

## Результат

Collider повинен:
- повторювати форму персонажа
- не заходити далеко в прозору область
- не бути значно більшим за персонажа

---

Головна задача:  
Collider повинен максимально точно повторювати форму персонажа.

# Крок. Створення скрипта PlayerMovement і базовий рух через rb.velocity

В панелі **Project** натисніть правою кнопкою миші по папці, де зберігаєте скрипти, потім виберіть **Create → C# Script**.

Приклад:

![Create C# Script](https://media.discordapp.net/attachments/917547349864230912/1469373991239155847/image.png?ex=69876cab&is=69861b2b&hm=8d128eab611b93e91990fc3bf1d58d3bebc05d7e14093f9b7ec3a63c2ce8c506&=&format=webp&quality=lossless&width=880&height=960)

Назвіть скрипт: `PlayerMovement`

Далі відкрийте його та напишіть код нижче.
```csharp
using UnityEngine;

public class PlayerMovement : MonoBehaviour
{
    [Header("References")]
    public Rigidbody2D rb;

    [Header("Movement")]
    public float moveSpeed = 6f;

    [Header("Jump")]
    public float jumpForce = 12f;

    [Header("Ground Checkers")]
    public Transform groundCheckL;
    public Transform groundCheckR;
    public float groundCheckRadius = 0.15f;
    public LayerMask groundLayer;

    private float moveDirection = 0f;
    private bool jumpPressed = false;

    private void Start()
    {
        if (rb == null)
            rb = GetComponent<Rigidbody2D>();
    }

    private void Update()
    {
        moveDirection = 0f;

        if (Input.GetKey(KeyCode.A) || Input.GetKey(KeyCode.LeftArrow))
            moveDirection = -1f;

        if (Input.GetKey(KeyCode.D) || Input.GetKey(KeyCode.RightArrow))
            moveDirection = 1f;

        if (Input.GetKeyDown(KeyCode.Space))
            jumpPressed = true;
    }

    private void FixedUpdate()
    {
        if (rb == null)
            return;

        rb.velocity = new Vector2(moveDirection * moveSpeed, rb.velocity.y);

        if (jumpPressed && CheckGrounded())
        {
            Jump();
            jumpPressed = false;
        }
    }

    public void Jump()
    {
        rb.velocity = new Vector2(rb.velocity.x, jumpForce);
    }

    public bool CheckGrounded()
    {
        bool groundedL = false;
        bool groundedR = false;

        if (groundCheckL != null)
        {
            groundedL = Physics2D.OverlapCircle(
                groundCheckL.position,
                groundCheckRadius,
                groundLayer
            );
        }

        if (groundCheckR != null)
        {
            groundedR = Physics2D.OverlapCircle(
                groundCheckR.position,
                groundCheckRadius,
                groundLayer
            );
        }

        return groundedL || groundedR;
    }

    private void OnDrawGizmosSelected()
    {
        Gizmos.color = Color.green;

        if (groundCheckL != null)
            Gizmos.DrawWireSphere(groundCheckL.position, groundCheckRadius);

        if (groundCheckR != null)
            Gizmos.DrawWireSphere(groundCheckR.position, groundCheckRadius);
    }
}
```
# Крок. Відкриття вікон Animator та Animation

## Що потрібно зробити

Активуйте вікна **Animator** та **Animation** у Unity.

---

## Як відкрити

Верхнє меню Unity:

```

Window → Animation → Animation
Window → Animation → Animator

```

---

## Приклад

![Open Animator And Animation](https://media.discordapp.net/attachments/917547349864230912/1469378726260244724/image.png?ex=69877114&is=69861f94&hm=fda0eb0f5ef7fb35873b54fcf05ed64b01fc284804cdced2188259a6d5580574&=&format=webp&quality=lossless)

---

## Для чого вони потрібні

### Animation
Тут створюються анімації:
- Idle
- Run
- Jump
- Fall

---

### Animator
Тут створюється логіка переходів між анімаціями:
- Idle → Run
- Run → Jump
- Jump → Fall
- Fall → Idle

---

## Результат

У вас повинні бути відкриті два вікна:
- Animation
- Animator

# Крок. Налаштування переходів в Animator (Make Transition)

## Що потрібно зробити

У вікні **Animator** створіть переходи між станами, щоб вийшла структура як на прикладі.

---

## Приклад структури

![Animator Transitions](https://cdn.discordapp.com/attachments/917547349864230912/1469379823594897631/image.png?ex=69877219&is=69862099&hm=4cb26b13e0847a6849c364e98d5b4b9c7efd93ab41ade7195c070f9df7fe3590&)

---

## Як створити перехід (Make Transition)

1. У **Animator** натисніть правою кнопкою миші по стану (наприклад, Idle)
2. Оберіть:
```

Make Transition

```
3. Клікніть по стану, куди має вести стрілка (наприклад, Walk)

---

## Які переходи потрібно зробити

Зробіть переходи між цими станами:
- `Idle → Walk`
- `Walk → Idle`
- `Idle → Jump`
- `Jump → Idle`
- `Walk → Jump`
- `Jump → Walk`

---

## Результат

Після цього в Animator повинні бути стрілки між станами як на прикладі.


# Крок. Додавання параметрів Animator (IsWalking, IsJumping)

## Що потрібно зробити

Додайте два параметри в Animator:
- `IsWalking` тип **Bool**
- `IsJumping` тип **Trigger**

---

## Як додати параметри

1. Відкрийте вкладку **Animator**
2. Перейдіть у вкладку **Parameters**
3. Натисніть кнопку:
```

+

```

---

## Додайте параметр ходьби

Тип:
```

Bool

```

Назва:
```

IsWalking

```

---

## Додайте параметр стрибка

Тип:
```

Trigger

```

Назва:
```

IsJumping

```

---

## Приклад

![Animator Parameters](https://media.discordapp.net/attachments/917547349864230912/1469380129645137930/image.png?ex=69877262&is=698620e2&hm=468589ba564f26af61af5e84ebe625ccba45b63523aa5d180d2a7c73e92fac03&=&format=webp&quality=lossless)

---

## Результат

У Parameters повинно бути:
- IsWalking (Bool)
- IsJumping (Trigger)

# Крок. Налаштування переходів у Jump

## Що потрібно зробити

Налаштуйте всі переходи, які ведуть у стан **Jump**, однаково.

---

## Які переходи налаштувати

Усі переходи:
- Idle → Jump  
- Walk → Jump  

---

## Як налаштувати перехід

Виберіть перехід у Animator  
Потім відкрийте **Inspector**

---

## Налаштування

### Вимкніть
```

Has Exit Time

```

---

### У Conditions додайте
```

IsJumping

```

---

## Приклад

![Jump Transition Settings](https://media.discordapp.net/attachments/917547349864230912/1469380760287969311/image.png?ex=698772f9&is=69862179&hm=93ebadeffa3c2b9b729c4f3c55ce2a8998b356c7b5a87dbe8b482d338cb9bf86&=&format=webp&quality=lossless)

---

## Результат

Стрибок буде запускатися:
- миттєво
- через Trigger IsJumping

# Крок. Налаштування переходів Walk ↔ Idle

## Що потрібно зробити

Налаштуйте переходи:
- Idle → Walk  
- Walk → Idle  

---

## 1) Перехід Idle → Walk

Виберіть перехід **Idle → Walk** у Animator.

### Налаштування

Вимкніть:
```

Has Exit Time

```

У Conditions встановіть:
```

IsWalking = true

```

---

## 2) Перехід Walk → Idle

Виберіть перехід **Walk → Idle**.

### Налаштування

Вимкніть:
```

Has Exit Time

```

У Conditions встановіть:
```

IsWalking = false

```

---

## Приклад

Idle → Walk:

![Idle To Walk](https://media.discordapp.net/attachments/917547349864230912/1469381204125028475/image.png?ex=69877362&is=698621e2&hm=e62cea9420f0a494697bfce1ea29495b0b0bd63b116278b767a067729e7ca49a&=&format=webp&quality=lossless)

Walk → Idle:

![Walk To Idle](https://media.discordapp.net/attachments/917547349864230912/1469381204611436818/image.png?ex=69877362&is=698621e2&hm=27b64cf2bff14efaadc07f86d971149aac93c620d146478cbb7ed376260c9e9f&=&format=webp&quality=lossless)

---

## Результат

Анімації будуть перемикатися:
- Почав рухатися → Walk
- Зупинився → Idle


Крок Зміна коду для анімацій. Нижче версія коду з підключеним Animator:

Що додано:

* Animator як public reference
* SetBool("IsWalking") для ходьби
* SetTrigger("IsJumping") при стрибку


---

### Оновлений код

```csharp
using UnityEngine;

public class PlayerMovement : MonoBehaviour
{
    [Header("References")]
    public Rigidbody2D rb;
    public Animator animator;

    [Header("Movement")]
    public float moveSpeed = 6f;

    [Header("Jump")]
    public float jumpForce = 12f;

    [Header("Ground Checkers")]
    public Transform groundCheckL;
    public Transform groundCheckR;
    public float groundCheckRadius = 0.15f;
    public LayerMask groundLayer;

    private float moveDirection = 0f;
    private bool jumpPressed = false;

    private void Start()
    {
        if (rb == null)
            rb = GetComponent<Rigidbody2D>();

        if (animator == null)
            animator = GetComponent<Animator>();
    }

    private void Update()
    {
        moveDirection = 0f;

        if (Input.GetKey(KeyCode.A) || Input.GetKey(KeyCode.LeftArrow))
            moveDirection = -1f;

        if (Input.GetKey(KeyCode.D) || Input.GetKey(KeyCode.RightArrow))
            moveDirection = 1f;

        if (Input.GetKeyDown(KeyCode.Space))
            jumpPressed = true;

        // Анімація ходьби
        if (animator != null)
            animator.SetBool("IsWalking", moveDirection != 0f);
    }

    private void FixedUpdate()
    {
        if (rb == null)
            return;

        rb.velocity = new Vector2(moveDirection * moveSpeed, rb.velocity.y);

        if (jumpPressed && CheckGrounded())
        {
            Jump();

            if (animator != null)
                animator.SetTrigger("IsJumping");

            jumpPressed = false;
        }
    }

    public void Jump()
    {
        rb.velocity = new Vector2(rb.velocity.x, jumpForce);
    }

    public bool CheckGrounded()
    {
        bool groundedL = false;
        bool groundedR = false;

        if (groundCheckL != null)
        {
            groundedL = Physics2D.OverlapCircle(
                groundCheckL.position,
                groundCheckRadius,
                groundLayer
            );
        }

        if (groundCheckR != null)
        {
            groundedR = Physics2D.OverlapCircle(
                groundCheckR.position,
                groundCheckRadius,
                groundLayer
            );
        }

        return groundedL || groundedR;
    }

    private void OnDrawGizmosSelected()
    {
        Gizmos.color = Color.green;

        if (groundCheckL != null)
            Gizmos.DrawWireSphere(groundCheckL.position, groundCheckRadius);

        if (groundCheckR != null)
            Gizmos.DrawWireSphere(groundCheckR.position, groundCheckRadius);
    }
}
```
Після додавання скрипта PlayerMovement на об’єкт Player потрібно обов’язково підключити всі посилання у Inspector. У поле Rb перетягується Rigidbody2D з об’єкта Player. У поле Animator потрібно перетягнути компонент Animator цього ж Player, щоб код міг керувати анімаціями ходьби та стрибка.

Далі потрібно підключити точки перевірки землі. У поля Ground Check L та Ground Check R перетягуються відповідні empty-об’єкти з Hierarchy, які розташовані біля лівої та правої ноги персонажа. Вони використовуються для перевірки, чи персонаж стоїть на землі.

У параметрі Ground Layer потрібно вибрати шар Ground, який ви створювали раніше та призначали всім блокам платформи. Без цього перевірка приземлення працювати не буде.

Якщо всі поля підключені правильно, персонаж зможе рухатися, стрибати та коректно перемикати анімації.
![](https://media.discordapp.net/attachments/917547349864230912/1469386651309703168/image.png?ex=69877875&is=698626f5&hm=35dba639b70f192643f6d3318007d0a9e7b1e3be6373bc752e72f9364d2c1b6d&=&format=webp&quality=lossless&width=1872&height=621)


# Тепер запустіть та перевірте!

# Домашнє завдання

Оновіть скрипт **PlayerMovement** так, щоб спрайт персонажа автоматично розвертався у сторону руху.

Коли персонаж рухається вправо, він має дивитися вправо.  
Коли персонаж рухається вліво, він має дивитися вліво.  
Якщо персонаж стоїть на місці, поворот змінювати не потрібно.

Підказка:  
Подумайте, як можна змінювати `localScale` або `flipX` у SpriteRenderer або змінювати знак масштабу по осі X залежно від напрямку руху.

Результат повинен працювати разом з уже реалізованим рухом та анімаціями.
