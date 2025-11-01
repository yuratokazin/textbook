# 4.1 Семантические теги: header, footer, main, section, article и др.

Семантические теги — это важный шаг в развитии HTML, который делает код понятным не только для браузера, но и для разработчиков, поисковых систем и вспомогательных технологий.

---

### **Что такое семантические теги и зачем они нужны?**

**Семантические теги** — это HTML-теги, которые несут смысловую нагрузку и описывают назначение контента, а не только его внешний вид.

**Преимущества семантической верстки:**

- ✅ **Доступность (Accessibility):** Скринридеры понимают структуру страницы
- ✅ **SEO:** Поисковые системы лучше индексируют контент
- ✅ **Читаемость кода:** Разработчики быстрее понимают структуру
- ✅ **Поддержка:** Упрощает стилизацию и поддержку проекта

---

### **Основные семантические теги**

#### **1. `<header>` — Шапка**
Используется для вводной информации или навигации.

**Где используется:**
- В начале страницы (шапка сайта)
- В начале секции `<article>` или `<section>`

```html
<header>
    <img src="logo.png" alt="Логотип компании">
    <nav>
        <a href="/">Главная</a>
        <a href="/about">О нас</a>
        <a href="/contact">Контакты</a>
    </nav>
</header>
```

#### **2. `<nav>` — Навигация**
Представляет блок навигационных ссылок.

```html
<nav>
    <ul>
        <li><a href="#home">Главная</a></li>
        <li><a href="#services">Услуги</a></li>
        <li><a href="#contact">Контакты</a></li>
    </ul>
</nav>

<!-- НЕ используйте nav для всех групп ссылок! -->
<!-- Только для основных блоков навигации -->
```

#### **3. `<main>` — Основное содержание**
Главный контент страницы. **На странице должен быть только один `<main>`!**

```html
<main>
    <h1>Главный заголовок страницы</h1>
    <p>Основной контент страницы...</p>
</main>
```

#### **4. `<article>` — Независимый контент**
Представляет самостоятельный, независимый фрагмент контента.

**Примеры использования:**
- Пост в блоге
- Новость
- Комментарий
- Виджет

```html
<article>
    <header>
        <h2>Заголовок статьи</h2>
        <p>Опубликовано: <time datetime="2024-01-15">15 января 2024</time></p>
    </header>
    <p>Содержание статьи...</p>
    <footer>
        <p>Автор: Иван Иванов</p>
    </footer>
</article>
```

#### **5. `<section>` — Секция/раздел**
Группирует тематический контент. Обычно имеет заголовок.

```html
<section>
    <h2>Наши услуги</h2>
    <p>Мы предлагаем широкий спектр услуг...</p>
</section>

<section>
    <h2>О компании</h2>
    <p>Наша компания работает с 2010 года...</p>
</section>
```

#### **6. `<aside>` — Боковая панель**
Контент, косвенно связанный с основным содержимым.

```html
<aside>
    <h3>Популярные статьи</h3>
    <ul>
        <li><a href="#">Статья 1</a></li>
        <li><a href="#">Статья 2</a></li>
    </ul>
</aside>
```

#### **7. `<footer>` — Подвал**
Завершающая часть страницы или секции.

```html
<footer>
    <p>&copy; 2024 Моя компания. Все права защищены.</p>
    <address>Контакты: example@mail.com</address>
</footer>
```

---

### **Разница между `<article>` и `<section>`**

| `<article>` | `<section>` |
|-------------|-------------|
| Независимый, самодостаточный контент | Тематическая группировка контента |
| Может иметь свою структуру (header, footer) | Обычно часть更大的 целого |
| Имеет смысл при изолированном использовании | Не имеет самостоятельного смысла |

**Правило:** Если контент можно использовать независимо (например, в RSS), используйте `<article>`. Если просто группируете相关内容 — `<section>`.

---

### **Дополнительные семантические теги**

#### **`<figure>` и `<figcaption>`**
Для иллюстраций, диаграмм, фото с подписями.

```html
<figure>
    <img src="chart.png" alt="График продаж за 2024 год">
    <figcaption>Рис. 1 - Динамика продаж по месяцам</figcaption>
</figure>
```

#### **`<time>`**
Для обозначения даты и времени.

```html
<p>Событие состоится <time datetime="2024-02-20T19:00">20 февраля в 19:00</time></p>
```

#### **`<mark>`**
Для выделения текста (как маркером).

```html
<p>Важно: <mark>не забудьте сохранить изменения</mark> перед выходом.</p>
```

#### **`<address>`**
Для контактной информации.

```html
<address>
    Автор: <a href="mailto:ivan@example.com">Иван Иванов</a><br>
    Телефон: +7 (123) 456-78-90
</address>
```

---

### **Полный пример семантической верстки**

```html
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Блог о веб-разработке</title>
</head>
<body>
    <!-- Шапка сайта -->
    <header>
        <img src="logo.svg" alt="Логотип блога" width="150">
        <nav aria-label="Основная навигация">
            <ul>
                <li><a href="/">Главная</a></li>
                <li><a href="/articles">Статьи</a></li>
                <li><a href="/about">Обо мне</a></li>
                <li><a href="/contact">Контакты</a></li>
            </ul>
        </nav>
    </header>

    <!-- Основной контент -->
    <main>
        <!-- Статья -->
        <article>
            <header>
                <h1>Семантическая верстка: полное руководство</h1>
                <p>
                    Опубликовано: 
                    <time datetime="2024-01-15">15 января 2024</time>
                    | Автор: Иван Иванов
                </p>
            </header>

            <section>
                <h2>Что такое семантическая верстка?</h2>
                <p>Семантическая верстка — это подход к созданию HTML-разметки...</p>
            </section>

            <section>
                <h2>Преимущества семантической верстки</h2>
                <p>Использование семантических тегов имеет множество преимуществ...</p>
                
                <figure>
                    <img src="semantic-structure.png" alt="Структура семантической верстки">
                    <figcaption>Пример правильной семантической структуры</figcaption>
                </figure>
            </section>

            <footer>
                <p>Теги: <mark>HTML</mark>, <mark>семантика</mark>, <mark>верстка</mark></p>
            </footer>
        </article>

        <!-- Боковая панель -->
        <aside>
            <section>
                <h3>Популярные статьи</h3>
                <ul>
                    <li><a href="#">CSS Grid для начинающих</a></li>
                    <li><a href="#">JavaScript ES6+ особенности</a></li>
                </ul>
            </section>
        </aside>
    </main>

    <!-- Подвал сайта -->
    <footer>
        <p>&copy; 2024 Блог о веб-разработке. Все права защищены.</p>
        <address>
            Контакты: 
            <a href="mailto:hello@example.com">hello@example.com</a>
        </address>
        <nav aria-label="Социальные сети">
            <a href="#">Twitter</a>
            <a href="#">GitHub</a>
            <a href="#">LinkedIn</a>
        </nav>
    </footer>
</body>
</html>
```

---

### **Иерархия и вложенность**

**Правильная структура:**
```html
<body>
    <header>...</header>
    <main>
        <article>
            <header>...</header>
            <section>...</section>
            <section>...</section>
            <footer>...</footer>
        </article>
    </main>
    <footer>...</footer>
</body>
```

**Неправильная структура:**
```html
<body>
    <div id="header">...</div>
    <div class="content">
        <div class="post">
            <div class="post-header">...</div>
            <div class="text">...</div>
        </div>
    </div>
    <div id="footer">...</div>
</body>
```

---

### **Проверка семантической структуры**

**Валидаторы:**
- W3C Validator
- Lighthouse (вкладка Accessibility)

**Доступность:**
- Используйте ARIA-роли только когда семантических тегов недостаточно
- Проверяйте с помощью скринридеров (NVDA, VoiceOver)

**Ключевые принципы:**
1. Используйте теги по назначению
2. Соблюдайте иерархию заголовков (`h1`-`h6`)
3. Один `<main>` на страницу
4. `<header>` и `<footer>` можно использовать многократно в разных секциях
5. Всегда добавляйте текстовые альтернативы для изображений

Семантическая верстка — это не просто "правильно", это профессиональный подход, который делает веб лучше для всех пользователей! 🌐

---
---

# 4.2 Практическая верстка семантического макета.

Давайте создадим практический пример семантической верстки — сверстаем макет блога с использованием всех изученных тегов.

---

### **Задача: Сверстать семантичный макет блога**

**Требования:**
- Использовать семантические теги
- Соблюдать иерархию заголовков
- Обеспечить доступность
- Создать адаптивную структуру

---

### **HTML-структура**

```html
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TechBlog - Блог о технологиях и разработке</title>
    <style>
        /* Базовые стили для наглядности */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background: #f4f4f4;
        }

        /* Стили для семантических тегов */
        header, footer, main, section, article, aside, nav {
            padding: 20px;
            margin: 10px 0;
        }

        header { background: #2c3e50; color: white; }
        footer { background: #34495e; color: white; text-align: center; }
        main { background: white; }
        nav { background: #3498db; }
        article { background: #ecf0f1; margin: 15px 0; }
        section { background: #fff; border-left: 4px solid #3498db; }
        aside { background: #bdc3c7; }
        
        /* CSS Grid для layout */
        .container {
            display: grid;
            grid-template-areas: 
                "header header"
                "nav nav"
                "main aside"
                "footer footer";
            grid-template-columns: 3fr 1fr;
            gap: 20px;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        header { grid-area: header; }
        nav { grid-area: nav; }
        main { grid-area: main; }
        aside { grid-area: aside; }
        footer { grid-area: footer; }

        /* Адаптивность */
        @media (max-width: 768px) {
            .container {
                grid-template-areas: 
                    "header"
                    "nav"
                    "main"
                    "aside"
                    "footer";
                grid-template-columns: 1fr;
            }
        }

        /* Дополнительные стили для красоты */
        .logo { font-size: 24px; font-weight: bold; }
        .nav-links { list-style: none; display: flex; gap: 20px; }
        .nav-links a { color: white; text-decoration: none; }
        .article-meta { color: #7f8c8d; font-size: 14px; margin: 10px 0; }
        .tags { margin-top: 15px; }
        .tag { background: #3498db; color: white; padding: 2px 8px; border-radius: 3px; font-size: 12px; }
    </style>
</head>
<body>
    <div class="container">
        <!-- Шапка сайта -->
        <header>
            <div class="logo">TechBlog</div>
            <p>Блог о веб-разработке, технологиях и IT-инновациях</p>
        </header>

        <!-- Основная навигация -->
        <nav aria-label="Основное меню">
            <ul class="nav-links">
                <li><a href="#home">Главная</a></li>
                <li><a href="#articles">Статьи</a></li>
                <li><a href="#tutorials">Уроки</a></li>
                <li><a href="#news">Новости</a></li>
                <li><a href="#about">О проекте</a></li>
                <li><a href="#contact">Контакты</a></li>
            </ul>
        </nav>

        <!-- Основной контент -->
        <main>
            <!-- Главная статья -->
            <article id="main-article">
                <header>
                    <h1>Семантическая верстка: почему это важно в 2024 году</h1>
                    <div class="article-meta">
                        <time datetime="2024-01-20">20 января 2024</time> | 
                        Автор: <span>Анна Петрова</span> | 
                        Время чтения: 5 минут
                    </div>
                </header>

                <section>
                    <h2>Что такое семантическая верстка?</h2>
                    <p>Семантическая верстка — это подход к созданию HTML-разметки, при котором теги выбираются в соответствии с смысловым значением контента, а не только его внешним видом.</p>
                    
                    <figure>
                        <img src="https://via.placeholder.com/800x400" alt="Сравнение семантической и несемантической верстки" style="width: 100%; max-width: 800px; height: auto;">
                        <figcaption>Рис. 1 - Разница между семантической и обычной версткой</figcaption>
                    </figure>
                </section>

                <section>
                    <h2>Ключевые преимущества</h2>
                    <h3>Для доступности</h3>
                    <p>Скринридеры и другие вспомогательные технологии лучше понимают структуру страницы, что улучшает опыт для пользователей с ограниченными возможностями.</p>
                    
                    <h3>Для SEO</h3>
                    <p>Поисковые системы отдают предпочтение хорошо структурированным страницам с четкой семантикой.</p>
                    
                    <h3>Для разработчиков</h3>
                    <p>Код становится более читаемым и поддерживаемым. Новые разработчики быстрее понимают структуру проекта.</p>
                </section>

                <section>
                    <h2>Основные семантические теги</h2>
                    <ul>
                        <li><strong>&lt;header&gt;</strong> - шапка сайта или раздела</li>
                        <li><strong>&lt;nav&gt;</strong> - блок навигации</li>
                        <li><strong>&lt;main&gt;</strong> - основной контент страницы</li>
                        <li><strong>&lt;article&gt;</strong> - независимый контент</li>
                        <li><strong>&lt;section&gt;</strong> - тематическая секция</li>
                        <li><strong>&lt;aside&gt;</strong> - дополнительный контент</li>
                        <li><strong>&lt;footer&gt;</strong> - подвал сайта или раздела</li>
                    </ul>
                </section>

                <footer>
                    <div class="tags">
                        <span class="tag">HTML5</span>
                        <span class="tag">Семантика</span>
                        <span class="tag">Верстка</span>
                        <span class="tag">Доступность</span>
                    </div>
                </footer>
            </article>

            <!-- Дополнительные статьи -->
            <section aria-labelledby="related-articles">
                <h2 id="related-articles">Читайте также</h2>
                
                <article>
                    <h3>CSS Grid vs Flexbox: когда что использовать</h3>
                    <p>Подробное сравнение двух современных CSS-технологий для создания макетов.</p>
                    <div class="article-meta">
                        <time datetime="2024-01-18">18 января 2024</time>
                    </div>
                </article>

                <article>
                    <h3>JavaScript ES2024: новые возможности</h3>
                    <p>Обзор самых интересных нововведений в стандарте JavaScript.</p>
                    <div class="article-meta">
                        <time datetime="2024-01-15">15 января 2024</time>
                    </div>
                </article>
            </section>
        </main>

        <!-- Боковая панель -->
        <aside>
            <section aria-labelledby="about-author">
                <h2 id="about-author">Об авторе</h2>
                <p>Анна Петрова - фронтенд-разработчик с 5-летним опытом. Специализируется на создании доступных и производительных веб-приложений.</p>
            </section>

            <section aria-labelledby="popular-tags">
                <h2 id="popular-tags">Популярные теги</h2>
                <div class="tags">
                    <span class="tag">JavaScript</span>
                    <span class="tag">React</span>
                    <span class="tag">CSS</span>
                    <span class="tag">HTML5</span>
                    <span class="tag">Vue</span>
                    <span class="tag">TypeScript</span>
                </div>
            </section>

            <section aria-labelledby="newsletter">
                <h2 id="newsletter">Рассылка</h2>
                <form>
                    <label for="email">Подпишитесь на обновления:</label>
                    <input type="email" id="email" name="email" placeholder="Ваш email" style="width: 100%; padding: 8px; margin: 5px 0;">
                    <button type="submit" style="width: 100%; padding: 10px; background: #3498db; color: white; border: none;">Подписаться</button>
                </form>
            </section>
        </aside>

        <!-- Подвал сайта -->
        <footer>
            <section aria-labelledby="site-links">
                <h2 id="site-links" style="display: none;">Ссылки сайта</h2>
                <nav aria-label="Дополнительная навигация">
                    <ul style="list-style: none; display: flex; justify-content: center; gap: 20px; flex-wrap: wrap;">
                        <li><a href="#privacy" style="color: white;">Политика конфиденциальности</a></li>
                        <li><a href="#terms" style="color: white;">Условия использования</a></li>
                        <li><a href="#sitemap" style="color: white;">Карта сайта</a></li>
                    </ul>
                </nav>
            </section>

            <section aria-labelledby="social-links">
                <h2 id="social-links" style="display: none;">Социальные сети</h2>
                <nav aria-label="Социальные сети">
                    <ul style="list-style: none; display: flex; justify-content: center; gap: 15px; margin: 15px 0;">
                        <li><a href="#" aria-label="Twitter" style="color: white;">Twitter</a></li>
                        <li><a href="#" aria-label="GitHub" style="color: white;">GitHub</a></li>
                        <li><a href="#" aria-label="LinkedIn" style="color: white;">LinkedIn</a></li>
                        <li><a href="#" aria-label="Telegram" style="color: white;">Telegram</a></li>
                    </ul>
                </nav>
            </section>

            <section>
                <p>&copy; 2024 TechBlog. Все права защищены.</p>
                <address>
                    Контакты: <a href="mailto:hello@techblog.ru" style="color: white;">hello@techblog.ru</a>
                </address>
            </section>
        </footer>
    </div>
</body>
</html>
```

---

### **Ключевые семантические особенности этого макета:**

#### **1. Правильная иерархия заголовков:**
```html
<h1>Семантическая верстка: почему это важно в 2024 году</h1>
<h2>Что такое семантическая верстка?</h2>
<h3>Для доступности</h3>
<h2>Читайте также</h2>
<h3>CSS Grid vs Flexbox: когда что использовать</h3>
```

#### **2. Использование ARIA-атрибутов для доступности:**
```html
<nav aria-label="Основное меню">
<section aria-labelledby="related-articles">
```

#### **3. Логическая структура контента:**
- `<header>` - шапка с логотипом и описанием
- `<nav>` - основное меню навигации
- `<main>` - весь основной контент
- `<article>` - каждая статья как независимая единица
- `<section>` - тематические разделы внутри статей
- `<aside>` - дополнительная информация (об авторе, теги, рассылка)
- `<footer>` - подвал с ссылками и контактами

#### **4. Семантические элементы для мета-информации:**
```html
<time datetime="2024-01-20">20 января 2024</time>
<address>Контакты: <a href="mailto:hello@techblog.ru">hello@techblog.ru</a></address>
```

#### **5. Адаптивная верстка с CSS Grid:**
```css
.container {
    display: grid;
    grid-template-areas: 
        "header header"
        "nav nav"
        "main aside"
        "footer footer";
}

@media (max-width: 768px) {
    .container {
        grid-template-areas: 
            "header"
            "nav"
            "main"
            "aside"
            "footer";
    }
}
```

---

### **Проверка семантичности:**

**Правильно:**
- Один `<main>` на странице
- Заголовки идут по порядку (`h1` → `h2` → `h3`)
- Каждый `<section>` и `<aside>` имеет заголовок
- Навигационные блоки помечены `<nav>`
- Используются `aria-label` и `aria-labelledby`

**Доступность:**
- Скринридеры понимают структуру страницы
- Формы имеют правильные `label`
- Все изображения имеют `alt` текст
- Цветовой контраст достаточен для чтения

**SEO-преимущества:**
- Поисковые системы видят четкую структуру контента
- Ключевые слова в семантических тегах
- Правильная иерархия заголовков

Такой подход к верстке делает сайт не только визуально привлекательным, но и функциональным, доступным и хорошо индексируемым в поисковых системах! 


