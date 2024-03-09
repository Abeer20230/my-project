# my-project

def CheckWin(Resultlist):
    if(len(Resultlist)== 3):
      if(Resultlist[0]+Resultlist[1]+Resultlist[2] == 15):
        return True
    if(len(Resultlist)== 4):
        if(Resultlist[0]+Resultlist[1]+Resultlist[3] == 15):
            return True
        if(Resultlist[1]+Resultlist[2]+Resultlist[3] == 15):
            return True
    if(len(Resultlist)== 5):
        if(Resultlist[0]+Resultlist[1]+Resultlist[4] == 15):
            return True
        if(Resultlist[1]+Resultlist[2]+Resultlist[4] == 15):
            return True
        if(Resultlist[2]+Resultlist[3]+Resultlist[4] == 15):
            return True
    else:
        return False
    return False
# varaible to store score
list1=[]
list2=[]

while(True):
    while(True):
        # take input from 1st player
        input1 = input(" player 1 : ")
        if( not input1.isdigit()):
            print('invalid')
            continue
        P1 = int(input1)
        # check if input is valid (betwen 1 and 9)
        if (P1< 1 or P1>9):
            print('invalid must be between 1 and 9')
        elif (P1 in list1) or (P1 in list2):
            print('invalid duplicated nymber')
        else:
            break
    # add player 1 number to score
    list1.append(P1)
    
    # check if player 1 win
    if(CheckWin(list1)):
        print("Player 1 win")
        break
    # check if game is draw 
    elif(len(list1) + len(list2) == 9):
        print("Draw")
        break
        
    while(True):
        # take input from 2nd player
        input2 = input(" player 2 : ")
        if( not input2.isdigit()):
            print('invalid')
            continue
        P2 = int(input2)
        # check if input is valid (betwen 1 and 9)
        if (P2< 1 or P2>9):
            print('invalid must be between 1 and 9')
        elif (P2 in list1) or (P2 in list2):
            print('invalid duplicated nymber')
        else:
            break
    # add player 2 number to score
    list2.append(P2)
    
    # check if player 2 win
    if(CheckWin(list2)):
        print("Player 2 win")
        break
    # check if game is draw 
    elif(len(list1) + len(list2) == 9):
        print("Draw")
        break

print("End Game")
