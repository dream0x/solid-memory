import turtle
import random

# Налаштування черепахи
tree = turtle.Turtle()
tree.speed(0)
tree.hideturtle()
tree.color("green")
tree.pensize(2)

# Функція малювання гілки
def draw_branch(t, branch_length):
    if branch_length > 5:
        angle = random.randint(15, 45)
        reduction = random.randint(10, 20)
        t.forward(branch_length)
        t.right(angle)
        draw_branch(t, branch_length - reduction)
        t.left(2 * angle)
        draw_branch(t, branch_length - reduction)
        t.right(angle)
        t.backward(branch_length)

# Початок малювання дерева
tree.penup()
tree.goto(0, -250)
tree.left(90)
tree.pendown()

draw_branch(tree, 100)

# Завершення
screen.exitonclick()
