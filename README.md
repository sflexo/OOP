import pygame
pygame.init


### class definition--------------------------------------------
class clover:
    def __init__(self, xpos, ypos):
        self.xpos = xpos
        self.ypos = ypos
        
    def draw(self):
        #stem
        pygame.draw.rect(screen, (0,150,85), (self.xpos-10, self.ypos+20, 15, 50))
        #leaves
        pygame.draw.circle(screen, (0,151,0), (self.xpos-20, self.ypos+20), 20) 
        pygame.draw.circle(screen, (85,150,0), (self.xpos, self.ypos-10), 20)
        pygame.draw.circle(screen, (85,150,0), (self.xpos+20, self.ypos+20), 20)
        
class easter:
    def __init__(self, xpos, ypos):
        self.xpos = xpos
        self.ypos = ypos
        
    def draw(self):
        #stem
        #leaves 
        pygame.draw.ellipse(screen, (255,255,255), (self.xpos, self.ypos, 40, 90))
        pygame.draw.ellipse(screen, (255,255,255), (self.xpos+40, self.ypos, 40, 90))
        pygame.draw.ellipse(screen, (250, 2, 180), (self.xpos, self.ypos, 30, 90))
        pygame.draw.ellipse(screen, (250, 2, 180), (self.xpos+40, self.ypos, 30, 90))
        pygame.draw.circle(screen, (255,255,255), (self.xpos+40, self.ypos+80), 50)
        pygame.draw.circle(screen, (0,0,0), (self.xpos+40, self.ypos+80), 50, 2)
        pygame.draw.circle(screen, (0,0,0), (self.xpos+20, self.ypos+60), 15, 2)
        pygame.draw.circle(screen, (0,0,0), (self.xpos+60, self.ypos+60), 15, 2)
        pygame.draw.circle(screen, (0,0,0), (self.xpos+20, self.ypos+60), 10)
        pygame.draw.circle(screen, (0,0,0), (self.xpos+60, self.ypos+60), 10)
        pygame.draw.circle(screen, (250, 2, 180), (self.xpos+40, self.ypos+80), 10)
        pygame.draw.line(screen, (0, 0, 0), [self.xpos+20, self.ypos+100], [self.xpos+60, self.ypos+100], 2)
        #add one more leaf here!


# end of class definition-----------------------------------------

#stamp (aka instantiate) clovers
clover1 = clover(200, 200)
clover2 = clover(400, 400)
clover3 = clover(100, 400)
clover4 = clover(450, 200)
clover5 = clover(600, 250)
bunny1 = easter(500, 600)
bunny2 = easter(600, 400)
bunny3 = easter(300, 150)
bunny4 = easter(200, 350)
bunny5 = easter(150, 550)

#creates game screen and caption
screen = pygame.display.set_mode((800, 800))
pygame.display.set_caption("clover class demo")

#game variables
doExit = False #variable to quit out of game loop
clock = pygame.time.Clock() #sets up a game clock to regulate game speed


#BEGIN GAME LOOP######################################################
while not doExit:
   
    clock.tick(60) #FPS (frames per second)
   
    #pygame's way of listening for events (key presses, mouse clicks, etc)
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
           doExit = True #lets you quit program

    #keyboard input-----------------------------------
  
     
    #render section-----------------------------------
    screen.fill((247, 223, 7))

    #draw class objects
    clover1.draw()
    clover2.draw()
    clover3.draw()
    clover4.draw()
    clover5.draw()
    bunny1.draw()
    bunny2.draw()
    bunny3.draw()
    bunny4.draw()
    bunny5.draw()
  

    pygame.display.flip() #update graphics each game loop

#END GAME LOOP#######################################################
pygame.quit()
