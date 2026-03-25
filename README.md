# Banganle-size-visualizer
# Description This project generates circles based on a given radius or diameter to visualize bangle sizes.  It helps users compare different sizes by displaying circles similar to those used in jewellery shops.  The program is implemented in Python using the Turtle graphics library to draw and label the circles.
# =====================================================
# Project: Bangle Size Visualizer
# Author: Dhanyashree P
#
# Description:
# This Python program draws circles to represent bangle sizes.
# The user can enter either radius or diameter, and the program
# will generate a circle accordingly. It can also display
# multiple standard bangle sizes for comparison.
#
# Technology Used:
# Python Turtle Graphics

this is my own idea and i took the help of chatboot to create a program
# =====================================================

import turtle   # Import turtle module for drawing graphics


# Function to draw a circle using user input
def draw_circle():
    
    # Ask the user whether they want to enter radius or diameter
    choice = input("Enter 'r' for radius or 'd' for diameter: ").lower()
    
    if choice == 'r':
        radius = float(input("Enter the radius: "))
        
    elif choice == 'd':
        diameter = float(input("Enter the diameter: "))
        radius = diameter / 2   # Convert diameter to radius
        
    else:
        print("Invalid choice")
        return

    # Create turtle object
    pen = turtle.Turtle()
    pen.speed(3)

    # Draw the circle
    pen.circle(radius)

    # Write label below the circle
    pen.penup()
    pen.goto(0, -radius - 20)
    pen.write(f"Radius: {radius}", align="center", font=("Arial", 12, "normal"))


# Function to display standard bangle sizes
def show_bangle_sizes():

    pen = turtle.Turtle()
    pen.speed(3)

    # Standard bangle diameters
    sizes = [2.2, 2.4, 2.6, 2.8]

    x_position = -200

    for size in sizes:

        pen.penup()
        pen.goto(x_position, 0)
        pen.pendown()

        radius = size * 20   # Scale for screen display
        pen.circle(radius)

        # Write the size label
        pen.penup()
        pen.goto(x_position, -20)
        pen.write(f"Size {size}", align="center", font=("Arial", 10, "normal"))

        x_position += 120


# Main program menu
print("===== Bangle Size Visualizer =====")
print("1. Draw circle using radius/diameter")
print("2. Show standard bangle sizes")

option = input("Enter your choice (1 or 2): ")

if option == '1':
    draw_circle()

elif option == '2':
    show_bangle_sizes()

else:
    print("Invalid option")

# Keep the window open
turtle.done()
