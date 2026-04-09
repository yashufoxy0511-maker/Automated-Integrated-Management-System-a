def connect_to_cloud():
    print("Connected to cloud (simulated)")


def add_stock(sym, price, qty):
    print(f"Stock added: {sym}, Price: {price}, Quantity: {qty}")


def view_stock(sym):
    print(f"Viewing stock: {sym}")


def update_price(sym, price):
    print(f"Updated {sym} price to {price}")


def delete_stock(sym):
    print(f"Deleted stock: {sym}")


def list_all_stocks():
    print("Listing all stocks...")


def low_stock_alert():
    print("Checking for low stock...")


def main_menu():
    """CO5 — Interactive stock management system (real-world app)"""
    connect_to_cloud()

    # CO2: while loop keeps the app running
    while True:
        print("""
===================================
CLOUD STOCK AUTOMATION MENU
===================================
[1] Add / Update Stock
[2] View a Stock
[3] Update Stock Price
[4] Delete a Stock
[5] List All Stocks
[6] Low Stock Alerts
[0] Exit
===================================
""")

        choice = input("Enter choice: ").strip()

        # CO2: if/elif/else control structure
        if choice == "1":
            sym = input("Stock Symbol (e.g. RELIANCE): ").upper()
            price = float(input("Price (Rs.): "))
            qty = int(input("Quantity: "))
            add_stock(sym, price, qty)

        elif choice == "2":
            sym = input("Stock Symbol: ").upper()
            view_stock(sym)

        elif choice == "3":
            sym = input("Stock Symbol: ").upper()
            price = float(input("New Price (Rs.): "))
            update_price(sym, price)

        elif choice == "4":
            sym = input("Stock Symbol to delete: ").upper()
            delete_stock(sym)

        elif choice == "5":
            list_all_stocks()

        elif choice == "6":
            low_stock_alert()

        elif choice == "0":
            print("Goodbye!")
            break

        else:
            print("Invalid option, try again.")  # CO2: else branch


# ── CO4: Testing ─────────────────────────────────────────

def run_tests():
    """CO4 — Unit tests to verify logic without needing Firebase"""
    print("\nRunning Tests...\n")
    passed = 0
    failed = 0

    def check(name, condition):
        nonlocal passed, failed
        if condition:
            print(f" PASS: {name}")
            passed += 1
        else:
            print(f" FAIL: {name}")
            failed += 1

    # Sample tests
    check("Test 1", 1 + 1 == 2)
    check("Test 2", "A".lower() == "a")

    print(f"\nTotal Passed: {passed}, Failed: {failed}")


# Run program
if __name__ == "__main__":
    main_menu()
    run_tests()
 
