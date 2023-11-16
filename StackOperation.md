ent = None #It is set to None. So it can't change the set stack's name.
stacks = list() #Empty stack, it will serve as the container for the program.
def stack(): #Function call to create a stack and to set the name of the stack permanently.
    global ent #Globalize the ent to call it everywhere in the program.
    if ent is None: #If ent is none, it will ask for a name.
        while True: #The while True function will determine the stack
            ent = input("\nEnter the name stack: ")  # Input a name for the stack.
            if ent.strip(): #If the user input a name of the stack the condition will be true
                print("stack's name:", ent,"\n")  # Print the name of the stack().
                break #break the loop if the condition is true.
            else:
                print("--The stack name is blank-- \n--Don't assigned a blank stack name--") #else ask the user to input again since it cannot enter a stack name with whitespaces char.
    else:
        print(f"--The stack already have a name-- \nname: {ent}\n")  #If the program detects the user to input another name.
        # This will appear and ask the user to enter another operation.

def push(): #This function will serve as the push method or append the element that the user inputted.
    global value #Globalize the variable value to call it all over the program.
    if ent is None: #If the user suddenly choose an operation this condition will apply to the program and repeat to the choices.
        print("--Please name the stack first--\n") #This will display if the user did not follow the proper process.
    else:
        while True:
            value = input(f"\nStack named: {ent} \nEnter an element: ")  # Ask the user to enter an element.
            if value == None:  # The strip() function will help the program to detect if the user tried to enter a blank.
                print(f"--Please enter an element--\n{value}")  # This will display if the condition is true.
            else:
                stacks.append(value)  # Append the value and push it inside the stack.
                print(f"Pushed element in {ent}:",stacks,"\n")  # It will print the pushed element and contain until the program ends.
                break

def pop(): #This function is known for popping or deleting the recently added element inside the stack.
    if stacks: #This condition will determine the stack.
        print(f"\nThe elements in {ent}:", stacks) #Show current stack.
        pop_val = stacks.pop() #It will pop the reCently added element since it follows the LIFO method.
        print(f"The element Popped:",pop_val) #Appear the element that was popped.
        print("Current stack:",stacks,"\n") #Show the current stack from popped method.
    elif not stacks: #The count() function will help the stack to detect an element. If the stacks did not receive any element first from the user.
        print("--There's no element detected--\n") #This will display to the user.
    else:
        print("--The stack empty, name the stack first--\n") #If stack is empty and wanted to use the pop() method, this will appear since its empty already.
        #Then ask the user to enter another operation.

def peek(): #This function is known for showing the most recently added element on the top.
    if ent is None:
        print("--Please name the stack first--\n")
    elif stacks: #This condition will determine the stack.
        peek_value = stacks[-1] #If the user suddenly use the Pop() method and wanted to peek or know what's the top of the stack.
        #This will automatically remove the popped element and show the current element that the user wants to peek in the stack.
        #The -1 will decrement the element.
        print(f"\n{ent}" ,"elements:",stacks) #This will show the current elements.
        print(f"Stack name: {ent}" ,"\nthe peek element:", peek_value,"\n") #Shows the recently added element inside the stack.
    else:
        print("--There's no element detected--\n")  # This will display to the user.

def show(): #This function will show all the current element entered by the user.
    if ent is None: #If the user try to use the show() method, this condition will apply to the program and repeat to the choices of the program.
        print("--Please name the stack first--\n") #This will display if the user did not follow the proper process.

    else:
        if not stacks:  #If the stacks did not detect any element inside the stack. This condition will run.
            print("--There's no element detected--\n")  # This will display to the user

        else:
            print(f"\nThe {ent} element is/are:",stacks,"\n") #show the latest stack.
            #exit() #After using the show() method it will automatically exit the program.

while True: #The while True method will ask the user continously until it shows the final stack.
    print(" [C] - Create Stack\n","[A] - Append element to stack\n","[D] - Remove element on stack\n","[P} - Peek the top element of stack\n","[S] - Show the stack element\n","[X] - Exit program")
    operation = input("\nChoose an operation: ").upper() #This are the following choice to guide the user.

    if operation == "C": #Choice for creating the stack.
        stack()
    elif operation == "A": #Choice for appending an element to the stack.
        push()
    elif operation == "D": #Choice for popping a recently added element inside the stack.
        pop()
    elif operation == "P": #Choice for the top most element inside the stack.
        peek()
    elif operation == "S": #Choice to show the latest stack.
        show()
    elif operation == "X":
        exit()
    else:
        print("--invalid input--") #If the user prompt different keys or characters it will invalid and return to the while True method.
