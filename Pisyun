import turtle
import time
import math

oval_x = 200
oval_y = -60
screen = turtle.Screen()
screen.title("prod. by kochev ivan")
screen.bgcolor("black")
screen.setup(800, 600)
screen.tracer(0)

pen = turtle.Turtle()
pen.speed(-50000)
pen.hideturtle()
pen.width(3)

def hsv_to_rgb(h, s=1.0, v=1.0):
    h = h % 360
    c = v * s
    x = c * (1 - abs((h / 60) % 2 - 1))
    m = v - c
    
    if 0 <= h < 60:
        r, g, b = c, x, 0
    elif 60 <= h < 120:
        r, g, b = x, c, 0
    elif 120 <= h < 180:
        r, g, b = 0, c, x
    elif 180 <= h < 240:
        r, g, b = 0, x, c
    elif 240 <= h < 300:
        r, g, b = x, 0, c
    else:
        r, g, b = c, 0, x
    
    return (r + m, g + m, b + m)

def draw_circle(x, y, radius, color):
    pen.up()
    pen.goto(x, y - radius)
    pen.down()
    pen.color(color)
    pen.begin_fill()
    pen.circle(radius)
    pen.end_fill()

def draw_oval(x, y, width, height, color):
    pen.up()
    pen.goto(x - width/2, y)
    pen.down()
    pen.color(color)
    pen.begin_fill()
    
    pen.setheading(0)
    for _ in range(2):
        pen.circle(height, 90)
        pen.forward(width)
        pen.circle(height, 90)
    
    pen.end_fill()

def animate():
    hue = 0
    
    while True:
        pen.clear()
        
        current_color = hsv_to_rgb(hue)
        circle_color1 = hsv_to_rgb(hue + 120)
        circle_color2 = hsv_to_rgb(hue + 240)
        
        draw_circle(-100, -100, 80, circle_color1)
        draw_circle(100, -100, 80, circle_color2)
        
        draw_oval(oval_x, oval_y, 400, 100, current_color)
        
        screen.update()
        
        hue += 0.5
        if hue >= 360:
            hue = 0
        
        time.sleep(0.02)

try:
    animate()
except:
    pass
#KUDA PROPALO BELOYE GOVNO
