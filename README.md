# Exercise 1

class BankAccount:
    """Initial account protected by pin number"""

    def _init_(self):
        """Initial account balance is 0 and pin is 'pin'"""
        self.pin = 'pin'
        self._balance = 0

    def deposit(self, pin, amount):
        """Increment account balance by amount and return amount"""
        if self.pin == pin:
            self._balance = self._balance + amount
            return self._balance
        else:
            print('pin is wrong')

    def withdraw(self, pin , amount):
        """Decrement account balance by amount and returm amount"""
        if self.pin == pin:
            self._balance = self._balance - amount
            return self._balance
        else:
            print("pin is wrong")

    def get_balance(self, pin):
        """Return account balance"""
        if self.pin == pin:
            return self._balance

    def change_pin(self, oldpin, newpin):
        """Change pin from oldpin to newpin."""
        if self.pin == oldpin:
            self.pin = newpin
            print('The old pin is ' + oldpin)
            print('New PIN is ' + self.pin)
        else:
            print("pin is wrong")

# Exercise 3
class SavingsAccount(BankAccount):

    def _init_(self):
        super()._init_()
        self._interestRate = 0.06

    def interest(self):
        self._balance = self._balance + (self._balance * self._interestRate)
        return self._balance

# Exercise 4
class FeeSavingsAccount(SavingsAccount):

    def _init_(self):
        super()._init_()
        self.free = 1

    def withdraw(self, pin , amount):
        if self.pin == pin:
            self._balance = self._balance = (amount + self.free)
            return self._balance
        else:
            return "Wrong Pin"


myBank = BankAccount()
savings_account = SavingsAccount()
fee_account = FeeSavingsAccount()

print(savings_account.interest())

pin = input('insert pin')
amount = int(input('insert amount'))

newpin = input('newpin')
oldpin = input('oldpin')
print(myBank.deposit(pin=pin, amount=amount))
# print(my_bank.withdraw('pin', 2))
# print(fee_account.deposit(pin='pin', amount=12))
# print(fee_account.withdraw('pin', 2))
print(myBank.change_pin(oldpin, newpin))
