# CoronaGame
#Game 
import turtle
import random
from turtle import*
import math
import time
Width=1400
Height=800
consola=turtle.Screen()
consola.setup(width=Width,height=Height)
consola.bgcolor('#585454')
turtle.speed(0)
turtle.hideturtle()

turtle.tracer(0)

#################################################################################config ecran de joc



##################################################################################cofigurare boschet
p=turtle.Turtle()
p.penup()
p.pensize(1)

p.hideturtle()


def cerc(x,y,culoare,numar_laturi,lungime_latura):
    p.setx(x)
    p.sety(y)
    p.pencolor(culoare)
    p.pendown()
    u = 180 - (360 / numar_laturi)
    u2 = u / 2

    p.setheading(u2)
    p.color(culoare)
    p.begin_fill()
    p.pencolor("black")
    r=1



    for i in range(numar_laturi):
        r=r+1

        p.pensize(0.3 * r)
        p.forward(lungime_latura)
        u2 = u2 - (180 - u)
        p.setheading(u2)
    p.end_fill()
    p.penup()

def boschet(x,y):
    nl=10
    cerc(x+10, y-15, "green", nl, 4)
    cerc(x+20, y+12, "green", nl, 6)
    cerc(x+10, y+15, "green", nl, 6)
    cerc(x, y, "green", nl, 10)

##################################################################################gata  cofigurare boschet
###################################################################################harta cu case etc.
test=turtle.Turtle()

test.hideturtle()

def casa1(x,y,l):
    test.penup()
    test.pensize(5)

    test.setx(x-l/2)
    test.sety(y-l/2)
    test.setheading(0)

    test.pendown()
    test.fillcolor("#C83C3A")
    test.pencolor("#6E0808")
    test.begin_fill()


    for i in range(4):
        test.forward(l)
        test.left(90)
    test.end_fill()
###contur casa

    test.setheading(30)
    test.forward(l / math.sqrt(3))
    test.setheading(90)
    test.forward(l -l/math.sqrt(3))
    test.setheading(150)
    test.forward(l / math.sqrt(3))
    test.setheading(0)
    test.forward(l)
    test.setheading(210)
    test.forward(l / math.sqrt(3))
    test.setheading(270)
    test.forward(l - l / math.sqrt(3))
    test.setheading(-30)
    test.forward(l / math.sqrt(3))

culoare_iarba="#3E9D3E"
dim_iarba=0.3
iarba=turtle.Turtle()
iarba.penup()
iarba.pensize(3)
iarba.setheading(0)
iarba.color(culoare_iarba)
iarba.shape("circle")
iarba.shapesize(dim_iarba,dim_iarba)


def Iarba(x,y):
    iarba.showturtle()

    a=x+260
    b=y-190


    for i in range(20):
        iarba.setx(random.randint(x, a))
        iarba.sety(random.randint(b, y))
        iarba.pendown()
        iarba.forward(1)
        iarba.penup()
    iarba.hideturtle()



def lot(x,y):
    test.penup()
    test.setx(x)
    test.sety(y)
    test.pendown()
    test.pencolor("#2DCF2D")
    test.begin_fill()
    test.fillcolor("#2DCF2D")
    test.setheading(270)
    for i in range(2):
        test.forward(190)
        test.left(90)
        test.forward(260)
        test.left(90)
    test.end_fill()
    Iarba(x, y)
    boschet(x+random.randint(20,50), y-random.randint(20,200))

    casa1(x+130,y-95,120)


###rand loturi....1
lot(-640,360)
boschet(-610, 300)

lot(-310,360)

lot(30,360)

lot(370,360)

###rand loturi....2
lot(-640,90)
lot(-310,90)

lot(30,90)
lot(370,90)
###rand loturi....3
lot(-640,-170)

lot(-310,-170)
lot(30,-170)
lot(370,-170)

################################################################################# gata harta cu case etc .
rezerva=turtle.Turtle()
rezerva.color("white")
rezerva.penup()
rezerva.shape("square")
rezerva.hideturtle()
a = random.randint(1, 5)

if a == 1:
    rezerva.goto(random.randint(-620, 620), random.randint(100, 160))
if a == 2:
    rezerva.goto(random.randint(-620, 620), random.randint(-160, -110))
if a == 3:
    rezerva.goto(random.randint(-40, 20), random.randint(-340, -340))
if a == 4:
    rezerva.goto(random.randint(300, 360), random.randint(-340, 340))
if a == 5:
    rezerva.goto(random.randint(-370, -300), random.randint(-340, 340))

rezerva.showturtle()
rezerva.shapesize(1,0.1)
def Rezerva_dispare():
    rezerva.hideturtle()
    rezerva.goto(-1000,1000)
def Rezerva_apare():
    b = random.randint(1, 300)
    if b == 146:
        rezerva.showturtle()
        a = random.randint(1, 5)
        if a == 1:
            rezerva.goto(random.randint(-620, 620), random.randint(100, 160))
        if a == 2:
            rezerva.goto(random.randint(-620, 620), random.randint(-160, -110))
        if a == 3:
            rezerva.goto(random.randint(-40, 20), random.randint(-340, -340))
        if a == 4:
            rezerva.goto(random.randint(300, 360), random.randint(-340, 340))
        if a == 5:
            rezerva.goto(random.randint(-370, -300), random.randint(-340, 340))
        rezerva.showturtle()




antibiotic=turtle.Turtle()
antibiotic.color("blue")
antibiotic.penup()
antibiotic.shape("circle")
antibiotic.hideturtle()
a = random.randint(1, 5)
if a == 1:
    antibiotic.goto(random.randint(-620, 620), random.randint(100, 160))
if a == 2:
    antibiotic.goto(random.randint(-620, 620), random.randint(-160, -110))
if a == 3:
    antibiotic.goto(random.randint(-40, 20), random.randint(-340, -340))
if a == 4:
    antibiotic.goto(random.randint(300, 360), random.randint(-340, 340))
if a == 5:
    antibiotic.goto(random.randint(-370, -300), random.randint(-340, 340))
antibiotic.showturtle()

antibiotic.shapesize(0.5,1)
def Antibiotic_dispare():
    antibiotic.hideturtle()
    antibiotic.goto(-1000,1000)


def Antibiotic_apare():
    b=random.randint(1,1000)
    if b==132:
        antibiotic.showturtle()
        a = random.randint(1, 5)
        if a == 1:
            antibiotic.goto(random.randint(-620, 620), random.randint(100, 160))
        if a == 2:
            antibiotic.goto(random.randint(-620, 620), random.randint(-160, -110))
        if a == 3:
            antibiotic.goto(random.randint(-40, 20), random.randint(-340, -340))
        if a == 4:
            antibiotic.goto(random.randint(300, 360), random.randint(-340, 340))
        if a == 5:
            antibiotic.goto(random.randint(-370, -300), random.randint(-340, 340))
        antibiotic.showturtle()








################################################################################config tepi virus
culoaretep="#A1226E"
formatep="triangle"
latime_tep=0.3
lungime_tep=5
class Tep(turtle.Turtle):
    def __init__(self,startx,starty,directie_tep,latime_tep,lungime_tep):
        turtle.Turtle.__init__(self)
        self.penup()
        self.color(culoaretep)
        self.shape(formatep)
        self.shapesize(latime_tep,lungime_tep)
        self.setheading(directie_tep)
        self.setx(startx)
        self.sety(starty)
##################################################################################

################config virus si flageli miscare
class Sprite(turtle.Turtle):
    def __init__(self,spriteshape,color,startx,starty,dimensiune):
        turtle.Turtle.__init__(self,shape=spriteshape)
        self.speed(0)
        self.penup()
        self.color(color)
        self.fd(0)
        self.goto(startx,starty)
        self.speed=20
        self.shapesize(dimensiune,dimensiune)

xprim=500
yprim=300

virus=Sprite("circle","#A1226E",xprim,yprim,1.5)

########################################################################################seringa



seringa=turtle.Turtle()
seringa.color("white")
seringa.shape("square")
seringa.shapesize(0.05,0.6)
seringa.speed(0)
seringa.penup()
seringa.setposition(-1000,-1000)
seringa.status="gata"
def inainte_seringa():
    seringa.forward(30)
    if seringa.xcor()>640:
        seringa.status="gata"
        seringa.hideturtle()
    if seringa.xcor()<-640:
        seringa.status = "gata"
        seringa.hideturtle()
    if seringa.ycor()<-360:
        seringa.status = "gata"
        seringa.hideturtle()
    if seringa.ycor()>360:
        seringa.status = "gata"
        seringa.hideturtle()


def arunca_seringa():
    if seringa.status=="gata":
        if seringi.nrseringi>0:
            seringa.showturtle()
            seringa.status = "aruncat"
            seringa.goto(player.xcor(), player.ycor())
            seringi.nrseringi -= 1
            seringi.show_status()
            seringa.setheading(player.heading())




######################################################################################## gata  seringa
######################################################################################## scor
class Game():
    def __init__(self):
        self.level=1
        self.score=0
        self.state="playing"
        self.pen=turtle.Turtle()
        self.pen.hideturtle()
        self.pen.speed(0)
        self.pen.penup()
        self.pen.goto(-600,600)

        self.lives=3
        self.pen.pendown()
    def show_status(self):
        self.pen.undo()
        msg="Score:%s" %(self.score)
        self.pen.goto(-640,360)
        self.pen.penup()
        self.pen.write(msg,font=("Arial",16,"normal"))


game=Game()

game.show_status()
class Game_Over():
    def __init__(self):


        self.state="playing"
        self.pen=turtle.Turtle()
        self.pen.hideturtle()
        self.pen.speed(0)
        self.pen.penup()
        self.score="!!!!!!Mai incerca!"
        self.pen.goto(0,0)
        self.pen.pendown()
    def show_status(self):
        self.pen.undo()
        msg4="Game Over%s" %(self.score)
        self.pen.goto(-340,0)
        self.pen.penup()
        self.pen.write(msg4,font=("Arial",40,"normal"))
gameover=Game_Over()

class VIETI():
    def __init__(self):
        self.level=1
        self.score=0
        self.state="playing"
        self.pen=turtle.Turtle()
        self.pen.hideturtle()
        self.pen.speed(0)
        self.pen.penup()
        self.pen.goto(-600,600)

        self.lives=3
        self.pen.pendown()

    def vieti(self):
        self.pen.undo()
        msg2 = "Vieti:%s" % (self.lives)
        self.pen.penup()
        self.pen.goto(-500, 360)
        self.pen.write(msg2, font=("Arial", 16, "normal"))

nrvieti=VIETI()

nrvieti.vieti()


class NRSERINGI():
    def __init__(self):


        self.pen=turtle.Turtle()
        self.pen.hideturtle()
        self.pen.speed(0)
        self.pen.penup()
        self.pen.goto(-600,600)

        self.nrseringi=3
        self.pen.pendown()
    def show_status(self):
        self.pen.undo()
        msg3="Numar Seringi:%s" %(self.nrseringi)
        self.pen.goto(-400,360)
        self.pen.penup()
        self.pen.write(msg3,font=("Arial",16,"normal"))
seringi=NRSERINGI()
seringi.show_status()

######################################################################################## gata scor
###################################################################################gata  def virus si flagelii



dim=1
culoare_jucator="white"
####picior 1
picior1_jucator=turtle.Turtle()
picior1_jucator.penup()
picior1_jucator.color("black")
picior1_jucator.shape("square")
picior1_jucator.shapesize(0.3,0.3)
picior1_jucator.setx(-9)
picior1_jucator.sety(11)
##picior 2
picior2_jucator=turtle.Turtle()
picior2_jucator.penup()
picior2_jucator.color("black")
picior2_jucator.shape("square")
picior2_jucator.shapesize(0.3,0.3)
picior2_jucator.setx(9 )
picior2_jucator.sety(11)
#####brat 1
brat2_jucator=turtle.Turtle()
brat2_jucator.penup()
brat2_jucator.color(culoare_jucator)
brat2_jucator.shape("square")
brat2_jucator.shapesize(0.2,0.7)
brat2_jucator.setheading(90)
brat2_jucator.setx(18)
brat2_jucator.sety(13)
## brat 2
brat1_jucator=turtle.Turtle()
brat1_jucator.penup()
brat1_jucator.color(culoare_jucator)
brat1_jucator.shape("square")
brat1_jucator.shapesize(0.2,0.7)
brat1_jucator.setheading(90)
brat1_jucator.setx(-18)
brat1_jucator.sety(13)
##### corp
corp_jucator=turtle.Turtle()
corp_jucator.penup()
corp_jucator.color(culoare_jucator)
corp_jucator.shape("square")
corp_jucator.shapesize(2,0.6)
corp_jucator.setheading(90)
player=Sprite("circle","#FFDBAC",0,0,dim)
player.setheading(90)

z=12
def misca_player():
    turtle.tracer(0)
    player.forward(z)
    if player.heading()==90:
        corp_jucator.setx(player.xcor())
        corp_jucator.sety(player.ycor())
        corp_jucator.setheading(90)

        brat1_jucator.setx(player.xcor() - 18)
        brat1_jucator.sety(player.ycor() + 13)
        brat1_jucator.setheading(90)

        brat2_jucator.setx(player.xcor() + 18)
        brat2_jucator.sety(player.ycor() + 13)
        brat2_jucator.setheading(90)

        picior1_jucator.setheading(90)
        picior1_jucator.setx(player.xcor() - 9)
        picior1_jucator.sety(player.ycor() + 11)

        picior2_jucator.setheading(90)
        picior2_jucator.setx(player.xcor() + 9)
        picior2_jucator.sety(player.ycor() + 11)
    if player.heading()==270:
        corp_jucator.setheading(270)
        corp_jucator.setx(player.xcor())
        corp_jucator.sety(player.ycor())

        brat1_jucator.setx(player.xcor() + 18)
        brat1_jucator.sety(player.ycor() - 13)
        brat1_jucator.setheading(270)

        brat2_jucator.setx(player.xcor() - 18)
        brat2_jucator.sety(player.ycor() - 13)
        brat2_jucator.setheading(270)

        picior1_jucator.setheading(270)
        picior1_jucator.setx(player.xcor() + 9)
        picior1_jucator.sety(player.ycor() - 11)

        picior2_jucator.setheading(270)
        picior2_jucator.setx(player.xcor() - 9)
        picior2_jucator.sety(player.ycor() - 11)
    if player.heading()==180:
        corp_jucator.setheading(180)
        corp_jucator.setx(player.xcor())
        corp_jucator.sety(player.ycor())

        brat1_jucator.setx(player.xcor() - 13)
        brat1_jucator.sety(player.ycor() - 18)
        brat1_jucator.setheading(180)

        brat2_jucator.setx(player.xcor() - 13)
        brat2_jucator.sety(player.ycor() + 18)
        brat2_jucator.setheading(180)

        picior1_jucator.setheading(180)
        picior1_jucator.setx(player.xcor() - 11)
        picior1_jucator.sety(player.ycor() + 9)

        picior2_jucator.setheading(180)
        picior2_jucator.setx(player.xcor() - 11)
        picior2_jucator.sety(player.ycor() - 9)
    if player.heading()==0:
        corp_jucator.setheading(0)
        corp_jucator.setx(player.xcor())
        corp_jucator.sety(player.ycor())

        brat1_jucator.setx(player.xcor() + 13)
        brat1_jucator.sety(player.ycor() + 18)
        brat1_jucator.setheading(0)

        brat2_jucator.setx(player.xcor() + 13)
        brat2_jucator.sety(player.ycor() - 18)
        brat2_jucator.setheading(0)

        picior1_jucator.setheading(0)
        picior1_jucator.setx(player.xcor() + 11)
        picior1_jucator.sety(player.ycor() + 9)

        picior2_jucator.setheading(0)
        picior2_jucator.setx(player.xcor() + 11)
        picior2_jucator.sety(player.ycor() - 9)





################################################################################### def tepi virus
turtle.tracer(0)
tep1=Tep(virus.xcor(),virus.ycor(),180,latime_tep,lungime_tep)
tep2=Tep(virus.xcor(),virus.ycor(),150,latime_tep,lungime_tep)
tep3=Tep(virus.xcor(),virus.ycor(),120,latime_tep,lungime_tep)
tep4=Tep(virus.xcor(),virus.ycor(),90,latime_tep,lungime_tep)
tep5=Tep(virus.xcor(),virus.ycor(),60,latime_tep,lungime_tep)
tep6=Tep(virus.xcor(),virus.ycor(),30,latime_tep,lungime_tep)
tep7=Tep(virus.xcor(),virus.ycor(),0,latime_tep,lungime_tep)
tep8=Tep(virus.xcor(),virus.ycor(),-30,latime_tep,lungime_tep)
tep9=Tep(virus.xcor(),virus.ycor(),-60,latime_tep,lungime_tep)
tep10=Tep(virus.xcor(),virus.ycor(),-90,latime_tep,lungime_tep)
tep11=Tep(virus.xcor(),virus.ycor(),-120,latime_tep,lungime_tep)
tep12=Tep(virus.xcor(),virus.ycor(),-150,latime_tep,lungime_tep)

################################################################################### gat  def tepi virus
#####################################################################################fuctie tepi atasafi la virus
def set_tep():
    turtle.tracer(0)

    tep1.setx(virus.xcor())
    tep1.sety(virus.ycor())
    tep2.setx(virus.xcor())
    tep2.sety(virus.ycor())
    tep3.setx(virus.xcor())
    tep3.sety(virus.ycor())
    tep4.setx(virus.xcor())
    tep4.sety(virus.ycor())
    tep5.setx(virus.xcor())
    tep5.sety(virus.ycor())
    tep6.setx(virus.xcor())
    tep6.sety(virus.ycor())
    tep7.setx(virus.xcor())
    tep7.sety(virus.ycor())
    tep8.setx(virus.xcor())
    tep8.sety(virus.ycor())
    tep9.setx(virus.xcor())
    tep9.sety(virus.ycor())
    tep10.setx(virus.xcor())
    tep10.sety(virus.ycor())
    tep11.setx(virus.xcor())
    tep11.sety(virus.ycor())
    tep12.setx(virus.xcor())
    tep12.sety(virus.ycor())



################################################################################# gata fuctie tepi atasafi la virus
def distanta(x1,y1,x2,y2):
    d=(x2-x1)*(x2-x1) + (y2-y1)*(y2-y1)
    d=math.sqrt(d)
    return d


def muta_corp():
    turtle.tracer(0)
    corp_jucator.setx(player.xcor())
    corp_jucator.sety(player.ycor())
    corp_jucator.setheading(90)

    brat1_jucator.setx(player.xcor() - 18)
    brat1_jucator.sety(player.ycor() + 13)
    brat1_jucator.setheading(90)

    brat2_jucator.setx(player.xcor() + 18)
    brat2_jucator.sety(player.ycor() + 13)
    brat2_jucator.setheading(90)

    picior1_jucator.setheading(90)
    picior1_jucator.setx(player.xcor() - 9)
    picior1_jucator.sety(player.ycor() + 11)

    picior2_jucator.setheading(90)
    picior2_jucator.setx(player.xcor() + 9)
    picior2_jucator.sety(player.ycor() + 11)


def sus():
    turtle.tracer(0)
    player.setheading(90)

def jos():
    turtle.tracer(0)
    player.setheading(270)
def stanga():
    turtle.tracer(0)
    player.setheading(180)
def dreapta():
    turtle.tracer(0)
    player.setheading(0)
sanatos=True
def restrictii():
    turtle.tracer(0)

    if player.ycor()>170 and player.ycor()<220 and player.xcor()>-640 and player.xcor()<-380:
        player.sety(160)
        muta_corp()

    if player.xcor()<-380 and  player.xcor()>-430 and player.ycor()<360 and player.ycor()>170:
        player.setx(-370)
        muta_corp()

    if player.ycor()<90 and player.ycor()>40 and player.xcor()>-640 and player.xcor()<-380:
        player.sety(100)
        muta_corp()

    if player.xcor()<-380 and  player.xcor()>-430 and player.ycor()<90 and player.ycor()>-100:
        player.setx(-370)
        muta_corp()

    if player.ycor()>-100 and player.ycor()<-50 and player.xcor()>-640 and player.xcor()<-380:
        player.sety(-110  )
        muta_corp()

    if player.ycor()<-170 and player.ycor()>-220 and player.xcor()>-640 and player.xcor()<-380:
        player.sety(-160)
        muta_corp()

    if player.xcor()<-380 and  player.xcor()>-430 and player.ycor()<-170 and player.ycor()>-360:
        player.setx(-370)
        muta_corp()

    if player.xcor()>-310 and  player.xcor()<-260 and player.ycor()<360 and player.ycor()>170:
        player.setx(-320)
        muta_corp()

    if player.ycor()>170 and player.ycor()<220 and player.xcor()>-310 and player.xcor()<-50:
        player.sety(160)
        muta_corp()


    if player.xcor()<-50 and  player.xcor()>-100 and player.ycor()<360 and player.ycor()>170:
        player.setx(-40)
        muta_corp()

    if player.xcor()>-310 and  player.xcor()<-260 and player.ycor()<90 and player.ycor()>-100:
        player.setx(-320)
        muta_corp()

    if player.ycor()<90 and player.ycor()>40 and player.xcor()>-310 and player.xcor()<-50:
        player.sety(100)
        muta_corp()

    if player.xcor()<-50 and  player.xcor()>-100 and player.ycor()<90 and player.ycor()>-100:
        player.setx(-40)
        muta_corp()

    if player.ycor()>-100 and player.ycor()<-50 and player.xcor()>-310 and player.xcor()<-50:
        player.sety(-110)
        muta_corp()

    if player.xcor()>-310 and  player.xcor()<-260  and player.ycor()<-170 and player.ycor()>-360:
        player.setx(-320)
        muta_corp()

    if player.ycor()<-170 and player.ycor()>-120 and player.xcor()>-310 and player.xcor()<-50:
        player.sety(-160)
        muta_corp()

    if player.xcor()<-50 and  player.xcor()>-100  and player.ycor()<-170 and player.ycor()>-360:
        player.setx(-40)
        muta_corp()

    if player.xcor()>30 and  player.xcor()<80  and player.ycor()<360 and player.ycor()>170:
        player.setx(20)
        muta_corp()

    if player.ycor()>170 and player.ycor()<220 and player.xcor()>30 and player.xcor()<290:
        player.sety(160)
        muta_corp()

    if player.xcor()<290 and  player.xcor()>240  and player.ycor()<360 and player.ycor()>170:
        player.setx(300)
        muta_corp()

    if player.ycor()<90 and player.ycor()>40 and player.xcor()>30 and player.xcor()<290:
        player.sety(100)
        muta_corp()

    if player.xcor()>30 and  player.xcor()<80  and player.ycor()<90and player.ycor()>-100:
        player.setx(20)
        muta_corp()

    if player.ycor()>-100 and player.ycor()<-50 and player.xcor()>30 and player.xcor()<290:
        player.sety(-100)
        muta_corp()

    if player.xcor()<290 and  player.xcor()>240  and player.ycor()<90and player.ycor()>-100:
        player.setx(300)
        muta_corp()

    if player.xcor()>30 and  player.xcor()<80  and player.ycor()<-170 and player.ycor()>-360:
        player.setx(20)
        muta_corp()

    if player.ycor()<-170 and player.ycor()>-220 and player.xcor()>30 and player.xcor()<290:
        player.sety(-160)
        muta_corp()

    if player.xcor()<290 and  player.xcor()>240  and player.ycor()<-170 and player.ycor()>-360:
        player.setx(300)
        muta_corp()

    if player.xcor()>370 and  player.xcor()<420  and player.ycor()<-170 and player.ycor()>-360:
        player.setx(360)
        muta_corp()

    if player.ycor()<-170 and player.ycor()>-220 and player.xcor()>370 and player.xcor()<630:
        player.sety(-160)
        muta_corp()

    if player.ycor()>-100 and player.ycor()<-50 and player.xcor()>370 and player.xcor()<630:
        player.sety(-110)
        muta_corp()

    if player.xcor()>370 and  player.xcor()<420  and player.ycor()<90 and player.ycor()>-100:
        player.setx(360)
        muta_corp()


    if player.ycor()<90 and player.ycor()>50 and player.xcor()>370 and player.xcor()<630:
        player.sety(100)
        muta_corp()

    if player.ycor() > 170 and player.ycor() < 220 and player.xcor() > 370 and player.xcor() < 630:
        player.sety(160)
        muta_corp()


    if player.xcor()>370 and  player.xcor()<420  and player.ycor()<360 and player.ycor()>170:
        player.setx(360)
        muta_corp()

    if player.xcor()<-640:
        player.setx(620)
        muta_corp()
    if player.xcor()>630:
        player.setx(-630)
        muta_corp()
    if player.ycor()>360:
        player.sety(-350)

        muta_corp()
    if player.ycor()<-360:
        player.sety(350)
        muta_corp()

x=6
def inainte():
    turtle.tracer(5)

    cat_inainteaza_virusul=x
    ab = (distanta(player.xcor(), player.ycor(), virus.xcor(), virus.ycor()))
    if player.xcor()>virus.xcor() and player.ycor()>virus.ycor():
        a=(player.ycor()-virus.ycor())/ab
        b = math.asin(a)*180/math.pi
        u=b
        virus.setheading(u)
        virus.forward(cat_inainteaza_virusul)
    if player.xcor()<virus.xcor() and player.ycor()>virus.ycor():
        a=(player.ycor()-virus.ycor())/ab
        b = math.asin(a)*180/math.pi
        u=180-b
        virus.setheading(u)
        virus.forward(cat_inainteaza_virusul)
    if player.xcor()<virus.xcor() and player.ycor()<virus.ycor():
        a = (virus.ycor() - player.ycor()) / ab
        b = math.asin(a)*180/math.pi
        u = 180 +b
        virus.setheading(u)
        virus.forward(cat_inainteaza_virusul)
    if player.xcor()>virus.xcor() and player.ycor()<virus.ycor():
        a = (virus.ycor() - player.ycor()) / ab
        b = math.asin(a)*180/math.pi
        u = -b
        virus.setheading(u)
        virus.forward(cat_inainteaza_virusul)
    if player.xcor() == virus.xcor() and player.ycor()>virus.ycor():
        u = 90
        virus.setheading(u)
        virus.forward(cat_inainteaza_virusul)
    if player.ycor() == virus.ycor() and player.xcor()<virus.xcor():
        u = 180
        virus.setheading(u)
        virus.forward(cat_inainteaza_virusul)
    if player.xcor() == virus.xcor() and player.ycor()<virus.ycor():
        u = 270
        virus.setheading(u)
        virus.forward(cat_inainteaza_virusul)
    if player.ycor() == virus.ycor() and player.xcor()>virus.xcor():
        u = 0
        virus.setheading(u)
        virus.forward(cat_inainteaza_virusul)

    set_tep()






turtle.listen()
turtle.onkey(sus, 'Up')
turtle.onkey(jos, 'Down')
turtle.onkey(stanga, 'Left')
turtle.onkey(dreapta, 'Right')
turtle.onkey(arunca_seringa,'space')


sanatos=True
turtle.update()
while sanatos:
    turtle.update()

    ab = (distanta(player.xcor(), player.ycor(), virus.xcor(), virus.ycor()))
    restrictii()
    inainte()
    misca_player()

    inainte_seringa()
    if ab < 30:
        if nrvieti.lives>0:
            player.goto(0, 0)
            muta_corp()
            nrvieti.lives -= 1
            nrvieti.vieti()
            x=x+1
            z=z-3
        else:
            break

        virus.goto(xprim, yprim)
    if distanta(seringa.xcor(), seringa.ycor(), virus.xcor(), virus.ycor()) < 30:
        if seringa.status == "aruncat":
            seringa.status = "dupa_impact"
            seringa.hideturtle()
            virus.goto(xprim, yprim)
            game.score += 100
            game.show_status()
    if distanta(player.xcor(),player.ycor(),rezerva.xcor(),rezerva.ycor())<30:

        Rezerva_dispare()
        seringi.nrseringi+=1
        seringi.show_status()
    if distanta(player.xcor(),player.ycor(),antibiotic.xcor(),antibiotic.ycor())<30:

        Antibiotic_dispare()
        nrvieti.lives+=1
        nrvieti.vieti()
    Rezerva_apare()
    Antibiotic_apare()
    if nrvieti.lives==0:
        gameover.show_status()
        break




turtle.done()

