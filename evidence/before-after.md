# 14 виправлень: до і після

Базовий стан: `569b6a0498e69596d0cdf638633281c1c097daf4`; виправлений: `39a42174241d121d5f55a6b4fb463ddbb9e7eb4c`.

## 2.1. Змістовний заголовок сторінки

Page title не пояснював, що відкрито магазин і добірку одягу.

### До

main.html, рядок 9

```html

    <title>Page title</title>

```

### Після

main.html, рядок 10

```html

<title>Best Picks 2020 | ACME Fashion House</title>

```

Назва вкладки відрізняє головну сторінку від Create Account.

Результат: У Chromium document.title дорівнює Best Picks 2020 | ACME Fashion House; назва форми інша.

## 2.2. Мова документа

На головній сторінці не було глобальної мови.

### До

main.html, рядок 2

```html

<html>

```

### Після

main.html, рядок 3

```html

<html lang="en-GB">

```

en-GB задає британську англійську для допоміжних технологій.

Результат: DOM містить lang="en-GB". Порушення axe html-has-lang усунено. Вимову екранним зчитувачем не перевірено.

## 2.3. Пропуск навігації

Перед основним вмістом не було skip link.

### До

main.html, рядок 11

```html

<body>
<div class="navbar navbar-topbar navbar-expand-xl navbar-light bg-light">

```

### Після

main.html, рядок 12

```html

<body><a class="skip-link" href="#main-content">Skip to main content</a>


```

main.html, рядок 100

```html

<main id="main-content" tabindex="-1"><h1 class="sr-hidden">ACME Fashion House collections</h1>

```

Перший Tab показує посилання. Enter передає фокус у main, наступний Tab веде до Shop Women.

Результат: Перевірено натисканнями Tab → Enter → Tab: skip link видимий; activeElement.id = main-content; далі Shop Women.

## 2.4. Ієрархія заголовків

Назви основних розділів були div із класами розміру шрифту.

### До

main.html, рядок 282

```html

                <div class="mb-4 h2BestPicks">Best Picks 2020</div>

```

### Після

main.html, рядок 251

```html

<h2 class="mb-4 h2BestPicks">Best Picks 2020</h2>

```

main.html, рядок 267

```html

<h3 class="h4 mb-0">Bags Collection</h3>

```

Заголовки передають структуру: h1 сторінки, h2 розділів і категорій, h3 колекцій та товарів.

Результат: У DOM один h1, переходів до рівня глибшого більш ніж на один немає. Структуру збережено в журналі й дереві доступності.

## 2.5. Семантичні орієнтири

Навігація й футер були div; основної області main не було. Також бракувало закривального тегу футера.

### До

main.html, рядок 31

```html

        <div class="collapse navbar-collapse" id="navbarCollapse">

```

main.html, рядок 1155

```html

<div class="bg-dark bg-cover footer">

```

### Після

main.html, рядок 15

```html

<header>

```

main.html, рядок 30

```html

<nav aria-label="Main navigation" class="collapse navbar-collapse" id="navbarCollapse">

```

main.html, рядок 100

```html

<main id="main-content" tabindex="-1">

```

main.html, рядок 998

```html

<footer class="bg-dark bg-cover footer">

```

Один header об’єднує верхні блоки; nav має назву; main і footer дають точки швидкого переходу.

Результат: У браузері рівно один header, main і footer; nav має назву Main navigation. Axe region і landmark-one-main більше не повідомляють порушень.

## 2.6. Природний порядок фокусу

17 позитивних tabindex змушували Tab починати з посилань унизу сторінки.

### До

main.html, рядок 1192

```html

                    <div><a class="text-gray-300" tabindex="1" href="#">Contact Us</a></div>

```

### Після

main.html, рядок 1034

```html

<a class="text-gray-300" href="#">Contact Us</a>

```

Навігація йде за DOM зверху вниз; tabindex="-1" лише на main потрібний для skip link і не додає зупинки Tab.

Результат: 101 зупинка Tab на головній сторінці відповідає порядку інтерактивних елементів DOM. Позитивних tabindex немає; зворотний перехід Shift+Tab перевірено.

## 2.7. Контраст тексту та фокусу

Світлий акцент, перекреслені ціни й підзаголовки мали недостатній контраст. Числа на фото залежали від фону.

### До

assets/css/theme.css, рядок 2695

```css

.btn-primary {
	color: #fff;
	background-color: #ff6f61;
	border-color: #ff6f61
}

```

assets/css/theme.css, рядок 16337

```css

.text-gray-350 {
	color: #a6a6a6!important
}

```

### Після

assets/css/site.css, рядок 197

```css

.text-muted, .text-gray-350, .text-gray-400, .text-gray-500 { color: #595959 !important; }

```

assets/css/site.css, рядок 201

```css

.card-circle { background-color: #b53b32; }

```

assets/css/site.css, рядок 213

```css

.card-img-overlay p { background: #111; padding: .25rem .5rem; }

```

Збережено червоний акцент, але зроблено темнішим. Для чисел на фото додано непрозоре тло; для фокусу є виразна рамка.

Результат: Виміряно: акцент #ff6f61 на білому 2,73:1 → #b53b32 5,77:1; стара ціна 2,43:1 → 7,00:1; підзаголовок 3,19:1 → 7,00:1. Після змін axe color-contrast не має порушень; залишені ним непевні випадки розглянуто окремо.

## 2.8. Альтернативний текст зображень

Усі 32 img головної сторінки не мали alt; посилання з одним зображенням не мали доступної назви.

### До

main.html, рядок 409

```html

                                    <img class="card-img-top card-img-front" src="./assets/img/site/sandals.png"
                                         width="253" height="300">

```

### Після

main.html, рядок 362

```html

<img alt="Leather mid-heel Sandals" class="card-img-top card-img-front" height="300" src="./assets/img/site/sandals.png" width="253">

```

main.html, рядок 710

```html

<img alt="" class="img-fluid" height="73" src="./assets/img/site/smallsneakers.png" width="73">

```

Товарні фото отримали назви товарів, логотипи й способи оплати свої назви. Повторні мініатюри відгуків і декоративні фото мають alt="".

Результат: 32 із 32 зображень мають alt; усі локальні картинки завантажилися. Axe image-alt не виявляє порушень. Доцільність описів переглянуто за зображеннями й контекстом, озвучення не перевірено.

## 2.9. Семантика відгуків

Текст реального за змістом цитування й підпис покупця містилися у звичайних div.

### До

main.html, рядок 867

```html

                        <!-- Blockquote -->
                        <div class="mb-0">
                            <p class="text-muted">

```

### Після

main.html, рядок 743

```html

<!-- Blockquote -->
<figure class="mb-0">
<blockquote><p class="text-muted">

```

main.html, рядок 750

```html

<figcaption class="font-size-xs text-muted">

```

Три наявні відгуки позначено blockquote; ім’я й історична дата лишилися окремим figcaption у figure.

Результат: У DOM і дереві доступності є три blockquote. Тексти, імена та дати відгуків збережено з оригіналу.

## 2.10. Зрозумілі назви посилань і кнопок

Однакові Shop Now та іконки не давали зрозуміти призначення без зображення.

### До

main.html, рядок 306

```html

                            <a class="btn btn-link stretched-link text-reset" href="#">
                                Shop Now <i class="fe fe-arrow-right ml-2"></i>

```

### Після

main.html, рядок 269

```html

<a aria-label="Shop Now: Bags Collection" class="btn btn-link stretched-link text-reset" href="#">
                                Shop Now <i aria-hidden="true" class="fe fe-arrow-right ml-2"></i>

```

Shop Now отримали назву з колекцією; іконки навігації та 24 кнопки товарів мають назви дії й товару. Назви узгоджено з видимим текстом.

Результат: Axe link-name: 13 → 0 вузлів; button-name: 24 → 0. За посиланням Create account клавіша Enter відкриває form.html. Посилання-заглушки не видаються за робочі сторінки.

## 2.11. Групування посилань футера

Пов’язані посилання були окремими div без структури списку.

### До

main.html, рядок 1192

```html

                    <div><a class="text-gray-300" tabindex="1" href="#">Contact Us</a></div>
                    <div><a class="text-gray-300" tabindex="2" href="#">FAQs</a></div>

```

### Після

main.html, рядок 1034

```html

<ul><li><a class="text-gray-300" href="#">Contact Us</a></li><li><a class="text-gray-300" href="#">FAQs</a></li><li><a class="text-gray-300" href="#">Size Guide</a></li><li><a class="text-gray-300" href="#">Shipping & Returns</a></li></ul></div>

```

Support, Shop, Company і Contact мають чотири ul; разом збережено 17 посилань у вихідному порядку.

Результат: У футері чотири списки з 4, 4, 5 і 4 пунктів. Порядок DOM та проходження Tab підтверджено.

## 3.1. Мітки полів форми

Title, First Name, Last Name й Email Address мали непов’язані label. Поле підписки внизу спиралося на placeholder.

### До

form.html, рядок 141

```html

            <label>First Name</label>
            <div class="form-group">
              <input type="text" id="first" class="form-control" autocomplete="off">

```

### Після

form.html, рядок 128

```html

<label for="first">First Name (required)</label>
<div class="form-group">
<input autocomplete="given-name" class="form-control" id="first" required="" type="text">

```

Кожне поле має пов’язану мітку через for/id. Для імен та email додано відповідні autocomplete. Поле email перевіряє формат.

Результат: Усі вісім полів форми облікового запису мають по одній мітці й належать account-form. Мітка нижньої підписки також пов’язана. Axe label і select-name: порушень немає.

## 3.2. Обов’язковість і перевірка введення

Обов’язковість не задавалася; кнопка Create Account була поза form і не запускала нативну перевірку.

### До

form.html, рядок 122

```html

          <div class="border">

```

form.html, рядок 127

```html

                <option value="? string: ?"></option>

```

### Після

form.html, рядок 111

```html

<form aria-describedby="account-help" class="border" id="account-form" onsubmit="event.preventDefault()">

```

form.html, рядок 114

```html

<select autocomplete="honorific-prefix" class="custom-select" id="title" required="">

```

form.html, рядок 115

```html

<option value="">Choose a title</option>

```

Контейнер замінено на form. Чотири основні поля мають required і видиме (required); signup і shipping залишено optional. Порожнє значення select тепер справді порожнє.

Результат: Порожня форма не надсилається й фокусує Title. Після вибору Title фокус переходить до першого незаповненого імені; некоректний email викликає typeMismatch. Заповнена форма без optional-полів проходить валідацію й породжує submit; серверної реєстрації у вихідному проєкті немає.

## 3.3. Групування доставки

Три радіокнопки мали спільне name, але не мали семантичної назви групи.

### До

form.html, рядок 161

```html

            <p>Please indicate your shipping option preferences by selecting the relevant option</p>

            <div class=" form-group">

```

### Після

form.html, рядок 145

```html

<fieldset class="form-group"><legend>Shipping option (optional)</legend>

```

fieldset і legend Shipping option (optional) пояснюють спільне призначення. Нативні radio збережено.

Результат: Space вибирає Standard; ArrowDown перемикає на Priority; ArrowRight на 3 workings days; ArrowLeft повертає Priority. У дереві доступності група має назву Shipping option (optional).
