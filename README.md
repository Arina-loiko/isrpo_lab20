# Лабораторная работа №20 - Работа с DOM и событиями в JavaScript

**ФИО:** Лойко Арина Станиславна
**Группа:** ИСП-232
**Дата:** 16.02.2026

## Описание (что изучили)

- Что такое DOM и как он устроен
- Как искать элементы на странице через getElementById и querySelector
- Как менять текст и стили элементов через JS
- Как работать с событиями - клики, ввод текста, отправка формы
- Как получать данные из полей формы и валидировать их
- Как динамически создавать и удалять элементы на странице
- Что такое делегирование событий и зачем оно нужно

## Структура проекта

```
isrpo_lab20/
├── index.html            - основная страница (шаги 1-9)
├── main.js               - JS для основной страницы
├── style.css             - стили
├── dynamicElements.html  - страница с динамическим списком (шаг 10)
├── dynamicElements.js    - JS для динамических элементов
├── img/                  - скриншоты к каждому шагу
└── README.md
```

## Сравнение с C# (WinForms/WPF)

| Концепция | C# (WinForms) | JavaScript (DOM) |
|---|---|---|
| Найти элемент | `Button myButton = this.Controls["myButton"]` | `const myButton = document.getElementById("myButton")` |
| Изменить текст | `label1.Text = "Новый текст"` | `label.textContent = "Новый текст"` |
| Добавить обработчик | `button1.Click += HandleClick` | `button.addEventListener("click", handleClick)` |
| Создать элемент | `Button btn = new Button()` | `const btn = document.createElement("button")` |
| Добавить в контейнер | `panel1.Controls.Add(btn)` | `panel.appendChild(btn)` |
| Скрыть элемент | `button1.Visible = false` | `button.style.display = "none"` |

**Events в JS = События в C#**

C# (WinForms):
```csharp
private void Button1_Click(object sender, EventArgs e)
{
  label1.Text = "Нажато!";
}
```

JavaScript (DOM):
```js
button.addEventListener("click", (e) => {
  label.textContent = "Нажато!";
});
```

**Валидация формы**

C# (WinForms):
```csharp
private void SubmitButton_Click(object sender, EventArgs e)
{
  if (string.IsNullOrEmpty(nameTextBox.Text))
  {
    MessageBox.Show("Введите имя!");
    return;
  }
}
```

JavaScript (DOM):
```js
form.addEventListener("submit", (e) => {
  e.preventDefault();
  if (!nameInput.value.trim()) {
    alert("Введите имя!");
    return;
  }
});
```

### Главные отличия

| Аспект | C# WinForms | JavaScript DOM |
|---|---|---|
| Компиляция | Да | Нет (интерпретация) |
| Типизация | Строгая | Динамическая |
| Ошибки | Во время компиляции | Во время выполнения |
| UI-дизайнер | Есть (визуальный) | Нет (только код) |
| Платформа | Windows | Любой браузер |

**Преимущества DOM перед WinForms:**
- Кроссплатформенность (работает везде)
- Не нужна установка приложения
- Легко обновлять

**Преимущества WinForms перед DOM:**
- Визуальный дизайнер (drag and drop)
- Ошибки на этапе компиляции
- Интеграция с Windows API

**Вывод:** DOM и WinForms решают схожие задачи, но разными подходами
