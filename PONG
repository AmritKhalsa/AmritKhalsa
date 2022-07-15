from tkinter import *
import time
import random

def movement():
    def up(e):
        coord = canvas.coords(player1)
        if coord[1] > 0:
            canvas.move(player1, 0, -20)

    def down(e):
        coord = canvas.coords(player1)
        if coord[3] < 500:
            canvas.move(player1, 0, 20)

    def up2(e):
        coord = canvas.coords(player2)
        if coord[1] > 0:
            canvas.move(player2, 0, -20)

    def down2(e):
        coord = canvas.coords(player2)
        if coord[3] < 500:
            canvas.move(player2, 0, 20)

    window.bind('<w>', up)
    window.bind('<s>', down)
    window.bind('<Up>', up2)
    window.bind('<Down>', down2)


window = Tk()
window.configure(bg='black')
window.geometry('900x500')

canvas = Canvas(window, bg='black')
canvas.pack(expand=True, fill=BOTH)

player1 = canvas.create_rectangle(20, 0, 40, 60, fill='white')
player2 = canvas.create_rectangle(860, 0, 880, 60, fill='white')
ball = canvas.create_rectangle(440, 240, 460, 260, fill='white')

movement()

time_ = .035
x_v, y_v = 5, -5
while True:
    y = random.choice([0, 0, 5, 5, 5, 5, 5, 5, 5, 5, 5, 5, 10])
    x = random.choice([5, 5, 5, 5, 5, 5, 5, 5, 5, 5, 10, 10, 10, 10])
    cord_p1 = canvas.coords(player1)
    cord = canvas.coords(ball)
    cord_p2 = canvas.coords(player2)
    if cord[1] <= 0:
        y_v *= -1
    elif cord[3] >= 500:
        y_v *= -1
    if cord[0] <= 0:
        canvas.delete(ball)
        x_v *= -1
        time_ = .035
        ball = canvas.create_rectangle(440, 240, 460, 260, fill='white')
    elif cord[2] >= 900:
        canvas.delete(ball)
        x_v *= -1
        time_ = .035
        ball = canvas.create_rectangle(440, 240, 460, 260, fill='white')
    if cord[0] == 40:
        if cord_p1[1] <= cord[1] <= cord_p1[3] or cord_p1[1] <= cord[3] <= cord_p1[3]:
            print("yes")
            time_ -= .005
            x_v = x
            y_v = y
    if cord[0] == 840:
        if cord_p2[1] <= cord[1] <= cord_p2[3] or cord_p2[1] <= cord[3] <= cord_p2[3]:
            print("yes")
            time_ -= .005
            x_v = x * -1
            y_v = y

    canvas.move(ball, x_v, y_v)
    window.update()
    if time_ > 0:
        time.sleep(time_)
    else:
        time.sleep(.000001)

