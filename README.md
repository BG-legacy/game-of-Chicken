Bernard Ginn 
import random
chicken_count=0
def welcome():# displays the Welcome message
    print("Welcome to my game of Chickens in a Pen!")
    return
def chickens():# method to take user input for number of chickens and validate the user input
    chicken_count = int(input("Enter the number of chickens: "))
    while chicken_count <2 or chicken_count > 100:
        print("The value is invalid!")
        chicken_count = int(input("Enter a number between 2 and 100: "))
    print('You entered ', chicken_count)
    return chicken_count
                 
def eggs(x):#A function that asks for and validates the # eggs entered
    y=int(input("Please enter the number of eggs:"))
    print("You entered",y)
    if y<1 or y>=x:
        while True:
            print("Please enter a number between 1 and",x-1,"!")
            q=int(input("Please enter the number of eggs: "))
            if q>=1 and q<x:
                print("You entered",q)
                return q
            break
        else:
            return y
    
def display(x,y):#a function to create and print the pen (list)
    mylist=[0]*(x-y)
    i = 0
    while i<y:
      mylist.append("&")
      i=i+1
    random.shuffle(mylist)
    for j in range(len(mylist)):
      if mylist[j]!="&":
        if j != 0 and mylist[j-1] == "&":
          mylist[j]+=1
        if j != x-1 and mylist[j+1] == "&":
          mylist[j]+=1
        mylist[j] = str(mylist[j])
    
    print("Pen:")
    print(' '.join(mylist))

def main():#a main function that calls the other functions
    welcome()
    x=chickens()
    y=eggs(x)
    display(x,y)
    
main()
