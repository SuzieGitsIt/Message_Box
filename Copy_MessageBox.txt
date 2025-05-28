import tkinter as tk                                    # Tkinter's Tk class
from tkinter import messagebox                          # standard message box  

main = tk.Tk()
main.geometry('100x100+5+5')                                 # Set the geometry of the GUI (LxH+posX+posY)
main.title("Main Window")

def chk_btn1():
    if start_pos < 1 or final_pos > 25:
        print("Warning, value(s) for checkbox 1 is/are incorrect.")
        msg_box_bad1 = tk.messagebox.showwarning('Value Error Checkbox 1', 'The value entered in the entry box must be \nbetween 1 and 25.\nRetry to enter new values.\nCancel to exit without saving..', icon='warning', type='retrycancel')
        if msg_box_bad1== 'retry':
            print("Retry was selected, let's try again.")
            return      # stops the execution of this function.
        elif msg_box_bad1== 'cancel':
            print("Cancel was selected, quit the app.")
            quit()
        else:
            print("Return no matter what.")
            return
    else:
        print("Button 1 inputs are between 1 and 25, value accepted. Continuing.")

def chk_btn2():
    if start_pos < 26 or final_pos > 50:
        print("Warning, value(s) for checkbox 2 is/are incorrect.")
        msg_box_bad2 = tk.messagebox.showwarning('Value Error Checkbox 2', 'The value entered in the entry box must be \nbetween 26 and 50.\nRetry to enter new values.\nCancel to exit without saving.', icon='warning', type='retrycancel')
        if msg_box_bad2== 'retry':
            print("Retry was selected, let's try again.")
            return      # stops the execution of this function.
        elif msg_box_bad2== 'cancel':
            print("Cancel was selected, quit the app.")
            quit()
        else:
            print("Return no matter what.")
            return
    else:
        print("Button 2 inputs are between 26 and 50, value accepted. Continuing.")

def chk_btn3():
    if start_pos < 51 or final_pos > 75:
        print("Warning, value(s) for checkbox 3 is/are incorrect.")
        msg_box_bad3 = tk.messagebox.showwarning('Value Error Checkbox 3', 'The value entered in the entry box must be \nbetween 51 and 75.\nRetry to enter new values.\nCancel to exit without saving.', icon='warning', type='retrycancel')
        if msg_box_bad3== 'retry':
            print("Retry was selected, let's try again.")
            return     
        elif msg_box_bad3== 'cancel':
            print("Cancel was selected, quit the app.")
            quit()
        else:
            print("Return no matter what.")
            return
    else:
        print("Button 3 inputs are between 51 and 75, value accepted. Continuing.")
start_pos = 1
final_pos = 1
chk_btn1()
start_pos = 26
final_pos = 51
chk_btn2()
start_pos = 51
final_pos = 75
chk_btn3()

main.mainloop()
