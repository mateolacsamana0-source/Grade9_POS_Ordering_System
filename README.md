# Grade9_POS_Ordering_System
Argota &amp; Lacsamana

Hello! This is the POS Ordering System created by Angelina Jane E. Argota and Mateo Lucas B. Lacsamana. We collaborated together to share ideas and build a better, stabilized POS orderibg meals, so you can order meals efficiently. 

class Product:
    def __init__(self, product, quantity, price):
        self.product = product
        self.quantity = quantity
        self.price = price

    def total(self):
        return self.price * self.quantity


class Receipt:
    def __init__(self, items):
        self.items = items

    def total(self):
        return sum(item.total() for item in self.items)

    def display(self):
        print("=" * 40)
        print("RECEIPT MINI STORE".center(40))
        print("=" * 40)
        print(f"{'Item':<20}{'Qty':>5}{'Price':>7}{'Amount':>8}")
        print("-" * 40)
        
        for item in self.items:
            print(f"{item.product:<20}{item.quantity:>5}"
                  f"{item.price:>7.2f}{item.total():>8.2f}")
        print("-" * 40)
        print(f"{'TOTAL AMOUNT':<32}{self.total():>8.2f}")
        print("=" * 40)

        print ("THANK YOU FOR YOUR ORDER!")
        print ("=" *40)


if __name__ == "__main__":
    order = Receipt([
        Product("Burger", 2, 50),
        Product("Fries", 1, 35),
        Product("Soft Drink", 1, 50),
    ])
    order.display()
