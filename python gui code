import tkinter as tk
from tkinter import simpledialog
from tkinter import messagebox

class ATM:
    def __init__(self, root):
        self.root = root
        self.root.title("ATM Machine")
        self.balance = 1000000
        self.pin = 1234

        # Define GUI elements
        self.label = tk.Label(root, text="Insert your Card")
        self.label.pack()

        self.pin_entry = tk.Entry(root, show='*')
        self.pin_entry.pack()

        self.pin_button = tk.Button(root, text="Enter", command=self.check_pin)
        self.pin_button.pack()
        
    def check_pin(self):
        pin_input = int(self.pin_entry.get())
        if self.pin == pin_input:
            self.transaction_loop()
        else:
            messagebox.showwarning("Invalid PIN", "Incorrect PIN entered. Please try again.")

    def transaction_loop(self):
        while True:
            option = simpledialog.askinteger("Select Option", 
                                             "Enter 1 for Balance Inquiry\n"
                                             "Enter 2 for Money Withdrawal\n"
                                             "Enter 3 for Money Deposit\n"
                                             "Enter 4 to Exit")
            if option == 1:
                self.check_balance()
            elif option == 2:
                self.withdraw()
            elif option == 3:
                self.deposit()
            elif option == 4:
                messagebox.showinfo("Exit", "Thank You, Visit Again")
                break
            else:
                messagebox.showwarning("Invalid Option", "Please select a valid option.")
    
    def check_balance(self):
        messagebox.showinfo("Balance Inquiry", f"Your Current Balance is: {self.balance} Rupees only")

    def deposit(self):
        damount = simpledialog.askinteger("Deposit", "Enter your Deposit amount:")
        if damount is not None:
            self.balance += damount
            messagebox.showinfo("Success", "Successfully Deposited")

    def withdraw(self):
        amount = simpledialog.askinteger("Withdrawal", "Enter the Withdrawal amount:")
        if amount is not None:
            if amount <= self.balance:
                self.balance -= amount
                messagebox.showinfo("Success", "Transaction Successful")
            else:
                messagebox.showwarning("Failed", "Insufficient Balance")

if __name__ == "__main__":
    root = tk.Tk()
    atm = ATM(root)
    root.mainloop()
