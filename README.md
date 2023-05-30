# FolderCreater
Скрипт для создания папок, по заданным именам с использованием стандартного графического дизайна.

Вот комментарии к каждой строке кода:

    import os
    import tkinter as tk
    from tkinter import filedialog
Импортируются модули os, tkinter и filedialog. Модуль os используется для работы с файловой системой, tkinter - для создания графического интерфейса, а filedialog - для открытия диалогового окна выбора папки.

    root = tk.Tk()
    root.withdraw()
Создается объект Tk() из модуля tkinter для создания главного окна. Затем метод withdraw() вызывается для скрытия этого окна. Это позволяет использовать только диалоговые окна без отображения основного окна.

    folder_path = filedialog.askdirectory()
Вызывается диалоговое окно для выбора папки с помощью filedialog.askdirectory(). Выбранный путь сохраняется в переменной folder_path.

    if folder_path:
        folder_names = input("Введи имена папок через запятую: ").split(", ")
Если был выбран путь folder_path (не пустая строка), то пользователю предлагается ввести имена папок через запятую. Введенные имена сохраняются в виде списка строк в переменной folder_names, разделяя каждое имя по запятой.

    for folder_name in folder_names:
        full_path = os.path.join(folder_path, folder_name)
        
    if not os.path.exists(full_path):
        os.makedirs(full_path)
Для каждого имени папки из списка folder_names создается полный путь full_path, объединяя путь к выбранной папке folder_path и текущее имя папки. Затем с помощью os.path.exists() проверяется, существует ли уже папка с таким путем. Если папки не существует, вызывается os.makedirs() для создания новой папки.

    print("Папки успешно созданы.")
Выводится сообщение о успешном создании папок.
