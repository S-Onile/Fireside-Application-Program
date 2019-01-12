# Fireside-Application-Program
A program that facilitates data collection for a hypothetical Card Gaming League.
#Seun Onile-ere
#27/05/17
#This program is being created so that the user's data can be registered for each player attempting to enter the Fireside Annual Card Gaming Leauge,
#subsequently displaying the personal details and information in the appropriate format.
#Task 1: Fireside_Register_Player

def Register():
    #States that as long as the variable 'request' equates to the value 'True', the code wil continue to run
    request = True
    while request == True:
    #Displays the welcome message that associates the player with the context of the program    
     print ('---------->>>Welcome to the Fireside Leauge Registration<<<---------- \n')

    #States that the user input in response to the prompt will be equal to the letters in the original response but in lower case
     First_Name = input('Please enter your First Name. \n')
     First_Name = First_Name.lower()
    #Creates a presence check for the variable 'First_Name', meaning whilst the user input in response to the prompt is equal to a blank space (''), the user will be prompted to re-enter
     while First_Name == '':
         First_Name = input('Unfortunately this input does not contain any notable data; please re-enter your First Name:  \n')
    #Upon this statement, this for loop ensures that any value aside from the letters between and including 'a' and 'z' (the alphabet) will cause an error message to appear 
     if any( [ i>'z' or i<'a' for i in First_Name]):
         print ('Error: Please do not use any non-letter values.  \n')
    #Following the previous message having been printed, the statement 'continue' will then be used to return the control to the beginning of the program 
         continue
    #States that the user input in response to the prompt will be equal to the letters in the original response but in lower case
     Last_Name = input('Please enter your Last Name.  \n')
     Last_Name = Last_Name.lower()
    #Creates a presence check for the variable 'Last_Name', meaning whilst the user input in response to the prompt is equal to a blank space (''), the user will be prompted to re-enter 
     while Last_Name == '':
         Last_Name = input('Unfortunately this input does not contain any notable data; please re-enter your Last Name:  \n')
    #Upon this statement, this for loop ensures that any value aside from the letters between and including 'a' and 'z' (the alphabet) will cause an error message to appear 
     if any( [ i>'z' or i<'a' for i in Last_Name]):
         print ('Error: Please do not use any non-letter values.  \n')
    #Following the previous message having been printed, the statement 'continue' will then be used to return the control to the beginning of the program
         continue
    #Creates a presence check for the variable 'Nick_Name', meaning whilst the user input in response to the prompt is equal to a blank space (''), the user will be prompted to re-enter, closing the name validation segment of the program
     Nick_Name = input('Please enter your Nick Name.  \n')
     while Nick_Name == '':
         Nick_Name = input('Unfortunately this input does not contain any notable data; please re-enter your Nick Name:  \n')
     
    #Imports 're' (Regular Expression) to specifiy a set of strings that matches it for the email validation, subsequently defining the function 'email'
     import re
     def email():
    #Creates a while loop pertaining to a duration in time whilst the variable 'email' is equal to the value 'False'   
         emails = False
         while emails == False:
    #Creates a presence check, meaning whilst the user input in response to the prompt is equal to a blank space (''), the user will be prompted to re-enter       
             Email_Address = input('Please enter your Email Address.  \n')
             while Email_Address == '':
                 Email_Address = input('Unfortunately this input does not contain any notable data; please re-enter your Email Address:  \n')
    #Establishes the variable 'match' as the syntax for a permissible value, for the variable 'Emali_Address' (userinput, '@', userinput , '.', userinput)            
             match = re.search(r'[\w.-]+@[\w.-]+.\w+', Email_Address )
    #States that if the variable 'match' equates to the aformentioned syntax, the variable email is 'False', but anything other than that causes the variable 'email' to remain 'True'      
             if match:
                 print('This email contains the appropriate syntax.  \n', match.group())
                 emails = True
             else:
                 print('Please input the appropriate syntax.  \n')
    #This closes the previously defined function 'email', ending the email validation segment of the program             
     email()
            
    #Creates a while loop pertaining to a duration in time whilst the variable 'valid' is equal to the value 'False'   
     valid = False
     while valid == False:
    #States that if the user input in response to the prompt is equal to 'C', then variable 'Skill_Level' will be appropriated the value 'Casual', 'valid' will equal 'True'
         Skill_Level = input('Please enter either E to dentote an Expert skill level, or C to dentote a Casual skill level.  \n')
         if Skill_Level == 'C':
             Skill_Level = 'Casual'
             valid = True
    #Otherwise, if the user input in response to the prompt is equal to 'E', then variable 'Skill_Level' will be appropriated the value 'Expert', 'valid' will equal 'True'
         elif Skill_Level == 'E':
             Skill_Level = 'Expert'
             valid = True
    #If the user input equates to neither 'E' or 'C', anything besides the options given will cause the program to request another input, finalising the skill level segment of the program.
         else:
             Skill_Level = input('Please enter either C or E to illustrate your level of experience.  \n')
         
    #This prints the user inputted values of each the variables as follows: 'First_Name','Last_Name','Nick_Name' and 'Skill_Level', with the variable 'Email_Address' already having been printed    
     print (First_Name, Last_Name, Nick_Name, Skill_Level)
     print ('Your Email Address has already been outputted above, in correlation with the message: "This email contains the appropriate syntax".  \n')

    #Creates a while loop pertaining to a duration in time whilst the variable 'valid' is equal to the value 'False'
     valid = False
     while valid == False:
    #States that if the user input in response to the prompt is equal to 'Yes', then the string 'Thank you for your time, your Fireside Leauge Registration details have been safely secured' is printed    
         Response = input('Is this information correct? If not, please type No to re-enter data, or Yes to complete the official Fireside Leauge Registration.  \n' )
         if Response == 'Yes':
            print ('Thank you for your time, your Fireside Leauge Registration details have been  safely secured. The program will now return to the title message.  \n' )
    #Following the words 'The program will now return to the title message', the program will then print the intial welcome message ('---------->>>Welcome to the Fireside Leauge Registration<<<----------')
            print ('---------->>>Welcome to the Fireside Leauge Registration<<<---------- \n')
    #After the previous message has been printed, 'request' (the variable from the start of the program) will then equate to 'False', using the statement 'break' to terminate the loop
            request = False
            break
    #Otherwise, if the user input in repsonse to the prompt is equal to 'No', then the string 'The program will now begin anew' will be printed, and 'valid' will equate to 'True'
         if Response == 'No':
             print ('The program will now begin anew \n')
             valid = True
    #Following the previous message having been printed, the statement 'continue' will then be used to return the control to the beginning of the program         
             continue
    #If the user input equates to neither 'Yes' or 'No', than anything besides the options given will cause the program to request another input, concluding the restart segment of the program 
         else:
            Response = input('Please enter either Yes or No to illustrate your choice  \n') 
Register()               
