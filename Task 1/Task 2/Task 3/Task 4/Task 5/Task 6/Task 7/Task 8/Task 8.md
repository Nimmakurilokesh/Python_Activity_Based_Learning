# Problem Statement
Develop a Python program to calculate the total manufacturing cost of a product by considering raw material cost, labour cost, and overhead expenses. Calculate the selling price, profit or loss, and profit percentage. Classify the product as profitable or loss-making.
# Algorithm
1. Start.
2. Read product name and quantity.
3. Read raw material cost, labour cost, and overhead cost per unit.
4. Read selling price per unit.
5. Calculate total manufacturing cost per unit.
6. Calculate total manufacturing cost.
7. Calculate total sales amount.
8. Calculate profit or loss.
9. Calculate profit percentage.
10. Display all results and classify the product.
11. Stop.
 # Mermaid Flowchart
  ```mermaid


flowchart TD
    A([Start]) --> B[/Input product name and quantity/]
    B --> C[/Input material, labour, overhead and selling price/]
    C --> D[Calculate cost per unit]
    D --> E[Calculate total manufacturing cost]
    E --> F[Calculate total sales]
    F --> G[Calculate profit or loss]
    G --> H{Profit greater than zero?}
    H -- Yes --> I[Classify as Profitable]
    H -- No --> J[Classify as Loss or No Profit]
    I --> K[/Display results/]
    J --> K
    K --> L([Stop])    

  ```

# Python Source Code
   
product = input("Enter product name: ")
quantity = int(input("Enter quantity: "))

material = float(input("Enter raw material cost per unit: "))
labour = float(input("Enter labour cost per unit: "))
overhead = float(input("Enter overhead cost per unit: "))
selling_price = float(input("Enter selling price per unit: "))

if quantity <= 0 or material < 0 or labour < 0 or overhead < 0 or selling_price < 0:
    print("Invalid input")
else:
    cost_per_unit = material + labour + overhead
    total_cost = cost_per_unit * quantity
    total_sales = selling_price * quantity

    profit = total_sales - total_cost

    if total_cost > 0:
        profit_percentage = (profit / total_cost) * 100
    else:
        profit_percentage = 0

    print("\n--- Manufacturing Report ---")
    print("Product Name:", product)
    print("Quantity:", quantity)
    print("Cost Per Unit:", cost_per_unit)
    print("Total Manufacturing Cost:", total_cost)
    print("Total Sales:", total_sales)
    print("Profit/Loss:", profit)
    print("Profit Percentage:", round(profit_percentage, 2), "%")

    if profit > 0:
        print("Status: Profitable")
    elif profit < 0:
        print("Status: Loss")
    else:
        print("Status: No Profit No Loss")
# Sample Input
Enter product name: Chair
Enter quantity: 100
Enter raw material cost per unit: 200
Enter labour cost per unit: 100
Enter overhead cost per unit: 50
Enter selling price per unit: 450
# Sample Output
 --- Manufacturing Report ---
Product Name: Chair
Quantity: 100
Cost Per Unit: 350.0
Total Manufacturing Cost: 35000.0
Total Sales: 45000.0
Profit/Loss: 10000.0
Profit Percentage: 28.57 %
Status: Profitable
# screenshot
<img width="753" height="320" alt="image" src="https://github.com/user-attachments/assets/20b3c214-6e79-4a32-9391-ac78f65d557a" />
