
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

![AssetStore 2D Environments](https://media.discordapp.net/attachments/917547349864230912/1469365441221627980/image.png?ex=69a50e74&is=69a3bcf4&hm=4c44899a0c76c665dee2f730d1ce292f564bdab2a86f36648dc087b6002dfef5&=&format=webp&quality=lossless&width=1334&height=358)

---

## Крок 2. Вибрати безкоштовні ассети

У фільтрах справа увімкніть:

```

Pricing → Free Assets

```

Приклад:

![Free Assets Filter](https://media.discordapp.net/attachments/917547349864230912/1469365583240761627/image.png?ex=69a50e96&is=69a3bd16&hm=19d7af6bf3f4435823190bf3ea7e8aa4c031b094cc781f8585fabb7991dd46b9&=&format=webp&quality=lossless&width=1334&height=643)

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

![AssetStore 2D Characters](https://media.discordapp.net/attachments/917547349864230912/1469365862757699665/image.png?ex=69a50ed9&is=69a3bd59&hm=da3988f3b56290f3dd1390c3ca812f94417ae3f7e4eb12a216364bdbd0be0027&=&format=webp&quality=lossless&width=1334&height=344)

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

![Create Project Screen](https://media.discordapp.net/attachments/917547349864230912/1469367086626373632/image.png?ex=69a50ffc&is=69a3be7c&hm=c963b4491db2f896c1a1ba3cbf27b42566a907caaac0ce717e80300d7d44b9a0&=&format=webp&quality=lossless&width=1147&height=421)

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

![Add To My Assets](https://media.discordapp.net/attachments/917547349864230912/1469367086940688626/image.png?ex=69a50ffd&is=69a3be7d&hm=fa3774d3513efd4aab3d49c3461a7850c44e358079a4591f2fd650e5bea3ce4d&=&format=webp&quality=lossless&width=1147&height=95)

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

![Download Asset](https://media.discordapp.net/attachments/917547349864230912/1469367086626373632/image.png?ex=69a50ffc&is=69a3be7c&hm=c963b4491db2f896c1a1ba3cbf27b42566a907caaac0ce717e80300d7d44b9a0&=&format=webp&quality=lossless&width=1147&height=421)

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

![Open Animator And Animation](https://media.discordapp.net/attachments/917547349864230912/1469378726260244724/image.png?ex=69a51ad4&is=69a3c954&hm=1d01c22b354bb9fe63255e852619578abb85bef47985772130005b361b32185a&=&format=webp&quality=lossless&width=961&height=983)

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

![Animator Transitions](https://media.discordapp.net/attachments/917547349864230912/1469379823594897631/image.png?ex=69a51bd9&is=69a3ca59&hm=a8917cb4911a15acb50f8382cf6cfc74286552618d50fd5de63df49b3cd70edd&=&format=webp&quality=lossless&width=1026&height=504)

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

![Animator Parameters](https://media.discordapp.net/attachments/917547349864230912/1469380129645137930/image.png?ex=69a51c22&is=69a3caa2&hm=aa0664efb9780160f5dd76d142688be117ffac96f67b3eb8b91d8f5ffc5148e2&=&format=webp&quality=lossless&width=734&height=659)

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

![Jump Transition Settings](https://media.discordapp.net/attachments/917547349864230912/1469380760287969311/image.png?ex=69a51cb9&is=69a3cb39&hm=31dc67ea6853a5958f883d6d76350f136a4c77ef4fd43cfa45592377a4e687a0&=&format=webp&quality=lossless&width=1197&height=1093)

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

![Idle To Walk](https://media.discordapp.net/attachments/917547349864230912/1469381204125028475/image.png?ex=69a51d22&is=69a3cba2&hm=daadf38820e8a2690d3982d814cf94a318bc71148f4ef06197071dd09904d174&=&format=webp&quality=lossless&width=1147&height=1044)

Walk → Idle:

![Walk To Idle](https://media.discordapp.net/attachments/917547349864230912/1469381204611436818/image.png?ex=69a51d22&is=69a3cba2&hm=f7f8bb2f3a170b96481e12048b85bfe911666d0ab40624c83904f8befdb4ba2a&=&format=webp&quality=lossless&width=1147&height=1051)

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
![](https://media.discordapp.net/attachments/917547349864230912/1469386651309703168/image.png?ex=69a52235&is=69a3d0b5&hm=88da2272f4e7171cd1a7df7f4f6a373860df6bbc5a3680ebbb519c0d6fbd55e8&=&format=webp&quality=lossless&width=1334&height=443)


# Тепер запустіть та перевірте!

# Домашнє завдання

Оновіть скрипт **PlayerMovement** так, щоб спрайт персонажа автоматично розвертався у сторону руху.

Коли персонаж рухається вправо, він має дивитися вправо.  
Коли персонаж рухається вліво, він має дивитися вліво.  
Якщо персонаж стоїть на місці, поворот змінювати не потрібно.

Підказка:  
Подумайте, як можна змінювати `localScale` або `flipX` у SpriteRenderer або змінювати знак масштабу по осі X залежно від напрямку руху.

Результат повинен працювати разом з уже реалізованим рухом та анімаціями.
