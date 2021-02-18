#Theme Park Ticket Program (A Cleave 15/02/2021)

#Import functions
import sys
import os
import time
from datetime import date

#Welcome message 1
def welcome_message1() :
    adult_ticket_price = 20.00
    child_ticket_price = 12.00
    senior_ticket_price = 11.00
    crowd_count = 0
    os.system('clear')
    print("Welcome to Copington Adventure Theme Park")
    print("")
    print("Ticket Prices :   Adults          : £{:.2f}".format(adult_ticket_price))
    print("              :   Child           : £{:.2f}".format(child_ticket_price))
    print("              :   Senior Citizen  : £{:.2f}".format(senior_ticket_price))
    print("")

    ticket_entry(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)

#Welcome message 2
def welcome_message2(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price) :
    time.sleep(3)
    os.system('clear')
    print("Welcome to Copington Adventure Theme Park")
    print("")
    print("Ticket Prices :   Adults          : £{:.2f}".format(adult_ticket_price))
    print("              :   Child           : £{:.2f}".format(child_ticket_price))
    print("              :   Senior Citizen  : £{:.2f}".format(senior_ticket_price))
    print("")

    ticket_entry(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)

#Loop to collect ticket volumes
def ticket_entry(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price) :
    #Define variables
    ticket_entries = 0
    ticket_num = 0
    num_adults = 0
    num_child = 0
    num_seniors = 0
    num_total_tickets = 0
    num_total_tickets_int = 0
    adult_entry_check = False
    child_entry_check = False
    senior_entry_check = False
    
    while ticket_num == 0 :
        while ticket_entries == 0 :
            print("How many total tickets would you like? (Max " + str(500 - crowd_count) + " available)")
            num_total_tickets = input()
            if num_total_tickets.isdigit() == True :
                num_total_tickets_int = int(num_total_tickets)
                if num_total_tickets_int < 1 :
                    print("Invalid input")
                    ticket_entry(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)
                elif num_total_tickets_int == 9999 :
                        admin_console(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)
                if crowd_count + num_total_tickets_int > 500 :
                        print("Ticket volume requested would exceed visitor limit.")
                        ticket_entry(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)
            elif num_total_tickets.isdigit() == False :
                print("Invalid input")
                print("")
                ticket_entry(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)
            ticket_entries = ticket_entries + 1

        while adult_entry_check == False :
            print("How many Adult tickets?")
            num_adults = input()
            if num_adults.isnumeric() == True :
                num_adults_int = int(num_adults)
                adult_entry_check = True
            else :
                print("Invalid entry")
                adult_entry_check = False
                  
        while child_entry_check == False :
            print("How many Child tickets?")
            num_children = input()
            if num_children.isnumeric() == True :
                num_children_int = int(num_children)
                child_entry_check = True
            else :
                print("Invalid entry")
                child_entry_check = False
        
        while senior_entry_check == False :
            print("How many Senior Citizen tickets?")
            num_seniors = input()
            if num_seniors.isnumeric() == True :
                num_seniors_int = int(num_seniors)
                senior_entry_check = True
            else :
                print("Invalid entry")
                senior_entry_check = False
       
#Check ticket entries valid   
        if num_total_tickets_int != num_adults_int + num_children_int + num_seniors_int :
            print("There has been a miscalculation when inputting total tickets.")
            ticket_entry(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)
        else:
            ticket_num = ticket_num + 1
       
            wristband_prompt(num_adults_int, num_children_int, num_seniors_int, num_total_tickets_int, crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)

#Wristband prompt
def wristband_prompt(num_adults_int, num_children_int, num_seniors_int, num_total_tickets_int,crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price) :
    #Define variables
    wrist_check = False
    num_wrist = 0
    num_wrist_int = 0
    
    while wrist_check == False :
            print("How many wristbands would you like, they are £20 each?")
            num_wrist = input()
            if num_wrist.isnumeric() == True :
                num_wrist_int = int(num_wrist)
                if num_wrist_int <= num_total_tickets_int :
                    wrist_check = True
                else :
                    print("Invalid entry")
                    wrist_check = False
            else :
                print("Invalid entry")
                wrist_check = False
        
    lead_booker(num_adults_int, num_children_int, num_seniors_int, num_wrist_int, num_total_tickets_int, crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)

#Surname entry and validation
def lead_booker(num_adults_int, num_children_int, num_seniors_int, num_wrist_int, num_total_tickets_int, crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price) :
    #Define variables
    booker = False
    booker_surname = ""
    
    while booker == False :
        print("What is the lead booker's surname?")
        booker_surname = input()
        if booker_surname.isalpha() == True :
            booker = True
        else :
            print("Invalid entry")

    parking_pass(num_adults_int, num_children_int, num_seniors_int, num_wrist_int, booker_surname, num_total_tickets_int, crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)

#Parking pass prompt
def parking_pass(num_adults_int, num_children_int, num_seniors_int, num_wrist_int, booker_surname, num_total_tickets_int, crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price) :
    #Define variables
    passcheck = False
    pass_req = ""

    while passcheck == False :
        print("Do you require a parking pass (free)? (Y / N)")
        pass_req = input()
        pass_req = pass_req.upper()
        if pass_req == "Y" :
            print("")
            print("I AM YOUR PARKING PASS, PUT ME IN YOUR CAR WINDOW")
            passcheck = True
        elif pass_req == "N" :
            print ("")
            passcheck = True
        else:
            print("Invalid entry")

    calculate_prices(num_adults_int, num_children_int, num_seniors_int, num_wrist_int, booker_surname, num_total_tickets_int, crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)

#Calculate prices for ticket groups
def calculate_prices(num_adults_int, num_children_int, num_seniors_int, num_wrist_int, booker_surname, num_total_tickets_int, crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price) :
    #Define variables
    cost_num_adults = 0
    cost_num_children = 0
    cost_num_seniors = 0
    cost_num_wrist = 0
    total_cost = 0

    cost_num_adults = num_adults_int * adult_ticket_price
    cost_num_children = num_children_int * child_ticket_price
    cost_num_seniors = num_seniors_int * senior_ticket_price
    cost_num_wrist = num_wrist_int * 20.00
    total_cost = cost_num_adults + cost_num_children + cost_num_seniors + cost_num_wrist
    print_thankyou(booker_surname, total_cost, num_total_tickets_int, crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)
   
#Print thanks
def print_thankyou(booker_surname, total_cost, num_total_tickets_int, crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price) :
    print("Thanks Mr/Mrs/Ms" , booker_surname)
    print("")

    collect_payment(total_cost, num_total_tickets_int, crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)

#Loop to collect & validate payment
def collect_payment(total_cost, num_total_tickets_int, crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price) :
    #Define variables
    payment = 0
    num_10_input = 0
    num_10_int = 0
    num_20_int = 0
    amt_10_paid = 0
    amt_20_paid = 0
    amt_change_int = 0
    ten_entry_check = False
    twenty_entry_check = False
    

    while payment == 0 :
        print("The total price for your day is £{:.2f}".format(total_cost))
        print("")
        print("Please pay with either £10 or £20 notes.")
        print("")

        while ten_entry_check == False :
            print("How many £10 notes would you like to enter?")
            num_10_input = input()
            if num_10_input.isnumeric() == True :
                num_10_int = int(num_10_input)
                amt_10_paid = num_10_int * 10.00
                ten_entry_check = True
            else :
                print("Invalid entry")
                ten_entry_check = False


        if amt_10_paid == total_cost :
            print("Thanks for your payment. Enjoy your day!")
            crowd_count = crowd_count + num_total_tickets_int
            payment = payment + 1
        elif amt_10_paid > total_cost :
            amt_change_int = amt_10_paid - total_cost
            amt_20_paid = 0
            print("Thanks for your payment. Your change is £{:.2f}".format(amt_change_int))
            crowd_count = crowd_count + num_total_tickets_int
            payment = payment + 1
        else:
            while twenty_entry_check == False :
                print("How many £20 notes would you like to enter?")
                num_20_input = input()
                if num_20_input.isnumeric() == True :
                    num_20_int = int(num_20_input)
                    amt_20_paid = num_20_int * 20.00
                    twenty_entry_check = True
                else :
                    print("Invalid entry")
                    twenty_entry_check = False
        
        if amt_10_paid + amt_20_paid == total_cost :
            print("Thanks for your payment. Enjoy your day!")
            crowd_count = crowd_count + num_total_tickets_int
            payment = payment + 1
        elif amt_10_paid + amt_20_paid > total_cost :
            amt_change_int = (amt_10_paid + amt_20_paid) - total_cost
            print("Thanks for your payment. Your change is £{:.2f}".format(amt_change_int))
            crowd_count = crowd_count + num_total_tickets_int
            payment = payment + 1
        else:
            print("Insufficient payment. All money returned.")
            ten_entry_check = False
            twenty_entry_check = False

    print_date(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)

#Print date
def print_date(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price) :
    today = date.today()
    print("Today's date:", today)
    welcome_message2(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)    

#Admin console funtions
def admin_console(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price) :
    #Define variables
    admin_selection = ""
    temp_adult_ticket_price = 0
    temp_child_ticket_price = 0
    temp_senior_ticket_price = 0

    os.system('clear')
    print("Copington Adventure Theme Park Admin Console")
    print ("")
    print("Press :")
    print("1 to change prices")
    print("")
    print("2 to shutdown machine")
    print("")
    print("3 to return to visitor mode")
    print("")
    admin_selection = input()
    if admin_selection.isalpha() == True :
         admin_console(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)
    
    elif admin_selection == "1" :
        print("")
        print("Enter Adult price - current = £{:.2f}".format(adult_ticket_price))
        temp_adult_ticket_price = input()
        if temp_adult_ticket_price.isnumeric() == True :
            adult_ticket_price = int(temp_adult_ticket_price)
        else :
            admin_console(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)
        
        
        
        print("")
        print("Enter Child price - current = £{:.2f}".format(child_ticket_price))
        temp_child_ticket_price = input()
        if temp_child_ticket_price.isnumeric() == True :
            child_ticket_price = int(temp_child_ticket_price)
        else :
            admin_console(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)
        
        
        
        print("")
        print("Enter Senior price - current = £{:.2f}".format(senior_ticket_price))
        temp_senior_ticket_price = input()
        if temp_senior_ticket_price.isnumeric() == True :
            senior_ticket_price = int(temp_senior_ticket_price)
        else :
            admin_console(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)

        admin_console(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)
    
    elif admin_selection == "2" :
            print ("")
            print("S y s t e m     S h u t d o w n")
            print("")
            sys.exit()        
    
    elif admin_selection == "3" :
            welcome_message2(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)
    
    else :
            admin_console(crowd_count, adult_ticket_price, child_ticket_price, senior_ticket_price)
    
#Run code
welcome_message1()
