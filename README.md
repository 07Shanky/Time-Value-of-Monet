# Time-Value-of-Money
# Calculate Time Value of Money 
def cal_pv_lump_sum():
    amt = float(input("Enter Amount: "))
    year = int(input("Enter Year: "))
    dis_rate = float(input("Enter Discounting Rate: "))
    pvif = 1 / round((1 + dis_rate / 100) ** year, 6)
    lump_sum = amt * pvif
    print(f"Present Value of Lumpsum {amt} is {lump_sum:.2f}")

def cal_pv_annuity():
    annuity = float(input("Enter Annuity Amount: "))
    year = int(input("Enter Years: "))
    dis_rate = float(input("Enter Discounting Rate: "))
    pvifa = ((1 - (1 / round((1 + dis_rate / 100) ** year, 6))) / (dis_rate / 100))
    annuity_value = annuity * pvifa
    print(f"Present Value of the Annuity Amount {annuity} is {annuity_value:.2f}")

def cal_pv_uneven_cashflow():
    k = int(input("Select \n 1) Different Discounting Rate for Different Cashflow \n 2) Same Discounting Rate For Different Cashflow: "))
    cashflows = int(input("Enter number of cash flows:"))
    pv = 0
    for m in range(cashflows):
        cashflow = float(input(f"Enter cash flow for Year {m + 1}:"))
        if k == 1:
            dis_rate = float(input(f"Enter Discount Rate for Year {m + 1}:"))
            pv += cashflow / ((1 + (dis_rate / 100)) ** (m + 1))
        elif k == 2:
            dis_rate1 = float(input(f"Enter Discounting Rate:"))
            pv += cashflow / ((1 + (dis_rate1 / 100)) ** (m + 1))
    print(f"Present Value of the Uneven Cash Flow is {pv:.2f}")

def cal_fv_lump_sum():
    amt = float(input("Enter Amount: "))
    year = int(input("Enter Year: "))
    comp_rate = float(input("Enter Compounding Rate: "))
    fvif = round((1 + comp_rate / 100) ** year, 6)
    lump_sum = amt * fvif
    print(f"Future Value of Lumpsum {amt} is {lump_sum:.2f}")

def cal_fv_annuity():
    annuity = float(input("Enter Annuity Amount: "))
    year = int(input("Enter Years: "))
    comp_rate = float(input("Enter Compounding Rate: "))
    fvifa = ((round((1 + comp_rate / 100) ** year, 6) - 1) / (comp_rate / 100))
    annuity_value = annuity * fvifa
    print(f"Future Value of the Annuity Amount {annuity} is {annuity_value:.2f}")

def cal_fv_uneven_cashflow():
    k = int(input("Select \n 1) Different Compounding Rate for Different Cashflow \n 2) Same Compounding Rate For Different Cashflow: "))
    cashflows = int(input("Enter number of cash flows:"))
    fv = 0
    for m in range(cashflows):
        cashflow = float(input(f"Enter cash flow for Year {m + 1}:"))
        if k == 1:
            comp_rate = float(input(f"Enter Compounding Rate for Year {m + 1}:"))
            fv += cashflow * ((1 + (comp_rate / 100)) ** (m + 1))
        elif k == 2:
            comp_rate1 = float(input(f"Enter Compounding Rate:"))
            fv += cashflow * ((1 + (comp_rate1 / 100)) ** (m + 1))
    print(f"Future Value of the Uneven Cash Flow is {fv:.2f}")

print("Welcome User !!!")
print("Would you like to Calculate Present Value or Future Value?")
print("1) Present Value\n2) Future Value")
n = int(input("Enter Your Choice:"))

if n == 1:
    print("Let's Calculate Present Value of Money")
    print("Select\n1) Lump Sum\n2) Annuity\n3) Uneven CashFlow")
    i = int(input("Enter Your Selection:"))
    if i == 1:
        cal_pv_lump_sum()
    elif i == 2:
        cal_pv_annuity()
    elif i == 3:
        cal_pv_uneven_cashflow()
    else:
        print("Invalid option. Please select a valid option.")

elif n == 2:
    print("Let's Calculate Future Value of Money")
    print("Select\n1) Lump Sum\n2) Annuity\n3) Uneven CashFlow")
    i = int(input("Enter Your Selection:"))
    if i == 1:
        cal_fv_lump_sum()
    elif i == 2:
        cal_fv_annuity()
    elif i == 3:
        cal_fv_uneven_cashflow()
    else:
        print("Invalid option. Please select a valid option.")
		
else:
    print("Invalid option. Please select a valid option.")
