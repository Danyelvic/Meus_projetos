import tkinter as tk
from tkinter import messagebox
import os

def desligar_pc_M(minutos):
    segundos = int(minutos * 60)
    os.system(f"shutdown /s /t {segundos}")
    if minutos > 0:
        messagebox.showinfo("Aviso", f"O PC vai desligar em {minutos} minutos!")

def desligar_pc_H(horas):
    segundos = int(horas * 3600)
    os.system(f"shutdown /s /t {segundos}")
    if horas > 0:
        messagebox.showinfo("Aviso", f"O PC vai desligar em {horas} horas!")

def reiniciar():
    os.system("shutdown /r")

def cancelar():
    os.system("shutdown /a")
    messagebox.showinfo("Aviso", "Desligamento cancelado")

janela = tk.Tk()
janela.title("Sitema OS")
janela.geometry("500x600")
tk.Label(janela, text="Funções comuns", font=("Arial", 20)).pack(pady=5)
tk.Button(janela, text="Desligar agora", width="30", font=("Arial", 16), command=lambda: desligar_pc_M(0)).pack(pady=5)
tk.Button(janela, text="Reiniciar agora", width="30", font=("Arial", 16), command=reiniciar).pack(pady=5)

tk.Label(janela, text="Cronometro por minutos", font=("Arial", 20)).pack(pady=5)
tk.Button(janela, text="Desligar 10 minutos", width="30", font=("Arial", 16), command=lambda: desligar_pc_M(10)).pack(pady=5)
tk.Button(janela, text="Desligar 20 minutos", width="30", font=("Arial", 16), command=lambda: desligar_pc_M(20)).pack(pady=5)
tk.Button(janela, text="Desligar 30 minutos", width="30", font=("Arial", 16), command=lambda: desligar_pc_M(30)).pack(pady=5)
tk.Button(janela, text="Desligar 40 minutos", width="30", font=("Arial", 16), command=lambda: desligar_pc_M(40)).pack(pady=5)
tk.Button(janela, text="Desligar 50 minutos", width="30", font=("Arial", 16), command=lambda: desligar_pc_M(50)).pack(pady=5)

tk.Label(janela, text="Cronometro por horas", font=("Arial", 20)).pack(pady=5)
tk.Button(janela, text="Desligar 1 hora", width="30", font=("Arial", 16), command=lambda: desligar_pc_H(1)).pack(pady=5)
tk.Button(janela, text="Desligar 1 h e 30 min", width="30", font=("Arial", 16), command=lambda: desligar_pc_H(1.5)).pack(pady=5)
tk.Button(janela, text="Desligar 2 horas", width="30", font=("Arial", 16), command=lambda: desligar_pc_H(2)).pack(pady=5)
tk.Button(janela, text="Desligar 2 h e 30 min", width="30", font=("Arial", 16), command=lambda: desligar_pc_H(2.5)).pack(pady=5)
tk.Button(janela, text="Desligar 3 horas", width="30", font=("Arial", 16), command=lambda: desligar_pc_H(3)).pack(pady=5)
tk.Button(janela, text="Desligar 3 h e 30 min", width="30", font=("Arial", 16), command=lambda: desligar_pc_H(3.5)).pack(pady=5)
tk.Button(janela, text="Desligar 4 horas", width="30", font=("Arial", 16), command=lambda: desligar_pc_H(4)).pack(pady=5)

tk.Label(janela, text="Cancelar qualquer tempo", font=("Arial", 20)).pack(pady=5)
tk.Button(janela, text="Cancelar tudo", width="30", font=("Arial", 16), command=lambda: cancelar()).pack(pady=5)

janela.mainloop()
