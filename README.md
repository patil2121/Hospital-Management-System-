# Hospital-Management-System-
import tkinter as tk
from tkinter import messagebox
import datetime as dt

root = tk.Tk()
root.geometry("900x677")
root.title("PRAVESH CLINIC, SHAHAPUR")
bg = tk.PhotoImage(file="C:/Users/athar/Downloads/Atharva Patil.png")
lbl1 = tk.Label(root, image=bg)
lbl1.place(x=0, y=0)

date = dt.datetime.now()
format_date = f"{date:%a, %b %d %Y}"
label = tk.Label(root, text=format_date, font=("Fraunces", 18 , ))
label.grid(row=0, column=0, padx=7, pady=7, ipady=7, ipadx=7)

txtf_var = tk.StringVar()
txtl_var = tk.StringVar()
txta_var = tk.StringVar()
txtb_var = tk.StringVar()
txtc_var = tk.StringVar()
txtd_var = tk.StringVar()


def submit():
    txtf1 = txtf_var.get()
    txtl1 = txtl_var.get()
    txta1 = txta_var.get()
    txtb1 = txtb_var.get()
    txtc1 = txtc_var.get()
    txtd1 = txtd_var.get()

    file = open(txtf1 + ".txt", "w")
    file.write("PRAVESH CLINIC, SHAHAPUR (Dr.PRAFULL R. CHAUDHARI) \n")
    file.write("\n")
    file.write("Name - ")
    file.write(txtf1 + "\n")
    file.write("Age - ")
    file.write(txtl1 + "\n")
    file.write("Address - ")
    file.write(txta1 + "\n")
    file.write("Mobile No.- ")
    file.write(txtb1 + "\n")
    file.write("Room No. - ")
    file.write(txtc1 + "\n")
    file.write("Medicine Given - ")
    file.write(txtd1 + "\n")
    file.close()

    messagebox.showinfo("Submit", "Data Submitted Sucessfully")

    txtf_var.set("")
    txtl_var.set("")
    txta_var.set("")
    txtb_var.set("")
    txtc_var.set("")
    txtd_var.set("")


lblh = tk.Label(root, text="PRAVESH CLINIC, SHAHAPUR", font="lucida 25 bold")
lblh.grid(row=0, column=1, pady=15, padx=15, ipady=15, ipadx=15)

lblf = tk.Label(root, text="Name of Patient - ", font="lucida 10 bold")
lbll = tk.Label(root, text="Age of Patient - ", font="lucida 10 bold")
lbla = tk.Label(root, text="Address of Patient - ", font="lucida 10 bold")
lblb = tk.Label(root, text="Mobile No. of Patient - ", font="lucida 10 bold")
lblc = tk.Label(root, text="Room No. of Patient - ", font="lucida 10 bold")
lbld = tk.Label(root, text="Medicine Given to Patient - ", font="lucida 10 bold")

txtf = tk.Entry(root, font="lucida 10 bold ", textvariable=txtf_var)
txtl = tk.Entry(root, font="lucida 10 bold", textvariable=txtl_var)
txta = tk.Entry(root, font="lucida 10 bold", textvariable=txta_var)
txtb = tk.Entry(root, font="lucida 10 bold", textvariable=txtb_var)
txtc = tk.Entry(root, font="lucida 10 bold", textvariable=txtc_var)
txtd = tk.Entry(root, font="lucida 10 bold", textvariable=txtd_var)

lblf.grid(row=3, column=0, padx=10, pady=10, ipady=10, ipadx=10)
txtf.grid(row=3, column=1, padx=10, pady=10, ipady=10, ipadx=10)

lbll.grid(row=4, column=0, padx=10, pady=10, ipady=10, ipadx=10)
txtl.grid(row=4, column=1, padx=10, pady=10, ipady=10, ipadx=10)

lbla.grid(row=5, column=0, padx=10, pady=10, ipady=10, ipadx=10)
txta.grid(row=5, column=1, padx=15, pady=10, ipady=10, ipadx=10)

lblb.grid(row=6, column=0, padx=10, pady=10, ipady=10, ipadx=10)
txtb.grid(row=6, column=1, padx=10, pady=10, ipady=10, ipadx=10)

lblc.grid(row=7, column=0, padx=10, pady=10, ipady=10, ipadx=10)
txtc.grid(row=7, column=1, padx=10, pady=10, ipady=10, ipadx=10)

lbld.grid(row=8, column=0, padx=20, pady=10, ipady=10, ipadx=10)
txtd.grid(row=8, column=1, padx=10, pady=10, ipady=10, ipadx=10)

sub_btn = tk.Button(root, text="Submit", font="lucida 15 bold", command=submit)
sub_btn.grid(row=10, column=1, padx=15, pady=15, ipady=15, ipadx=15)

root.mainloop()
