class ShoppingCart:
    def __init__(self):
        self.cart = {}

    def add_item(self, product_name, price, quantity):
        if quantity <= 0:
            raise ValueError("Quantity must be greater than 0.")
        if product_name in self.cart:
            self.cart[product_name][1] += quantity
        else:
            self.cart[product_name] = [price, quantity]

    def apply_discount(self, coupon_code, total_price):
        if coupon_code == "SAVE10":
            return total_price * 0.9
        elif coupon_code == "50OFF":
            return total_price * 0.5
        else:
            return total_price

    def calculate_total_price(self, coupon_code=None):
        total_price = sum([self.cart[item][0] * self.cart[item][1] for item in self.cart])
        if coupon_code:
            print("Total :",total_price)
            print("Coupon Applied")
            total_price = f" Total price after discount {self.apply_discount(coupon_code, total_price)}"

        return total_price

    def display_cart(self):
        print("Items in the cart:")
        for item in self.cart:
            print(f"{item} - Price: {self.cart[item][0]}, Quantity: {self.cart[item][1]}")
        print(f"{self.calculate_total_price('SAVE10')}")

    def run(self):
        try:
            self.add_item("Apple", 2.0, 3)
            self.add_item("Banana", 1.0, 2)
            self.add_item("Orange", 1.5, 1)  # Invalid quantity, will raise an exception
        except ValueError as e:
            print(f"Error: {e}")
        finally:
            print("Thank you for shopping!")


if __name__ == "__main__":
    cart = ShoppingCart()
    cart.run()
    cart.display_cart()


