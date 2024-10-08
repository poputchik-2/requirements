# Общее предоставление об устройстве проекта и продукта
![image](https://github.com/user-attachments/assets/d373bef9-ebb6-487a-8532-29259755d6bb)

# Соглашение между GUI Team и Development Team

# Мониторинг и обработка ошибок
## JavaScript Team

## Flutter Team

# Storybook и скриншотные тесты
## JavaScript Team

## Flutter Team

# JavaScript инструменты

Посмотрел, NextJS, скорее всего, будет еще долго поддерживаться -- его бэкает немаленькая компания Versel, инструменты с ним работают (storybook, sentry), нативные возможности не ограничивает (если верить GPT4o). Считаю стоит его выбирать, поскольку хайповый инструмент, чтобы изучть :) Если на следующем созвоне почувствуем, что много на себя взяли, стопнемся на React-e (к которому вопросов нет, с ним все работают).

# Касательно и17и:
Помимо перевода текста, ещё есть локализация дат, календарей (к счастью, нам не грозит), денежный формат, RTL support и т.д.

Как правило, даты локализуются сами собой. Но если углубляться -- там очень запарная история, и нас она долгое время не будет касаться -- СНГ придерживается общего формата дат, насколько мне известно.

Хочется иметь единый i18n файл для мобилки и веба.
Это умеет делать данная штука:
https://poeditor.com/kb/open-source-localization

По ходу ресерча увидел, что некоторые жалуются на размер файла со строками и размер либ для л9и. Я не считаю это веской причиной делать самописное решение или N вариантов фронта на бэкэнде (тут конкретно про либу перевода, поскольку по ходу ресерча встречал такие рекомендации).

В целом, файлик (которому лучше быть единым) выглядит так:
```json
{
 "app.channel.plug": "Учебник предоставлен вам {blogName}"
}
```

React-intl звучит как решение.

https://github.com/marciobarrios/react-intl-number-format

Для nextJS есть такое https://www.thomasledoux.be/blog/minimal-dependency-free-translation-system-nextjs.

А что на Flutter использовать посмотрит Рома.

### Итог

1. Нужно создать файлы /l10n/ru.json со всем необходимым.
2. Использовать либо poeditor, либо самописный скрипт для трансформации в react-intl-читаемый формат и flutter'ный .arb формат.
3. Использовать готовые либы для локализации внутри приложений.
