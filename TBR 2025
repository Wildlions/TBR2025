from pybricks.hubs import PrimeHub
from pybricks.pupdevices import Motor, ColorSensor, UltrasonicSensor, ForceSensor
from pybricks.parameters import Button, Color, Direction, Port, Side, Stop
from pybricks.robotics import DriveBase
from pybricks.tools import wait, StopWatch

hub = PrimeHub()

from pybricks.hubs import PrimeHub
from pybricks.pupdevices import Motor, ColorSensor, UltrasonicSensor, ForceSensor
from pybricks.parameters import Button, Color, Direction, Port, Side, Stop
from pybricks.robotics import DriveBase
from pybricks.tools import wait, StopWatch
from umath import sin, cos, tan, pi

tempo = StopWatch()   
hub = PrimeHub()
direito = Motor(Port.D)
esquerdo = Motor(Port.B, Direction.COUNTERCLOCKWISE)
garra_esq = Motor(Port.C, Direction.COUNTERCLOCKWISE)
garra_dir = Motor(Port.E)
sensoresq = ColorSensor(Port.A)
sensordir = ColorSensor(Port.F)
mover = DriveBase(esquerdo, direito, 55, 80)
mover.use_gyro(True)
numero = 1
lancamento = 1
hub.system.set_stop_button(Button.BLUETOOTH)
sensoresq.lights.on(100)
sensordir.lights.on(100)
whiteLow = 95
whiteHigh = 100

def lerE():
    
    return(sensoresq.reflection())

def lerD():

    return(sensordir.reflection())

def andar(distancia, velocidade = 400):
    mover.settings(velocidade, 900, 900, 900)
    mover.straight(distancia*10)

def curva(graus, velocidade = 200):
    mover.settings(50, 600, 130, velocidade)
    mover.turn(graus)
    
def garraD(velocidade, tempo):
    garra_dir.run_time(velocidade, tempo)

def garraE(velocidade, tempo):
    garra_esq.run_time(velocidade, tempo)

def arco(raio, graus, velocidade = 300):

    mover.settings(velocidade, 400, 400, 400)
    mover.curve(raio, graus)
    
    
def esperar(tempo):
    mover.stop()
    wait(tempo*1000)
    mover.stop()

def estacionarB(velocidade):

    loop = True

    while loop == True:

        refE = lerE()
        refD = lerD()
        mover.drive(velocidade, 0)

        if refD >= whiteLow and refD <= whiteHigh:

            mover.stop()
            wait(1)
            loop = False

        if refE >= whiteLow and refE <= whiteHigh:

            mover.stop()
            wait(1)
            loop = False


while numero == 1:

    hub.display.number(lancamento)
    botao = hub.buttons.pressed()
    
    if Button.LEFT in botao: 

        if lancamento == 0:

            lancamamento = 0
            hub.display.number(lancamento)

        else:

            lancamento -= 1
            hub.display.number(lancamento)
            wait(250)
    
    if Button.RIGHT in botao:

        if lancamento == 99:

            lancamento = 99

        else:

            lancamento += 1
            hub.display.number(lancamento)
            wait(250)

    if Button.CENTER in botao:
        
        wait(300)

        if lancamento == 0:
            
            print("Bateria: ", hub.battery.voltage())
            mover.drive(1000, 0)

        if lancamento == 1:
           #missão 1 
            curva(19)
            garraE(4000, 343)
            andar(32)
            arco(70, 43)
            garraE(4000, 515)
            arco(1000, 18)
            curva(10)
            andar(50)
            estacionarB(400)
            curva(-30)
            andar(-15)
            #missão 2
            garraE(-4000, 610)
            garraE(-6000, 600)
            garraE(4000, 800)
            #missão 3
            curva(95)
            andar(-5)
            garraE(-4000, 950)
            andar(6)
            andar(2)
            garraE(4000, 360)
            curva(175)
            andar(-9)
            curva(90)
            andar(15)
            andar(-7)
            curva(35)
            andar(25)
            curva(-20)
            andar(20)

            mover.stop()
            
 
