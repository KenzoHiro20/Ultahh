import turtle

def draw_rectangle(color, x, y, width, height):
    turtle.penup()
    turtle.goto(x, y)
    turtle.pendown()
    turtle.fillcolor(color)
    turtle.begin_fill()
    for _ in range(2):
        turtle.forward(width)
        turtle.left(90)
        turtle.forward(height)
        turtle.left(90)
    turtle.end_fill()

def draw_circle(color, x, y, radius):
    turtle.penup()
    turtle.goto(x, y - radius)
    turtle.pendown()
    turtle.fillcolor(color)
    turtle.begin_fill()
    turtle.circle(radius)
    turtle.end_fill()

def draw_candle(x, y):
    draw_rectangle("yellow", x, y, 10, 40)
    turtle.penup()
    turtle.goto(x + 5, y + 40)
    turtle.pendown()
    turtle.fillcolor("red")
    turtle.begin_fill()
    turtle.circle(5)
    turtle.end_fill()

def write_text(message, x, y, font_size, color):
    turtle.penup()
    turtle.goto(x, y)
    turtle.color(color)
    turtle.write(message, align="center", font=("Arial", font_size, "bold"))

def draw_birthday_cake():
    # Cake Base
    draw_rectangle("brown", -75, -100, 150, 100)

    # Top Layer
    draw_rectangle("pink", -50, 0, 100, 50)

    # Candles
    draw_candle(-40, 50)
    draw_candle(0, 50)
    draw_candle(40, 50)

# Setup Turtle Screen
turtle.setup(800, 600)
turtle.bgcolor("lightblue")
turtle.speed(3)

# Draw Happy Birthday Text
write_text("Happy Birthday Rhevy!", 0, 200, 24, "purple")

# Draw Cake
draw_birthday_cake()

# Hide Turtle and Finish
turtle.hideturtle()
turtle.done()
