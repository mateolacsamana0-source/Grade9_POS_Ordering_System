# Grade9_POS_Ordering_System
Argota &amp; Lacsamana

Hello! This is the POS Ordering System Menu created by Angelina Jane E. Argota. I created the Menu portion while Mateo, my partner, created the Receipt. Inside the menu, there are burger, fries, and soft drinks.

class Product:
    def __init__(self, name, price):
        self.name = name
        self.price = price
        
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
        Food("Petchay", 50),
        Food("Monay", 30),
        Food("French Fries", 22), #be carefull y'all this can cause cancer
        Drink("Iced Tea", 35),
        Drink("Lemonade", 35)
        ]
        
    order_items = []
    
    print("\nPRODUCT MENU 🥶")
    
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
