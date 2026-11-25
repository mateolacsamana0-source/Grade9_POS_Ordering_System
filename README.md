# Grade9_POS_Ordering_System
Argota &amp; Lacsamana

Hello! This is the POS Ordering System created by Angelina Jane E. Argota and Mateo Lucas B. Lacsamana. We collaborated together to share ideas and build a better, stabilized POS orderibg meals, so you can order meals efficiently. 

class Product:
    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity 
        
    def display(self):
        print(f"{self.name} - P {self.price:.2f}")
        
class Food(Product):
    def __init__(self, name, price):
        super().__init__(name, price)
        
class Drink(Product):
    def __init__(self, name, price):
        super().__init__(name, price)

def product_menu():
    products = [
        Food("Burger", 50),
        Food("Fries", 35),
        Food("Soft Drink", 25), 
        ]
        
    order_items = []
    
    print("\nPRODUCT MENU ")
    
    for i, product in enumerate(products, 1):
        print(f"{i}. ", end="")
        product.display()
        
    while True:
        choice = int(input("\nselect a product (1-5): "))
        
        if 1 <= choice <= len(products):
            selected = products[choice - 1]
            
            quantity = int(input("quantity"))
            
            subtotal = selected.price * quantity
            
            order_items.append({
                "name": selected.name,
                "price": selected.price,
                "quantity": quantity,
                "subtotal": subtotal
            })
            
            print(f"subtotal: P {subtotal:.2f}")
            
        else:
            print("invalid selection.")
            
        again = input("order another product? (yes/no): ").lower()
        
        if again != "yes":
            break
        
    return order_items
    
ordered_items = product_menu()

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
        Product("Soft Drink", 2, 25),
    ])
    order.display()
