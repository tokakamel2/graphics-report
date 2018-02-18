# graphics-report
from OpenGL.GL import *
from OpenGL.GLUT import *
from math import *
import numpy as np

def draw():
    glClearColor(0.9, 0.9, 0.9, 1)
    glClear(GL_COLOR_BUFFER_BIT)

    head()
    leg()
    arms()
    eyes()
    mouth()
    body()
    buttons()




    glFlush()


def body():

    glColor3d(1, 0.8, 0)
    glBegin(GL_POLYGON)
    glVertex2d(-0.37, 0.25)
    glVertex2d(0.37, 0.25)
    glVertex2d(0.37, -0.5)
    glVertex2d(-0.37, -0.5)
    glEnd()

def head():

    glBegin(GL_POLYGON)
    glColor3d(1,0.8,0)
    glVertex2d(0.3, 0.4)
    glVertex2d(-0.3, 0.4)
    glVertex2d(-0.3, 0.9)
    glVertex2d(0.3, 0.9)

    glEnd()


    glBegin(GL_POLYGON)
    glColor3d(0, 0, 0)
    glVertex2d(0.1, 0.25)
    glVertex2d(-0.1, 0.25)
    glVertex2d(-0.1, 0.4)
    glVertex2d(0.1, 0.4)

    glEnd()



def leg():
    glBegin(GL_POLYGON)
    glColor3d(0,0,0)
    glVertex2d(0.1, -0.5)
    glVertex2d(0.1, -0.95)
    glVertex2d(0.25, -0.95)
    glVertex2d(0.25, -0.5)

    glEnd()
    glBegin(GL_POLYGON)
    glColor3d(0, 0, 0)
    glVertex2d(-0.1, -0.5)
    glVertex2d(-0.1, -0.95)
    glVertex2d(-0.25, -0.95)
    glVertex2d(-0.25, -0.5)

    glEnd()

def arms():
    glBegin(GL_POLYGON)
    glColor3d(0,0,0)
    glVertex2d(0.37, 0.1)
    glVertex2d(0.65, 0.1)
    glVertex2d(0.65, -0.03)
    glVertex2d(0.37, -0.03)

    glEnd()

    glBegin(GL_POLYGON)
    glColor3d(0, 0, 0)
    glVertex2d(0.52, 0)
    glVertex2d(0.65, 0)
    glVertex2d(0.65, -0.2)
    glVertex2d(0.52, -0.2)

    glEnd()


# left arm

    glBegin(GL_POLYGON)
    glColor3d(0,0,0)
    glVertex2d(-0.37, 0.1)
    glVertex2d(-0.65, 0.1)
    glVertex2d(-0.65, -0.03)
    glVertex2d(-0.37, -0.03)

    glEnd()

    glBegin(GL_POLYGON)
    glColor3d(0, 0, 0)
    glVertex2d(-0.52, 0)
    glVertex2d(-0.65, 0)
    glVertex2d(-0.65, -0.2)
    glVertex2d(-0.52, -0.2)

    glEnd()



def eyes():

     glBegin(GL_POLYGON)
     glColor3d(1,1,1)

     for x in range (0,1000):
         glVertex2d(0.08* sin(x) +0.14, 0.08*cos(x)+0.7 )


     glEnd()

     glBegin(GL_POLYGON)
     glColor3d(1, 1, 1)

     for x in range(0, 360):
         glVertex2d(0.08 * sin(x) - 0.14, 0.08 * cos(x) + 0.7)

     glEnd()



     glBegin(GL_POLYGON)
     glColor3d(0, 0, 0)

     for x in range(0, 1000):
         glVertex2d(0.05 * sin(x) + 0.14, 0.05 * cos(x) + 0.7)

     glEnd()

     glBegin(GL_POLYGON)
     glColor3d(0, 0, 0)

     for x in range(0, 360):
         glVertex2d(0.05 * sin(x) - 0.14, 0.05 * cos(x) + 0.7)

     glEnd()




def mouth():
    glBegin(GL_POLYGON)

    glColor3d(0, 0, 0)
    glVertex2d(0.25, 0.45)
    glVertex2d(-0.25, 0.45)
    glVertex2d(-0.25, 0.55)
    glVertex2d(0.25, 0.55)

    glEnd()







def buttons():
    glColor3d(0, 0, 0)
    glBegin(GL_POLYGON)
    glVertex2d(-0.3, 0.2)
    glVertex2d(0.3, 0.2)
    glVertex2d(0.3, -0.45)
    glVertex2d(-0.3, -0.45)
    glEnd()

    glColor3d(1, 0.8, 0)
    glBegin(GL_POLYGON)
    glVertex2d(-0.27, 0.17)
    glVertex2d(0.27, 0.17)
    glVertex2d(0.27, -0.43)
    glVertex2d(-0.27, -0.43)
    glEnd()


    #lines










glutInit()
glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB)
glutCreateWindow(b"Robot Program")
glutInitWindowSize(100, 100)   # Set the window's initial width & height
glutDisplayFunc(draw)


glutMainLoop()

