# Problem Statement
Develop a Python program to calculate the financial details of a campus event. Calculate the total income from ticket sales and sponsorships, total expenses, profit or loss, and compare the final amount with the event budget.
# Algorithm
1. Start.
2. Enter the event name.
3. Enter the number of tickets sold and ticket price.
4. Enter sponsorship income.
5. Enter other income.
6. Enter venue, food, decoration, and other expenses.
7. Calculate total income.
8. Calculate total expenses.
9. Calculate profit or loss.
10. Compare expenses with the event budget.
11. Display the financial report.
12. Stop.
# Mermaid Flowchart
  ```mermaid
  flowchart TD
    A([Start]) --> B[/Enter event name and budget/]
    B --> C[/Enter tickets sold and ticket price/]
    C --> D[/Enter sponsorship and other income/]
    D --> E[/Enter event expenses/]
    E --> F[Calculate ticket income]
    F --> G[Calculate total income]
    G --> H[Calculate total expenses]
    H --> I[Calculate profit or loss]
    I --> J{Expenses <= Budget?}
    J -- Yes --> K[Within Budget]
    J -- No --> L[Over Budget]
    K --> M[/Display financial report/]
    L --> M
    M --> N([Stop])
```
# Python Source Code

event = input("Enter event name: ")
budget = float(input("Enter event budget: "))

tickets = int(input("Enter number of tickets sold: "))
price = float(input("Enter ticket price: "))

sponsor = float(input("Enter sponsorship income: "))
other_income = float(input("Enter other income: "))

venue = float(input("Enter venue expenses: "))
food = float(input("Enter food expenses: "))
decoration = float(input("Enter decoration expenses: "))
other_expenses = float(input("Enter other expenses: "))

if (budget < 0 or tickets < 0 or price < 0 or
    sponsor < 0 or other_income < 0 or venue < 0 or
    food < 0 or decoration < 0 or other_expenses < 0):
    print("Invalid input")
else:
    ticket_income = tickets * price
    total_income = ticket_income + sponsor + other_income

    total_expenses = venue + food + decoration + other_expenses
    profit = total_income - total_expenses

    print("\n--- Campus Event Financial Report ---")
    print("Event Name:", event)
    print("Ticket Income:", ticket_income)
    print("Total Income:", total_income)
    print("Total Expenses:", total_expenses)
    print("Profit/Loss:", profit)

    if total_expenses <= budget:
        print("Budget Status: Within Budget")
    else:
        print("Budget Status: Over Budget")

    if profit > 0:
        print("Event Status: Profit")
    elif profit < 0:
        print("Event Status: Loss")
    else:
        print("Event Status: No Profit No Loss")
# Sample Input
 Enter event name: College Fest
Enter event budget: 50000
Enter number of tickets sold: 200
Enter ticket price: 100
Enter sponsorship income: 15000
Enter other income: 5000
Enter venue expenses: 10000
Enter food expenses: 8000
Enter decoration expenses: 7000
Enter other expenses: 5000
# Sample Output
   --- Campus Event Financial Report ---
Event Name: College Fest
Ticket Income: 20000.0
Total Income: 40000.0
Total Expenses: 30000.0
Profit/Loss: 10000.0
Budget Status: Within Budget
Event Status: Profit
# screenshot
<img width="752" height="352" alt="image" src="https://github.com/user-attachments/assets/e1d6f057-a0d3-4983-b30a-5171f629a45a" />

