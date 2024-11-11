import random 

word = ["bad","index","random","print","cin","fine","black"]
rand_word =random.choice(word)
display =len(rand_word)*"_"
print(display)

HANGMANPICS = ['''
  +---+
  |   |
      |
      |
      |
      |
=========''', '''
  +---+
  |   |
  O   |
      |
      |
      |
=========''', '''
  +---+
  |   |
  O   |
  |   |
      |
      |
=========''', '''
  +---+
  |   |
  O   |
 /|   |
      |
      |
=========''', '''
  +---+
  |   |
  O   |
 /|\  |
      |
      |
=========''', '''
  +---+
  |   |
  O   |
 /|\  |
 /    |
      |
=========''', '''
  +---+
  |   |
  O   |
 /|\  |
 / \  |
      |
=========''']
lis_display =list(display)
live =6
photo = 0
while ("_" in lis_display)  :
  if live > 0 :
    choice = input("Enter letter please ")
  
    if len(choice) == 1 :
      if choice in rand_word :
        findi =list(rand_word).index(choice)
        lis_display[findi] = choice 

        print("".join(lis_display))
      elif choice not in rand_word:
        print("\ninvaled choice\n")
        live-=1
        print(f"you have {live} already ")
        print(HANGMANPICS[photo+1])
        print("".join(lis_display))
        photo+=1
    else :
       print("Erroe 'Enter one line ' ")
  elif live == 0 :
    print("you lose")
    print("\ntry again later\n")
    print("the man was hanged ")
    break
if "_" not in lis_display :
  print("************************ Congrats! *************************")
  print("you finsh the game ")


