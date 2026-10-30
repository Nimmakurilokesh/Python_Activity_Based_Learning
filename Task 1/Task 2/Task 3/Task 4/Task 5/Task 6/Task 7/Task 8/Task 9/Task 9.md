# Problem Statement
Develop a Python program to calculate a travel budget using multiple currencies. Convert expenses from foreign currencies into Indian Rupees (INR) using given exchange rates. Calculate total expenses, compare them with the available budget, and display the remaining balance or extra amount.
# Algorithm
1. Start.
2. Read the travel budget in INR.
3. Read the number of expenses.
4. For each expense, enter the currency name, amount, and exchange rate.
5. Convert each expense into INR.
6. Calculate the total travel expenses.
7. Compare total expenses with the budget.
8. Calculate the remaining balance or extra amount.
9. Display the travel expense report.
10. Stop.
# Mermaid Flowchart
```mermaid
    A([Start]) --> B[/Enter travel budget in INR/]
    B --> C[/Enter number of expenses/]
    C --> D[Set total expenses = 0]
    D --> E[/Enter currency, amount and exchange rate/]
    E --> F[Convert amount into INR]
    F --> G[Add converted amount to total]
    G --> H{More expenses?}
    H -- Yes --> E
    H -- No --> I[Calculate total expenses]
    I --> J{Total expenses <= Budget?}
    J -- Yes --> K[Calculate remaining balance]
    J -- No --> L[Calculate extra amount]
    K --> M[/Display travel report/]
    L --> M
```
  # Python Source Code
    
budget = float(input("Enter travel budget in INR: "))
n = int(input("Enter number of expenses: "))

total = 0

if budget < 0 or n <= 0:
    print("Invalid input")
else:
    for i in range(n):
        print("\nExpense", i + 1)

        currency = input("Enter currency name: ")
        amount = float(input("Enter expense amount: "))
        rate = float(input("Enter exchange rate to INR: "))

        if amount < 0 or rate <= 0:
            print("Invalid expense")
            continue

        inr = amount * rate
        total += inr

        print("Converted amount in INR:", round(inr, 2))

    print("\n--- Travel Budget Report ---")
    print("Travel Budget: Rs.", budget)
    print("Total Expenses: Rs.", round(total, 2))

    if total <= budget:
        balance = budget - total
        print("Remaining Balance: Rs.", round(balance, 2))
        print("Status: Within Budget")
    else:
        extra = total - budget
        print("Extra Amount: Rs.", round(extra, 2))
        print("Status: Over Budget")
# Sample Input
   Enter travel budget in INR: 50000
Enter number of expenses: 3

Expense 1
Enter currency name: USD
Enter expense amount: 100
Enter exchange rate to INR: 85

Expense 2
Enter currency name: EUR
Enter expense amount: 50
Enter exchange rate to INR: 90

Expense 3
Enter currency name: GBP
Enter expense amount: 20
Enter exchange rate to INR: 100
# Sample Output
Converted amount in INR: 8500.0
Converted amount in INR: 4500.0
Converted amount in INR: 2000.0

--- Travel Budget Report ---
Travel Budget: Rs. 50000.0
Total Expenses: Rs. 15000.0
Remaining Balance: Rs. 35000.0
Status: Within Budget
# screenshot
<img width="703" height="347" alt="image" src="https://github.com/user-attachments/assets/94280e36-b48a-43f8-8cc2-240c60472c98" />


    
    M --> N([Stop])

