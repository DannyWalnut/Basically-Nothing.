#Created by Daniel Walton, Kazim Raffiq-Fazal, Mobin Hosseini & Oskar Lesniewski <3#
#Ver 1.9#

import time
import random
import msvcrt

############################## Function 1 - Fibonacci ############################## - Danny

def fibonacci():
    print("\n----------------------------")
    t=1
    n=1
    l=0
    c=0
    s=20
    while s>0:
        time.sleep(0.05)
        print (t,n)
        l = c
        c = n
        n = c + l
        t = t + 1
        s = s - 1
        while s<1:
            cont=input("Do you wish to continue?\n(Press Y to continue, N to cancel)\n").title()
            if cont == ("Y"):
                s=20
            else:
                table()

############################## Function 2 - Rocket League Trading ############################## - Danny & Kazim

def rocketleague1(credit):
    print("\n----------------------------")
    print("You have", credit, "credits.")
    time.sleep(1)
    bs=input("Do you wish to buy, check owned items or sell?\n(Enter B to buy, C to check, and S to sell)\n").title()
    if bs == ("B"):
        rocketleaguebuy(credit)
    if bs == ("C"):
        f = open("OwnedItems.txt", "r")
        print("You own the following items:")
        OwnedItems = f.read()
        print (OwnedItems)
        f.close()
        time.sleep(1)
        rocketleague1(credit)
    if bs == ("S"):
        rocketleaguesell(credit)
    else:
        print("\nThat is not an acceptable answer.\n")
        rocketleague1(credit)

def rocketleaguebuy(credit):
    print("\n----------------------------")
    print("You have", credit, "credits.")
    item = input("What item do you want?\n").title()
    price = random.randint(1,10000)
    print("\nI will give you ", item, " for ", price, " credits!")
    time.sleep(1)
    accept = input("Do you accept the trade? Y or N?\n").title()
    choices = ["N", "Y"]
    while accept not in choices:
        print("\nThis is not an acceptable answer. Try again.\nI will give you ", item, " for ", price, " credits!")
        accept = input("Do you accept the trade? Y or N?\n").title()
    if accept == ("Y"):
        credit = credit - price
        if credit < 1:
            print("\nHaha you are broke noob. GG.\n----------------------------\n")
            table()
        print("\nYou acquired ", item, " for ", price, "credits!")
        f = open("OwnedItems.txt", "a")
        item = item+"\n"
        f.write(item)
        f.close()
        time.sleep(1)
        print("Your new balance is: ", credit)
        rocketleague1(credit)
    if accept == ("N"):
        rocketleague1(credit)

def rocketleaguesell(credit):
    print("\n----------------------------")
    print("You have", credit, "credits.")
    time.sleep(1)
    print("You own the following items:")
    f = open("OwnedItems.txt", "r")
    OwnedItems = f.read()
    print (OwnedItems)
    time.sleep(1)
    item=input("\nWhat item do you wish to sell? ").title()
    arr=OwnedItems.split("\n")
    arr=arr[0:len(arr)-1]
    if item in arr:
        arr.remove(item)
    else:
        print("You do not own", item)
        rocketleague1(credit)
    f.close()
    f = open("OwnedItems.txt", "w+")
    for i in arr:
        f.write(i+"\n")
    f.close()
    profit=random.randint(1,11000)
    credit=credit+profit
    print("\nYou received ", profit, " for your ", item)
    time.sleep(1)
    print("You now have", credit, "credits.")
    rocketleague1(credit)

############################## Function 3 - Destroy Storage ############################## - Danny

def destroy():
    print("\n----------------------------\n Now destroying... Have fun :)")
    i=int(1)
    while i>0:
        j=str(i)
        f= open("yo cruise "+j+".txt","w+")
        f.write("nothing.")
        f.close()
        i+=1

############################## Function 4 - Spam Message ############################## - Oskar

def spam():
    print("\n----------------------------")
    msg = input("Enter the message: ")
    n = int(input("How many times?: "))
    print("t minus")
    time.sleep(1)
    count = int(5)
    while(count != 0):
            print(count)
            time.sleep(1)
            count -= 1
    print("Fire in the hole!!!")
    time.sleep(1)
    for i in range(0,int(n)):
        print(msg)
    table()

############################## Function 5 - Rock Paper Scissors ############################## - Oskar

def rps():
    print("\n----------------------------")
    input("Welcome to Rock, Paper, Scissors! Press Enter to start.\n----------------------------\n")
    user_wins = 0
    computer_wins = 0
    choices = ["Rock", "Paper", "Scissors"]
    while True:
      random_index = random.randint(0,2)
      cpu_choice = choices[random_index]
      user_choice = input("Rock, Paper, or Scissors? ").title()
      while user_choice not in choices:
        user_choice = input("That is not a valid choice. Please try again: ").title()
      print()
      print("Your choice:", user_choice)
      time.sleep(1)
      print("Computer's choice:", cpu_choice)
      print()
      time.sleep(1)
      if user_choice == "Rock":
        if cpu_choice == "Rock":
          print("It's a tie!")
        elif cpu_choice == "Scissors":
          print("You win!")
          user_wins+=1
        elif cpu_choice == "Paper":
          print("You lose!")
          computer_wins+=1
      elif user_choice == "Paper":
        if cpu_choice == "Paper":
          print("It's a tie!")
        elif cpu_choice == "Rock":
          print("You win!")
          user_wins+=1
        elif cpu_choice == "Scissors":
          print("You lose!")
          computer_wins+=1
      elif user_choice == "Scissors":
        if cpu_choice == "Scissors":
          print("It's a tie!")
        elif cpu_choice == "Paper":
          print("You win!")
          user_wins+=1
        elif cpu_choice == "Rock":
          print("You lose!")
          computer_wins+=1
      time.sleep(1)
      print()
      print("You have "+str(user_wins)+" wins")
      print("The computer has "+str(computer_wins)+" wins")
      print()
      repeat = input("Play again? (Y/N) ").title()
      while repeat not in ["Y", "N"]:
        repeat = input("That is not a valid choice. Please try again: ").title()
      if repeat == "N":
        print("\n")
        table()
      print("\n----------------------------\n")

############################## Function 6 - Nothing ############################## - Danny

def nothing():
    i=1
    while i>0:
        time.sleep(5)
        print("\nOK goodbye!")
        time.sleep(1)
        exit()

############################## Function 7 - Amogus ############################## - Danny, Kazim, Oskar & Mobin

def amogus():
    print("\n----------------------------")
    colours = ["Red","Orange","Brown","Purple","Yellow","Cyan","Pink","Lime","Green","Blue","White","Black"]
    print("What colour character do you wish to play as?\n\nYou may play as:")
    print(', '.join(colours))
    player_colour = input("\n").title()
    while player_colour not in colours:
        player_colour = input("That is not a valid choice. Please try again:").title()
    print("\nYou are:",player_colour)
    time.sleep(2)
    maps = ["The Skeld","Polus","Mira HQ","The Airship"]
    mapchosen = random.choice(maps)
    print("The map you are playing on is:", mapchosen)
    if mapchosen == "The Skeld":
        locations = ["Cafeteria","Weapons","Navigation","O2","Shields","Communications","Storage","Admin","Electrical","Lower Engine","Security","Reactor","Upper Engine"]
    if mapchosen == "Polus":
        locations = ["Dropship","Electrical","Outside","Office","O2","Admin","Boiler Room","Communications","Decontamination","Laboratory","MedBay","Security","Specimen Room","Storage","Weapons"]
    if mapchosen == "Mira HQ":
        locations = ["Launchpad","MedBay","Communications","Locker Room","Office","Admin","Balcony","Cafeteria","Decontamination","Hallway","Laboratory","Reactor","Storage","Greenhouse"]
    if mapchosen == "The Airship":
        locations = ["Electrical","Cockpit","Vault","Brig","Security","Medical","Meeting Room","Gap Room","Engine Room","Records","Main Hall","Kitchen","Showers","Viewing Deck","Lounge","Armory"]
    time.sleep(2)
    player_status = random.randint(1, 1)
    if player_status < 2:
        player_status = "Impostor"
    else: player_status = "Crewmate"
    print("You are:",player_status)
    colours.remove(player_colour)
    if player_status == "Impostor":
        susmeter = 8
        caught = "false"
        time.sleep(2)
        ImpostorTeammate = random.choice(colours)
        print(ImpostorTeammate, "is the other impostor.")
        impostor_colours = [player_colour, ImpostorTeammate]
        impostor_count = len(impostor_colours)
        crewmate_colours = colours
        crewmate_colours.remove(ImpostorTeammate)
        catcher = random.choice(crewmate_colours)
        crewmate_count = len(crewmate_colours)
        print("There are",impostor_count,"impostors among us.")
        time.sleep(2)
        while impostor_count > 1:
            print("\n----------------------------")
            caught = "false"
            killpotential = random.randint(0,4)
            teammatekills = random.randint (0,1)
            kills = 0
            while kills < killpotential:
                victim = random.choice(crewmate_colours)
                catchers = crewmate_colours
                catchers.remove(victim)
                catcher = random.choice(catchers)
                location = random.choice(locations)
                seenchance = random.uniform(0,crewmate_count)/10
                seenchance = seenchance*100
                seenchance = round(seenchance, 2)
                print("Do you wish to kill", victim, "in", location,"?\nYou have a",seenchance,"% chance of being caught by",catcher)
                killvictim = input("Press Q to kill, N to spare them!\n").title()
                buttons = ["Q","N"]
                while killvictim not in buttons:
                    killvictim = input("That is not a valid choice. Please try again:\n").title()
                if killvictim == "Q":
                    print()
                    print(victim,"was killed! So sus!")
                    crewmate_count = len(crewmate_colours)
                    print(crewmate_count + impostor_count,"players remain.")
                    time.sleep(2)
                    if random.uniform(0,100) < seenchance:
                        print()
                        print(catcher,"saw you kill! Will the group believe them?\n")
                        susmeter = susmeter + random.uniform(15,28)
                        caught = "true"
                        time.sleep(2)
                        killpotential = 0
                    else:
                        print("\nNobody saw you kill... nice moves.")
                        time.sleep(2)
                        susmeter = susmeter + random.uniform(1,5)
                        caught = "false"
                    print("----------------------------\n")
                    killpotential = killpotential - 1
                else:
                    killpotential = killpotential - 1
                    susmeter = susmeter + random.uniform(1,3)
                    crewmate_colours.append(victim)
                    caught = "false"
                    print("----------------------------")
            else:
                print("An emergency meeting has been called!")
                if caught == "true":
                    time.sleep(3)
                    print(catcher,"says 'I saw",player_colour,"kill",victim,"in",location,"!'")
                    time.sleep(3)
                    counter = input("What is your counter argument?\n").title()
                    print(player_colour,"says'",counter,"!'")
                    success = random.randint(1,100)
                    if random.randint(1,100) > success:
                        success = "fail"
                    else: success = "success"
                    if success == "success":
                        print("\nYou refuted their argument!")
                        susmeter = susmeter - random.randint(10,35)
                    else:
                        print("That was a weak argument!")
                        susmeter = susmeter + random.randint(5,10)
                else:
                    print(random.choice(crewmate_colours),"pressed the button.")
                time.sleep(3)
                playervotes = 0
                crewvotes = 0
                for i in range (crewmate_count - 1):
                    if random.randint(0,100) < susmeter:
                        playervotes = playervotes + 1
                    else:
                        crewvotes = crewvotes + 1
                playervotes = playervotes + 1
                crewvotes = crewvotes + impostor_count
                print("You got",playervotes,"votes")
                time.sleep(3)
                crewmate_colours.append(catcher)
                crewmate_colours.append(catcher)
                mostvotedr = random.choice(crewmate_colours)
                oppvotes = random.randint(1,crewvotes)
                print(mostvotedr,"was the highest other player and received",oppvotes,"votes.")
                time.sleep(3)
                crewmate_colours.remove(catcher)
                crewmate_colours.remove(catcher)
                if playervotes > oppvotes:
                    print("You have been voted out!")
                    #make spectate using dead variable

                if playervotes == oppvotes:
                    print("It's a tie!\nNobody was ejected.\n",crewmate_count + impostor_count,"players remain.")
                    print("There are",impostor_count,"impostors among us.")
                    
                elif playervotes < oppvotes:
                    print(mostvotedr,"has been voted out!")
                    print(mostvotedr,"was not the impostor.")
                    crewmate_colours.remove(mostvotedr)
                    crewmate_count = len(crewmate_colours)
                    print(crewmate_count + impostor_count,"players remain.")
                    print("There are",impostor_count,"impostors among us.")
                    
                    
                
    else:
        print("Crewmate game")

############################## Function 8 - DaBaby ############################## - Oskar

def dababy():
    a = ["\nLet's GOOO!!", "\nHUH?!?", "\nYEEE", "\nYOU KNOW IT'S BABY NI..", "\nFollow DaCruisey on IG", "\nIt's me DaBaby on my secret account LESS GOO!","I WILL TURN YOU INTO A CONVERTIBLE"]
    print(random.choice(a))
    print("\n")
    table()

############################## Function 9 - Kazim's Strategy Game ############################## - Kazim

class Character:
    def __init__(self, hp, dmg, crit, dodge, block):
        self.hp = random.randint(5, 20)
        self.dmg = random.randint(1, 3)
        self.crit = random.randint(self.dmg, self.dmg * 2)
        self.dodge = random.randint(1 , 7)
        self.block = random.randint(1, 7)

def battlec():
    name = random.choice(['bob', 'james', 'daniel', 'oscar', 'victoria', 'alice', 'victor', 'olivia', 'edward', 'bruno', 'ellie', 'thomas', 'terry', 'ryan'])
    name = name.title()
    difficulty = input("| Easy | Medium | Hard | \n").lower()
    if difficulty == 'easy' or difficulty[0] == 'e':
        multiplier = 0.5
    elif difficulty == 'medium' or difficulty[0] == 'm':
        multiplier = 0.8
    elif difficulty == 'hard' or difficulty[0] == 'h':
        multiplier = 1.2
    else:
        print("difficulty error.")
        battlec()
    hp = random.randint(5, 20)
    dmg = random.randint(1, 3)
    crit = random.randint(dmg, 2 * dmg)
    dodge = random.randint(1, 7)
    block = random.randint(1, 7)
    player = Character(hp, dmg, crit, dodge, block)
    hp = (random.randint(5, 18)) / 2
    dmg = round((random.randint(1, 3)) / 2)
    crit = random.randint(dmg, 2 * dmg)
    dodge = (random.randint(1 , 5)) / 2
    block = (random.randint(1, 5)) / 2
    computer = Character(hp, dmg, crit, dodge, block)
    print("---------------------------------")
    time.sleep(0.1)
    print("-Player Stats-")
    time.sleep(0.1)
    print("Health: " + str(player.hp))
    time.sleep(0.1)
    print("Attack Damage: " + str(player.dmg))
    time.sleep(0.1)
    print("Critical Hit Damage: " + str(player.crit))
    time.sleep(0.1)
    print("Dodge Chance: ", str(player.dodge * 10), "%")
    time.sleep(0.1)
    print("Block Absorber: ", str(player.block * 10), "%")
    time.sleep(0.1)
    print("---------------------------------")
    time.sleep(0.1)
    print("You are against %s, may the best being win" % name)
    time.sleep(1)
    turn = ['player', 'computer']
    pturn = random.choice(turn)
    while computer.hp > 0 and player.hp > 0:
        pattack = False
        pblock = False
        pdodge = False
        cattack = False
        cblock = False
        cdodge = False
       
        print("---------------------------------")
        time.sleep(0.1)
        print("- %s 's Stats-" % name)
        time.sleep(0.1)
        print("Health: " + str(computer.hp))
        time.sleep(0.1)
        print("Attack Damage: " + str(computer.dmg))
        time.sleep(0.1)
        print("Critical Hit Damage: " + str(computer.crit))
        time.sleep(0.1)
        print("Dodge Chance: " + str(computer.dodge * 10) + "%")
        time.sleep(0.1)
        print("Block Absorber: " + str(computer.block * 10) + "%")
        time.sleep(0.1)
        print("---------------------------------")
        time.sleep(0.1)
        print("-Player Stats-")
        time.sleep(0.1)
        print("Health: " + str(player.hp))
        time.sleep(0.1)
        print("Attack Damage: " + str(player.dmg))
        time.sleep(0.1)
        print("Critical Hit Damage: " + str(player.crit))
        time.sleep(0.1)
        print("Dodge Chance: " + str(player.dodge * 10) + "%")
        time.sleep(0.1)
        print("Block Absorber: " + str(player.block * 10) + "%")
        time.sleep(0.1)
        print("---------------------------------")
        time.sleep(0.1)
        if pturn == 'player':
            print("player goes first")
        else:
            print("computer goes first")        
        print("What will you do?")
        time.sleep(0.1)
        pchoice = input(" | Attack | Block | Dodge | Any fumbling will give your opponent an advantage!\n")
        pchoice = pchoice.lower()
        if pchoice == 'attack' or pchoice[0] == 'a':
            pattack = True
        elif pchoice == 'block' or pchoice[0] == 'b':
            pblock = True
        elif pchoice == 'dodge' or pchoice[0] == 'd':
            print("player wants to dodge")
            pdodge = True
        cchoice = random.randint(0, 3)
        if cchoice == 0:
            cattack = True
        elif cchoice == 1:
            cblock = True
        elif cchoice == 2:
            cdodge = True
        if (pblock == True and cblock == True) or (pdodge == True and cdodge == True) or (pblock == True and cdodge == True) or (pdodge == True and cblock == True):
            print("both players did not engage in offensive attacks")
            if pturn == 'player': pturn = 'computer'
            else: pturn = 'player'
            continue
        if pturn == 'player':
            if pattack == True:
                if random.randint(0, 20) <= (15 - (multiplier * 10)):
                    if cblock == True:
                        computer.hp -= player.crit / 2
                        print("computer blocked")
                    elif cdodge == True:
                        print("computer dodge attempted on crit")
                        if random.randint(0, 10) <= computer.dodge:
                            print("computer dodge success")
                    else:
                        print("player normal crit from attempted dodge")
                        computer.hp -= player.crit
                    print("Crit player damage")
                else:
                    if cblock == True:
                        computer.hp -= player.dmg / 2
                        print("computer blocked, half damage dealt")
                    elif cdodge == True:
                        print("computer dodge attempted on normal attack")
                        if random.randint(0, 10) >= computer.dodge:
                            print("computer dodge success")
                    else:
                        computer.hp -= player.dmg
                        print("player normal attack")
            if cattack == True:
                if random.randint(0, 20) >= (20 - (multiplier * 10)):
                    if pblock == True:
                        player.hp -= computer.crit / 2
                        print("player blocked computer's crit")
                    elif pdodge == True:
                        print("player dodge attempted on computer normal damage")
                        if random.randint(0, 10) <= player.dodge:
                            print("player dodge success")
                    else:
                        player.hp -= computer.crit
                    print("Crit computer damage")
                else:
                    if pblock == True:
                        player.hp -= computer.dmg / 2
                        print("player blocked computer's damage")
                    elif pdodge == True:
                        print("player dodge attempted")
                        if random.randint(0, 10) <= player.dodge:
                            print("player dodge success")
                    else:
                        player.hp -= computer.dmg
                        print("computer dealt normal damage")
            pturn = 'computer'
        else:
            if cattack == True:
                if random.randint(0, 20) >= (20 - (multiplier * 10)):
                    if pblock == True:
                        player.hp -= computer.crit / 2
                        print("player blocked computer's crit")
                    elif pdodge == True:
                        print("player dodge attempted")
                        if random.randint(0, 10) <= player.dodge:
                            print("player dodge success")
                    else:
                        player.hp -= computer.crit
                    print("Crit computer damage")
                else:
                    if pblock == True:
                        player.hp -= computer.dmg / 2
                        print("player blocked computer's damage")
                    elif pdodge == True:
                        print("player dodge attempted")
                        if random.randint(0, 10) <= player.dodge:
                            print("player dodge success")
                    else:
                        player.hp -= computer.dmg
                        print("computer dealt normal damage")
            if pattack == True:
                if random.randint(0, 20) <= (20 - (multiplier * 10)):
                    if cblock == True:
                        computer.hp -= player.crit / 2
                        print("computer blocked")
                    elif cdodge == True:
                        print("computer dodge attempted on crit")
                        if random.randint(0, 10) <= computer.dodge:
                            print("computer dodge success")
                    else:
                        print("player normal crit from attempted dodge")
                        computer.hp -= player.crit
                    print("Crit player damage")
                else:
                    if cblock == True:
                        computer.hp -= player.dmg / 2
                        print("computer blocked, half damage dealt")
                    elif cdodge == True:
                        print("computer dodge attempted on normal attack")
                        if random.randint(0, 10) >= computer.dodge:
                            print("computer dodge success")
                    else:
                        computer.hp -= player.dmg
                        print("player normal attack")
            pturn = 'player'
    if player.hp <= 0:
        winner = name
    elif computer.hp <= 0:
        winner = 'you'
    print("And the winner was", winner, "GG!")
    print("-------------------------------------")
    print("Do you want to play again?")
    choice = input("| Yes | No |\n")
    choice = choice.lower()
    if choice[0] == 'y':
        print("Loading in new battle...")
        time.sleep(1)
        print("...")
        time.sleep(1)
        print("...")
        battlec()
    else:
        print("I will take that as a no then :(, hope to see you play again!")
        table()

############################## Function 10 - Odds On ############################## - Oskar

def odds():
    print("----------------------------")
    bb = int(input("Type in a number between 1 and 10\n"))
    b = random.randint(1,10)
    print("The computer chose", b)
    if bb == b:
        print("You must do the task!\n")
        table()
    else:
        print("You got lucky G\n")
        table()
        
############################## Table ############################## - Danny

def table():
    print("----------------------------")
    open('OwnedItems.txt', 'w').close()
    fib=str(1)
    rl=str(2)
    dest=str(3)
    spa=str(4)
    rp=str(5)
    noth=str(6)
    amog=str(7)
    dab=str(8)
    strat=str(9)
    odds=str(10)
    options = ["1","2","3","4","5","6","7","8","9","10"]
    option = input("""What would you like to do?
Press '1' to see the Fibonacci sequence!
Press '2' to trade Rocket League items!
Press '3' to destroy your storage!
Press '4' to spam a message!
Press '5' to play Rock Paper Scissors!
Press '6' to nothing!
Press '7' to amogus!
Press '8' to DaBaby!
Press '9' to play Kazim's Strategy Game!
Press '10' to play odds on!\n""")
    while option not in options:
        option = input("That is not a valid choice. Please try again:\n")
    if option == fib:
        fibonacci()
    if option == rl:
         rocketleague1(25000)
    if option == dest:
        confirm=input("Are you sure? (Press Y to continue, N to cancel)\n").title()
        if confirm == ("Y"):
            destroy()
        else:
            print("Ok then you do you.\n")
            table()
    if option == spa:
        spam()
    if option == rp:
        rps()
    if option == noth:
        nothing()
    if option == amog:
        amogus()
    if option == dab:
        dababy()
    if option == strat:
        battlec()

table()

