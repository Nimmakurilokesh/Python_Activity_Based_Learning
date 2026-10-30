# Problem Statement
Develop a Python program to generate a retail shopping bill for multiple products. Calculate product prices based on quantity, apply category-specific taxes, provide discounts based on purchase amounts, and ensure that the maximum discount limit is not exceeded. Finally, display an itemized invoice with the total bill amount.
# Algorithm
1. Start the program.
2. Enter the number of products.
3. Enter product name, category, price, and quantity.
4. Calculate the total price of each product.
5. Calculate the subtotal of all products.
6. Apply a discount based on the subtotal:
   - Above ₹5,000: 10% discount.
   - Above ₹2,000: 5% discount.
   - Otherwise: No discount.
7. Limit the maximum discount to ₹1,000.
8. Calculate category-specific tax.
9. Calculate the final bill.
10. Display the itemized invoice.
11. Stop the program.
# Mermaid Flowchart
  ```mermaid
    A([Start]) --> B[/Enter number of products/]
    B --> C[/Enter product name, category, price and quantity/]
    C --> D{Valid inputs?}
    D -- No --> E[Display Invalid Input]
    D -- Yes --> F[Calculate product total]
    F --> G[Add to subtotal]
    G --> H{More products?}
    H -- Yes --> C
    H -- No --> I{Subtotal above 5000?}
    I -- Yes --> J[Apply 10 percent discount]
    I -- No --> K{Subtotal above 2000?}
    K -- Yes --> L[Apply 5 percent discount]
    K -- No --> M[No discount]
    J --> N[Limit discount to 1000]
    L --> N
    M --> O[Calculate category tax]
    N --> O
    O --> P[Calculate final bill]
    P --> Q[/Display invoice/]
    E --> R([Stop])
    Q --> R
```
# Python Source Code

products = []
subtotal = 0

n = int(input("Enter number of products: "))

for i in range(n):
    print("\nProduct", i + 1)

    name = input("Enter product name: ")
    category = input("Enter category (Food/Clothing/Electronics): ").lower()
    price = float(input("Enter price: "))
    quantity = int(input("Enter quantity: "))

    if price < 0 or quantity <= 0:
        print("Invalid Input")
        continue

    if category == "food":
        tax_rate = 5
    elif category == "clothing":
        tax_rate = 12
    elif category == "electronics":
        tax_rate = 18
    else:
        print("Invalid Category")
        continue

    total = price * quantity
    subtotal += total

    products.append((name, category, total, tax_rate))

# Calculate discount
if subtotal > 5000:
    discount = subtotal * 0.10
elif subtotal > 2000:
    discount = subtotal * 0.05
else:
    discount = 0

discount = min(discount, 1000)

# Calculate category tax after discount
tax = 0

for name, category, total, rate in products:
    discounted_price = total - (total / subtotal * discount)
    tax += discounted_price * rate / 100

final_bill = subtotal - discount + tax

print("\n--- RETAIL BILL ---")

for name, category, total, rate in products:
    print(name, "-", category, "- Rs.", total)

print("\nSubtotal: Rs.", round(subtotal, 2))
print("Discount: Rs.", round(discount, 2))
print("Category Tax: Rs.", round(tax, 2))
print("Final Bill: Rs.", round(final_bill, 2))
# Sample Input
Enter number of products: 3

Product 1
Enter product name: Rice
Enter category (Food/Clothing/Electronics): food
Enter price: 1000
Enter quantity: 2

Product 2
Enter product name: Shirt
Enter category (Food/Clothing/Electronics): clothing
Enter price: 1000
Enter quantity: 2

Product 3
Enter product name: Headphones
Enter category (Food/Clothing/Electronics): electronics
Enter price: 2000
Enter quantity: 1
# Expected Output
--- RETAIL BILL ---

Rice - food - Rs. 2000.0
Shirt - clothing - Rs. 2000.0
Headphones - electronics - Rs. 2000.0

Subtotal: Rs. 6000.0
Discount: Rs. 600.0
Category Tax: Rs. 630.0
Final Bill: Rs. 6030.0

# screenshot
<img width="803" height="325" alt="image" src="https://github.com/user-attachments/assets/5d41e2ee-7022-4909-95a4-f7271568c0d0" />


