# pharmacy-system
Keep records of sold medical drugs in the pharmacy
class Pharmacy:
    def __init__(self):
        self.drugs = {}
        self.sales_history = []

    def add_drug(self, name, quantity):
        if name in self.drugs:
            self.drugs[name] += quantity
        else:
            self.drugs[name] = quantity

    def sell_drug(self, name, quantity):
        if name in self.drugs and self.drugs[name] >= quantity:
            self.drugs[name] -= quantity
            self.sales_history.append((name, quantity))
            print(f"Sold {quantity} {name}(s).")
        else:
            print(f"Insufficient quantity of {name}.")

    def display_inventory(self):
        print("Current Inventory:")
        for name, quantity in self.drugs.items():
            print(f"{name}: {quantity}")

    def display_sales_history(self):
        print("Sales History:")
        for sale in self.sales_history:
            name, quantity = sale
            print(f"{quantity} {name}(s) sold.")
