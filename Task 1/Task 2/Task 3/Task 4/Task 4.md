# Problem Statement
Develop a Python program to calculate employee salary based on basic pay, allowances, overtime, and incentives. Calculate the gross salary, apply progressive deductions, and generate a formatted salary statement showing total deductions and net salary.
# Algorithm
1. Start the program.
2. Enter employee name and basic salary.
3. Enter allowances, overtime hours, overtime rate, and incentives.
4. Calculate overtime payment.
5. Calculate gross salary.
6. Calculate progressive deductions based on salary slabs.
7. Calculate Provident Fund (PF) deduction.
8. Calculate total deductions.
9. Calculate net salary.
10. Display the formatted salary statement.
11. Stop the program.
    
# Mermaid Flowchart
```mermaid
    A([Start]) --> B[/Enter employee name and basic salary/]
    B --> C[/Enter allowances, overtime and incentives/]
    C --> D{Are inputs valid?}
    D -- No --> E[Display Invalid Input]
    D -- Yes --> F[Calculate overtime payment]
    F --> G[Calculate gross salary]
    G --> H[Calculate progressive deductions]
    H --> I[Calculate PF deduction]
    I --> J[Calculate total deductions]
    J --> K[Calculate net salary]
    K --> L[/Display salary statement/]
    E --> M([Stop])
    L --> M
```
# Python Source Code

print("--- EMPLOYEE PAYROLL SYSTEM ---")

name = input("Enter employee name: ")

basic = float(input("Enter basic salary: "))
allowances = float(input("Enter allowances: "))
hours = float(input("Enter overtime hours: "))
rate = float(input("Enter overtime rate: "))
incentives = float(input("Enter incentives: "))

if (basic < 0 or allowances < 0 or hours < 0
    or rate < 0 or incentives < 0):

    print("Invalid Input")

else:
    overtime = hours * rate

    gross = basic + allowances + overtime + incentives

    # Progressive deduction
    if gross <= 10000:
        tax = 0

    elif gross <= 20000:
        tax = (gross - 10000) * 0.05

    else:
        tax = 500 + (gross - 20000) * 0.10

    # PF deduction
    pf = basic * 0.08

    total_deduction = tax + pf

    net_salary = gross - total_deduction

    print("\n--- SALARY STATEMENT ---")
    print("Employee Name:", name)
    print("Basic Salary: Rs.", basic)
    print("Allowances: Rs.", allowances)
    print("Overtime Payment: Rs.", overtime)
    print("Incentives: Rs.", incentives)
    print("Gross Salary: Rs.", gross)
    print("Progressive Deduction: Rs.", tax)
    print("PF Deduction: Rs.", pf)
    print("Total Deduction: Rs.", total_deduction)
    print("Net Salary: Rs.", net_salary)
# Sample Input
   --- EMPLOYEE PAYROLL SYSTEM ---

Enter employee name: Lokesh
Enter basic salary: 25000
Enter allowances: 5000
Enter overtime hours: 10
Enter overtime rate: 200
Enter incentives: 2000
# Expected Output
--- SALARY STATEMENT ---

Employee Name: Lokesh
Basic Salary: Rs. 25000.0
Allowances: Rs. 5000.0
Overtime Payment: Rs. 2000.0
Incentives: Rs. 2000.0
Gross Salary: Rs. 34000.0
Progressive Deduction: Rs. 1900.0
PF Deduction: Rs. 2000.0
Total Deduction: Rs. 3900.0
Net Salary: Rs. 30100.0
# screenshot
<img width="762" height="355" alt="image" src="https://github.com/user-attachments/assets/6b4510b1-1127-4ad2-9f30-007298bc2e19" />
