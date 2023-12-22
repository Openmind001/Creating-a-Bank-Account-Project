# Creating-a-Bank-Account-Project

#Checkpoint Objective
#Create a class called "Account" that has the following attributes:
#account_number (string)
#account_balance (float)
#account_holder (string)
#The class should have the following methods:
#deposit(amount: float) - This method should add the amount passed as an argument to the account balance.
#withdraw(amount: float) - This method should subtract the amount passed as an argument from the account balance, but only if the account balance is greater than the amount being withdrawn.
#check_balance() - This method should return the current account balance.
#Instructions
#Create a new file called "bank_account.py"
#Define the Account class and its attributes as specified above.
#Define the deposit() method. It should take in one argument, the amount to be deposited, and add it to the account balance.
#Define the withdraw() method. It should take in one argument, the amount to be withdrawn, and subtract it from the account balance. The method should only execute the withdrawal if the account balance is greater than or equal to the amount to be withdrawn.
#Define the check_balance() method. It should return the current account balance.
#Create an instance of the Account class, and assign it to a variable called "my_account".
#Use the methods of the class to deposit and withdraw money from the account, and check the account balance.
#Test the program by creating multiple instances of the class and performing different transactions on them.

class Account:
    def __init__(self, account_number, account_balance, account_holder):
        self.account_number = account_number
        self.account_balance = account_balance
        self.account_holder = account_holder

    def deposit(self, amount):
        self.account_balance += amount
        print(f"Deposited ${amount}. Current balance: ${self.account_balance}")

    def withdraw(self, amount):
        if self.account_balance >= amount:
            self.account_balance -= amount
            print(f"Withdrew ${amount}. Current balance: ${self.account_balance}")
        else:
            print("Insufficient funds. Withdrawal canceled.")

    def check_balance(self):
        return self.account_balance

# Create an instance of the Account class
my_account = Account(account_number="123456789", account_balance=1000.0, account_holder="John Doe")

# Test the methods
my_account.deposit(500.0)
my_account.withdraw(200.0)
print(f"Current balance: ${my_account.check_balance()}")

# Test with another account
another_account = Account(account_number="987654321", account_balance=1500.0, account_holder="Jane Smith")
another_account.deposit(1000.0)
another_account.withdraw(2000.0)  # This should print an insufficient funds message
print(f"{another_account.account_holder}'s balance: ${another_account.check_balance()}")
