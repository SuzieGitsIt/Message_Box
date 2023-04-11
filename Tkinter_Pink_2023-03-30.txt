# File:     Tkinter_Pink_2023-03-30
# Version:  0.0.01
# Author:   Susan Haynes

from enum import global_flag_repr
from functools import partial

import tkinter as tk                                    # Tkinter's Tk class
import tkinter.ttk as ttk                               # Tkinter's Tkk class
import datetime as dt
import time
import random

from PIL import ImageTk, Image
from tkinter import messagebox

GUI = tk.Tk()
GUI.title("LAL Measurement")
GUI.geometry("1000x700")                                # Set the geometry of Tkinter frame
GUI.configure(bg = 'white')                             # Set background color
GUI.option_add("*Font", "Helvetica 12 bold")            # set the font and size for entire gui
GUI.option_add("*fg", "black")                          # set the text color, hex works too "#FFFFFF"
GUI.option_add("*bg", "white")                          # set the background to white

def resize_image(event):
    new_width = event.width
    new_height = event.height
    background_image = copy_of_image.resize((new_width, new_height))
    bkgnd_img = ImageTk.PhotoImage(background_image)
    lbl_photo.config(image = bkgnd_img)
    lbl_photo.background_image = bkgnd_img #avoid garbage collection

background_image = Image.open(r"\\RXS-FS-02\userdocs\shaynes\My Documents\R&D - Software\Python\Tkinter_Pink_2023-03-30\LAL.png")
copy_of_image = background_image.copy()
bkgnd_img = ImageTk.PhotoImage(background_image)

lbl_photo = ttk.Label(GUI, image = bkgnd_img)
lbl_photo.bind('<Configure>', resize_image)
lbl_photo.pack(fill=tk.BOTH, expand = True)

################################################        RANDOM PINK BUTTON         ################################################   
colors = ['#FF69B4']

but_pink = tk.Button(GUI, text= "Click Me", bg= colors, width= 7).place(x=750,y=630)

# Must be at the end of the program in order for the application to run b/c windows is constantly updating
GUI.mainloop()  