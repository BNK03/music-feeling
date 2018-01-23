# music-feeling
Python Project 

#Chandler Bankos
#Project Milestone Function Framework

import pygame
def inputKeyword():
    mood=["sad", "happy", "mad", "dance", "party", "funky", "groovy", "freaky" ]
    for word in mood:
        print(word,end=" ")
    try:
        a=input("Please enter a keyword from the list: ")
        if (len(a)) == 0:
            print("Did not enter a keyword")
        return(a)
    except:
        raise Exception("Something went wrong")

def keywordIdentify(a):
    song={"sad":"s4.wav",
       "happy":"h1.wav",
       "dance":"d1.wav",
       "party":"p1.wav",
          "mad":"m1.wav",
          "funky":"f1.wav",
          "groovy":"g1.wav",
          "freaky":"fr.wav",
          "excited":"e1.wav"}
    return(song[a])
    

def outputMusic(b):
    pygame.mixer.pre_init(44100,-16,2,2048)
    pygame.mixer.init()
    sound=pygame.mixer.Sound(b)
    sound.play()

def finalOutput():
    i=1
    while i<4:
        try:
            a=inputKeyword()
            b=keywordIdentify(a)
            outputMusic(b)
        except:
            print("Program Ended")
            break
    

        

finalOutput()
