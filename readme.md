# Критерии хорошей верстки

Обязательные и необязательные критерии оценки вёрстки.


## 1. Разметка


### 1.1. Разметка проходит валидацию на [validator.w3.org/nu](https://validator.w3.org/nu/)

Проверяются все сверстанные страницы.

Проверке подвергается и логическая структура документа (флаг `Show Outline` при проверке). Допустим «безымянный» блок для `<nav>`.


### 1.2. Отсутствуют грубые ошибки

Примеры грубых ошибок: ссылки не являются ссылками, `<br><br>` вместо параграфов.

Примеры негрубых (условно-допустимых) ошибок: `<div>` вместо `<section>`, `<header>` или `<article>`, отсутствие списка в одноуровневой навигации.


### 1.3. Разметка работоспособна без стилей и скриптов

Страница без стилей и скриптов, будучи открыта в браузере, выглядит логично и работает:

- видна чёткая иерархия блоков (заголовки),
- не видны элементы, ненужные или не работающие без стилей и скриптов (пример: бургер главного меню),
- интерактивные элементы (ссылки, в т.ч. якорные, формы) видны и работоспособны.

**Исключение:** страницы, работоспособность которых невозможна без стилей/скриптов.


### 1.4. Использована методология БЭМ, отсутствуют типовые ошибки

CSS-классы, использованные в разметке, написаны по БЭМ ([Описание методологии](https://ru.bem.info/methodology/quick-start/)). Предпочтительным является использование [диалекта Two Dashes](https://ru.bem.info/methodology/naming-convention/#Стиль-two-dashes) (`__` как разделитель для элемента и `--` как разделитель для модификатора).

Типовые ошибки:

- повторение разделителя более одного раза в одном классе: `block__element__element` или `block--modifier--modifier`,
- класс-модификатор без класса, который он модифицирует: `<div class="block--modifier">` или `<div class="btn  toggler--red">`.


## 2. Стилизация

### 2.1. Отклонения от макета минимальны

На прорисованных ширинах вертикальные отклонения не должны превышать 10px (но не более 5% для малых высот), горизонтальные не должны превышать 5px. Ширины блоков, формирующих раскладку блоков на странице должны точно совпадать с макетом.

Недопустимы отклонения по параметрам текста, цветам, контентным изображениям.

### 2.2. Шрифты заданы правильно

При указании названия шрифта в `font-family` должны быть указаны альтернативные семейства и тип семейства.


### 2.3. Отсутствуют «CSS-заплатки»

В стилях не должно быть `!important`.

На блоках раскладки не должно быть `overflow[-x||-y]: hidden;` (исключение: в дизайне есть горизонтальный скролл).


### 2.4. Фрагменты страницы выдерживают переполнение и недополнение

Простые фрагменты верстки должны выдерживать переполнение текстом (увеличение габаритов и/или сокрытие части длинного текста).

Фрагменты, содержащие потоковые блоки (пример: блок каталога товаров, содержащий поток вложенных блоков с товарами), должны выдерживать переполнение и недополнение потоковыми блоками.

Вставка в разметку контентных изображений с размерами, отличающимися от представленных в макете, не должно ломать страницу.


## 3. Дополнительные файлы

### 3.1. Минимум подключенных файлов

К странице должны быть подключены 1 CSS-файл и не более 3 синхронно подгружаемых JS-файлов.

CSS-файл должен быть подключен в секции `<head>`. JS-файлы должны быть подключены перед `</body>`.


### 3.2. Шрифты подключены в нужных форматах

Необходимые форматы: `woff`, `woff2`.


### 3.3. Растровые изображения оптимизированы

Растровые изображения должны быть оптимизированы, но не должны иметь видимых отличий от макета.


### 3.4. Векторные изображения не содержат растра

Внутри используемых SVG не должно встречаться растровых изображений.

**Исключение:** использование SVG для каких-либо сложных эффектов на растровых изображениях.


## 4. Оптимизация

### 4.1. Использованы доступные семантические возможности

TODO: label и прочее про формы, таблицы, типографика?


## 5. Автоматизация

Сжимать картинки не при каждом билде.

Оптимизировать оптимизацию )))


## 6. Адаптивность




## 7. Разное

Кроссбраузерность

нет транслита и camelCase.

спрайты



## Необязательные критерии

Разделение стилей обертки и содержимого.

контроль включенного JS

Спорные текстовые элементы — любой тег.

Обертки вокруг текст. фрагментов, выводимых из CMS.

контроль подгрузки шрифтов
