import sys
class Customer:
    '''Customer class with bank operation'''
    bankname="sai bank"
    
    def __init__(self,name,balance=0.0):
        self.name=name
        self.balance=balance

    def deposit(self,amount):
        self.balance=self.balance+amount
        print('the balance after deposit:',self.balance)

    def withdraw(self,amount):
        if amount>self.balance:
            print("insufficient funds....can't perform this opertion")
            sys.exit()
        self.balance=self.balance-amount
        print('the balance after withdraw:',self.balance)

print(Customer.__doc__)

print("welcome to",Customer.bankname)
name=input("enter your name:")
c=Customer(name)
while True:
    print('d-Deposit \n w-withdraw \n e-exit')
    option=input('choose your option')
    if option=='d' or option=='D':
        amount=float(input('enter amount to deposit:'))
        c.deposit(amount)
    elif option=='w' or option=='W':
        amount=float(input('enter amount to withdraw:'))
        c.withdraw(amount)
    elif option=='e' or option=='E':
        print('Thnaks for Banking at',Customer.bankname)
        sys.exit()
    else:
        print("invalid option....please choose valid option")
