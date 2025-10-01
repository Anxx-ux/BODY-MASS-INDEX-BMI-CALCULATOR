# BODY-MASS-INDEX-BMI-CALCULATOR
A  simple BMI calculator using python Tkinter
#code
import tkinter as tk
from tkinter import messagebox

def calculate_bmi():
    try:
        weight = float(entry_weight.get())
        height = float(entry_height.get())
        bmi = weight / (height ** 2)

        if bmi < 18.5:
            result = "🌸 BMI: {:.2f}\nYou are Underweight!".format(bmi)
        elif bmi < 24.9:
            result = "🌿 BMI: {:.2f}\nYou are Normal weight!".format(bmi)
        elif bmi < 29.9:
            result = "🍩 BMI: {:.2f}\nYou are Overweight!".format(bmi)
        else:
            result = "❤️ BMI: {:.2f}\nYou are Obese!".format(bmi)

        messagebox.showinfo("Your Result 🐻", result)
    except ValueError:
        messagebox.showerror("Error 🚨", "Please enter valid numbers!")

# Main window
root = tk.Tk()
root.title("Cute BMI Calculator 🐻🍓")
root.geometry("300x250")
root.config(bg="lightpink")

label_title = tk.Label(root, text="🐻 Cute BMI Calculator 🍓", font=("Arial", 14, "bold"), bg="lightpink")
label_title.pack(pady=10)

label_weight = tk.Label(root, text="Enter weight (kg):", bg="lightpink")
label_weight.pack()
entry_weight = tk.Entry(root)
entry_weight.pack()

label_height = tk.Label(root, text="Enter height (m):", bg="lightpink")
label_height.pack()
entry_height = tk.Entry(root)
entry_height.pack()

btn_calculate = tk.Button(root, text="Calculate BMI 🌿", command=calculate_bmi, bg="lightgreen")
btn_calculate.pack(pady=15)

root.mainloop()
