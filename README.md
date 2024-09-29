# Language-Translator-tool
#Language Translation Tool using python, with tkinter and googletrans library.

from tkinter import *
import tkinter as tk
from tkinter import ttk
from googletrans import Translator
from tkinter import messagebox

root = tk.Tk()
root.title ('Language Translater by Syed Mahmood Ejaz')
root.geometry ('1800x900')

frame1= Frame(root, width=1800, height=900, relief=RIDGE, borderwidth=5, bg ='skyblue')
frame1.place(x=0, y=0)

Label (root, text="LANGUAGE TRANSLATOR", font=("Helvetica 29 bold"),fg= "black", bg='skyblue').pack(pady=10) 

def translate():
    lang_1 = text_entry1.get("1.0", "end-1c")
    cl = choose_language.get()

    if lang_1=='':
        messagebox.showerror('Language Translator', 'Enter the text to translator!')
    else:
        text_entry2.delete(1.0,'end')
        translator = Translator()
        output = translator.translate(lang_1, dest=cl)
        text_entry2.insert('end', output.text)    


def clear():
    text_entry1.delete(1.0, 'end')
    text_entry2.delete(1.0, 'end')

a= tk.StringVar()

auto_select = ttk.Combobox(frame1, width=27, textvariable=a, state='randomly', font=('verdana', 15, 'bold'))

auto_select['values'] = (
                            'Auto Select',
                                )

auto_select.place(x=295, y=160)
auto_select.current(0)

l= tk.StringVar()
choose_language= ttk.Combobox(frame1, width=27, textvariable=1, state='randomly', font=('verdana', 15, 'bold'))

choose_language['values'] = (
                "Afrikaans",
                "Albanian",
                "Amharic",
                "Arabic",
                "Armenian",
                "Basque",
                "Bengali",
                "Byelorussian",
                "Burmese",
                "Bulgarian",
                "Catalan",
                "Czech",
                "Chinese",
                "Croatian",
                "Danish",
                "Dari",
                "Dzongkha",
                "Dutch",
                "English",
                "Esperanto",
                "Estonian",
                "Faroese",
                "Farsi",
                "Finnish",
                "French",
                "Gaelic",
                "Galician",
                "German",
                "Greek",
                "Hebrew",
                "Hindi",
                "Hungarian",
                "Icelandic",
                "Indonesian",
                "Inuktitut (Eskimo)",
                "Italian",
                "Japanese",
                "Khmer",
                "Korean",
                "Kurdish",
                "Laotian",
                "Latvian",
                "Lappish",
                "Lithuanian",
                "Macedonian",
                "Malay",
                "Maltese",
                "Nepali",
                "Norwegian",
                "Pashto",
                "Polish",
                "Portuguese",
                "Romanian",
                "Russian",
                "Scots",
                "Serbian",
                "Slovak",
                "Slovenian",
                "Somali",
                "Spanish",
                "Swedish",
                "Swahili",
                "Tagalog-Filipino",
                "Tajik",
                "Tamil",
                "Thai",
                "Tibetan",
                "Tigrinya",
                "Tongan",
                "Turkish",
                "Turkmen",
                "Ukrainian",
                "Urdu",
                "Uzbek",
                      )

choose_language.place(x=890, y=160)
choose_language.current(0)

text_entry1 = Text(frame1,width=29, height=15, borderwidth=5, relief=RIDGE, font=('verdana', 15))
text_entry1.place(x=300, y=200)

text_entry2 = Text(frame1, width=29, height=15, borderwidth=5, relief=RIDGE, font=('verdana', 15))
text_entry2.place(x=900, y=200)

btn1= Button(frame1, command=translate, text="Translate", relief=RAISED, borderwidth=4, font=('verdana', 15, 'bold'), bg='grey', fg="white", cursor="hand2")
btn1.place(x=675, y=610)

btn2= Button(frame1, command=clear, text="Clear", relief=RAISED, borderwidth=4, font=('verdana', 15, 'bold'), bg='grey', fg="white", cursor="hand2")
btn2.place(x=825, y=610)

root.mainloop()       
