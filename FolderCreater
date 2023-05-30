import os
import tkinter as tk
from tkinter import filedialog

root = tk.Tk()
root.withdraw()

folder_path = filedialog.askdirectory()

if folder_path:
    folder_names = input("Введи имена папок через запятую: ").split(", ")

for folder_name in folder_names:
    full_path = os.path.join(folder_path, folder_name)
        
    if not os.path.exists(full_path):
        os.makedirs(full_path)

print("Папки успешно созданы.")
