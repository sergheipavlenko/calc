import tkinter as tk

# Функция для обработки нажатий кнопок
def button_click(value):
    current = entry.get()
    entry.delete(0, tk.END)
    entry.insert(0, current + value)

# Функция для очистки поля ввода
def clear():
    entry.delete(0, tk.END)

# Функция для выполнения расчета
def calculate():
    try:
        result = eval(entry.get())
        entry.delete(0, tk.END)
        entry.insert(0, str(result))
    except:
        entry.delete(0, tk.END)
        entry.insert(0, "Ошибка")

# Создание главного окна
root = tk.Tk()
root.title("Красивый калькулятор")

# Настройки интерфейса
root.configure(bg='#F0F0F0')  # Фоновый цвет окна
root.geometry("350x450")  # Размер окна

# Поле ввода
entry = tk.Entry(root, width=16, font=('Arial', 24), borderwidth=5, relief='flat', justify='right')
entry.grid(row=0, column=0, columnspan=4, padx=10, pady=20)

# Кнопки калькулятора
buttons = [
    ('7', 1, 0), ('8', 1, 1), ('9', 1, 2), ('/', 1, 3),
    ('4', 2, 0), ('5', 2, 1), ('6', 2, 2), ('*', 2, 3),
    ('1', 3, 0), ('2', 3, 1), ('3', 3, 2), ('-', 3, 3),
    ('0', 4, 0), ('.', 4, 1), ('+', 4, 2), ('=', 4, 3),
]

# Цвета кнопок
button_color = '#4CAF50'  # Зеленый
button_text_color = 'white'

# Создание кнопок с красивым стилем
for (text, row, col) in buttons:
    if text == '=':
        button = tk.Button(root, text=text, padx=20, pady=20, font=('Arial', 18), bg='#FF5722', fg='white', command=calculate)
    else:
        button = tk.Button(root, text=text, padx=20, pady=20, font=('Arial', 18), bg=button_color, fg=button_text_color, command=lambda t=text: button_click(t))
    button.grid(row=row, column=col, padx=5, pady=5, sticky="nsew")

# Кнопка для очистки поля
clear_button = tk.Button(root, text='C', padx=20, pady=20, font=('Arial', 18), bg='#F44336', fg='white', command=clear)
clear_button.grid(row=4, column=2, padx=5, pady=5, sticky="nsew")

# Настройка гибкой разметки
for i in range(5):
    root.grid_rowconfigure(i, weight=1)
    if i < 4:
        root.grid_columnconfigure(i, weight=1)

# Запуск основного цикла программы
root.mainloop()
