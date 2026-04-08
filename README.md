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
print("Invalid option, try again.") # CO2: else branch
 
 
# ── CO4: Testing ─────────────────────────────────────────
 
def run_tests():
"""CO4 — Unit tests to verify logic without needing Firebase"""
print("\nRunning Tests...\n")
passed, failed = 0, 0
 
def check(name, condition):
nonlocal passed, failed
if condition:
print(f" PASS: {name}"); passed += 1
else:
print(f" FAIL: {name}"); failed += 1
 
 
