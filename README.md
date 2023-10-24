# Time-Value-of-Money
# Calculate Time Value of Money 
print(" Welcome user !!!")
print(" Would You like to Calculate Present Value or Future Value ?")
print (" 1) Present Value \n 2) Future Value")
n = int (input("Enter Your Choice :"))
if n == 1: 
    print ("Let's Calcualte Present Value of Money")
    print("Select \n 1) Lump Sum \n 2) Annuinty \n 3) Uneven CashFlow")
    i = int(input("Enter Your Selection:"))
    if i == 1:
        amt= float(input("Enter Amount :"))
        year= int(input("Enter Year:"))
        dis_rate= float(input("Enter Discounting Rate:"))
        pvif = 1/round((1+dis_rate/100)**year,6) # factor upto 6 decimal place
        lump_sum= amt*pvif
        print(f"Present Value of Lumpsum {amt}, is {lump_sum:.2f}")
    elif i==2:
        print ("Select \n 1) Ordinary Annuity \n 2) Annuity Due")
        j = int(input("Enter Your Selection:"))
        if  j == 1 :
            annuity = float(input("Enter Annuity Amount: "))
            year = int(input("Enter Years: "))
            dis_rate = float(input("Enter Discounting Rate: "))
            pvifa = ((1 - (1 / round((1 + dis_rate/100) ** year, 6)))/(dis_rate/100))
            annuity_value = annuity*pvifa
            print(f"Present Value of the Annuity Amount {annuity} is {annuity_value:.2f}")
        elif j == 2 :
            annuity = float(input("Enter Annuity Amount: "))
            year = int(input("Enter Years: "))
            dis_rate = float(input("Enter Discounting Rate: "))
            pvifa = (((1 - (1 / round((1 + dis_rate/100) ** year, 6)))/(dis_rate/100))*(1+dis_rate/100))
            annuity_value = annuity*pvifa
            print(f"Present Value of the Annuity Amount {annuity} is {annuity_value:.2f}")
    elif i == 3:
        print("Select \n 1) Different Discounting Rate for Different Cashflow \n 2) Same Discounting Rate For Different Cashflow")
        k = int(input("Enter Your Selection:"))
        if k == 1 :
            cashflows = int(input("Enter number of cash flows:"))
            pv = 0
            for m in range(cashflows):
                cashflow = float(input(f"Enter cash flow for Year {m + 1}:"))
                dis_rate = float(input(f"Enter Discount Rate for Year {m + 1}:"))
                pv += cashflow / ((1 + (dis_rate / 100)) ** (m + 1))
                print(f"The present value of the cash flows is: {pv:.2f}")
            print(f"Present Value of the Uneven Cash Flow is {pv:.2f}")
        elif k == 2 :
            dis_rate1=float(input(f"Enter Discounting Rate:"))
            cashflows = int(input("Enter number of cash flow:"))
            pv = 0
            for m in range (cashflows):
                cashflow = float(input(f"Enter cash flow for Year{m + 1}:"))
                pv += cashflow/((1+(dis_rate1/100))**(m + 1))
            print(f"Present Value of the Uneven Cash Flow is {pv:.2f}")
elif n == 2: 
    print ("Let's Calcualte Future Value of Money")
    print("Select \n 1) Lump Sum \n 2) Annuinty  \n 3) Uneven CashFlow")
    i = int(input("Enter Your Selection:"))
    if i == 1:
        amt= float(input("Enter Amount :"))
        year= int(input("Enter Year:"))
        comp_rate= float(input("Enter Compounding Rate:"))
        fvif = round((1+comp_rate/100)**year,6) # factor upto 6 decimal place
        lump_sum= amt*fvif
        print(f"Future Value of Lumpsum {amt}, is {lump_sum:.2f}")
    elif i==2:
        print ("Select \n 1) Ordinary Annuity \n 2) Annuity Due")
        j = int(input("Enter Your Selection:"))
        if  j == 1 :
            annuity = float(input("Enter Annuity Amount: "))
            year = int(input("Enter Years: "))
            comp_rate = float(input("Enter Compounding Rate: "))
            fvifa = (round((1 + comp_rate/100) ** year, 6)-1)/(comp_rate/100)
            annuity_value = annuity*fvifa
            print(f"Future Value of the Annuity Amount {annuity} is {annuity_value:.2f}")
        elif j == 2 :
            annuity = float(input("Enter Annuity Amount: "))
            year = int(input("Enter Years: "))
            comp_rate = float(input("Enter Compounding Rate: "))
            fvifa = (((round((1 + comp_rate/100) ** year, 6))-1)/(comp_rate/100))*(1+comp_rate/100)
            annuity_value = annuity*fvifa
            print(f"Future Value of the Annuity Amount {annuity} is {annuity_value:.2f}")
    elif i == 3:
        print("Select \n 1) Different Discounting Rate for Different Cashflow \n 2) Same Discounting Rate For Different Cashflow")
        k = int(input("Enter Your Selection:"))
        if k == 1 :
            cashflows = int(input("Enter number of cash flow:"))
            pv = 0
            for m in range (cashflows):
                cashflow = float(input(f"Enter cash flow for Year{m+1}:"))
                comp_rate=float(input(f"Enter Compounding Rate for Year {m +1}:"))
                pv += cashflow*((1+(comp_rate/100))**(m + 1))
            print(f"Future Value of the Uneven Cash Flow is {pv:.2f}")
        elif k == 2 :
            comp_rate=float(input(f"Enter Compounding Rate:"))
            cashflows = int(input("Enter number of cash flow:"))
            pv = 0
            for m in range (cashflows):
                cashflow = float(input(f"Enter cash flow for Year{m+1}:"))
                pv += cashflow*((1+(comp_rate/100))**(m + 1))
            print(f"Present Value of the Uneven Cash Flow is {pv:.2f}")

else:
    print("Invalid option. Please select Valid Options")
    
