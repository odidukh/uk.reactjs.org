---
id: faq-structure
title: Структура файлів
permalink: docs/faq-structure.html
layout: docs
category: FAQ
---

### Чи існують рекомендації по структуруванню React-проектів? {#is-there-a-recommended-way-to-structure-react-projects}

Немає одностайної думки. Однак є кілька популярних підходів, які ви можете розглянути.

#### Групування по функціональності або маршруту {#grouping-by-features-or-routes}

Один з популярних підходів — це розміщення файлів CSS, JS і тестів у папках, згрупованих за функціональністю або маршруту.

```
common/
  Avatar.js
  Avatar.css
  APIUtils.js
  APIUtils.test.js
feed/
  index.js
  Feed.js
  Feed.css
  FeedStory.js
  FeedStory.test.js
  FeedAPI.js
profile/
  index.js
  Profile.js
  ProfileHeader.js
  ProfileHeader.css
  ProfileAPI.js
```

Визначення «функціональність» не є універсальним, тому вибір рівня деталізації залишається за вами. Якщо у вас не виходить скласти список папок верхнього рівня, ви можете запитати у користувачів вашого продукту з яких основних частин він складається і взяти модель мислення користувачів за зразок.

#### Групування по типу файла {#grouping-by-file-type}

Іншим популярним способом структурування проектів є груповання схожих файлів, наприклад:

```
api/
  APIUtils.js
  APIUtils.test.js
  ProfileAPI.js
  UserAPI.js
components/
  Avatar.js
  Avatar.css
  Feed.js
  Feed.css
  FeedStory.js
  FeedStory.test.js
  Profile.js
  ProfileHeader.js
  ProfileHeader.css
```

Деякі розробники вважають за краще йти ще далі і розміщувати компоненти в різні папки в залежності від їх ролі в додатку. Наприклад, методологія розробки [Atomic Design](http://bradfrost.com/blog/post/atomic-web-design/) побудована на цьому принципі. Пам'ятайте, що дані методології слід розглядати як корисні приклади, а не як строгі правила.

#### Уникайте надмірної вкладеності{#avoid-too-much-nesting}

Проблем, пов'язаних з надмірною вкладеністю папок у JavaScript-проектах, може виникнути досить багато.  Одна з них — це складність контролю щодо імпорту або поновлення цих імпортів при переміщенні файлів. Якщо у вас немає вагомих підстав використовувати глибоку вкладеність папок, подумайте про те, щоб обмежити себе максимум трьома або чотирма рівнями вкладення у межах одного проекта. Звісно, це всього лише рекомендація і вона може бути не актуальна для вашого проекту.

#### Не перестарайтеся {#dont-overthink-it}

Якщо ви тільки починаєте проект, [не витрачайте більше 5 хвилин](https://en.wikipedia.org/wiki/Analysis_paralysis) на вибір структури проекту. Виберіть будь-який з перерахованих вище підходів (або придумайте свій власний) і почніть писати код! Є велика ймовірність, що ви повернетеся до переосмислення структури проекту після написання певної кількості коду.

Якщо ви відчуваєте що остаточно застрягли, починайте з однієї папки. Згодом, коли вона стане занадто великою, вам захочеться відокремити деякі файли від інших. На той час у вас буде достатньо знань, щоб визначити, які файли ви редагуєте разом найчастіше. Як правило, файли, які часто змінюються разом, слід тримати ближче один до одного. Цей принцип називається «спільне розміщення».

На практиці проекти часто використовують поєднання декількох вищезгаданих підходів. Тому вибір «правильного» підходу на самому початку проекту не надто важливий.
