# Polygon-Area-Calculator

Solution for Polygon Area Calculator
Close
×
PY
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def set_width(self, width):
        self.width = width

    def set_height(self, height):
        self.height = height

    def get_area(self):
        return self.width * self.height

    def get_perimeter(self):
        return 2 * self.width + 2 * self.height

    def get_diagonal(self):
        return (self.width ** 2 + self.height ** 2) ** 0.5

    def get_picture(self):
        if self.width > 50 or self.height > 50:
            return "Too big for picture."
        return (("*" * self.width + "\n") * self.height).rstrip() + "\n"

    def get_amount_inside(self, shape):
        return (self.width // shape.width) * (self.height // shape.height)

    def __str__(self):
        return f"Rectangle(width={self.width}, height={self.height})"


class Square(Rectangle):
    def __init__(self, side):
        super().__init__(side, side)

    def set_side(self, side):
        self.width = side
        self.height = side

    def set_width(self, width):
        self.set_side(width)

    def set_height(self, height):
        self.set_side(height)

    def __str__(self):
        return f"Square(side={self.width})"

# Usage example
rect = Rectangle(10, 5)
print(rect.get_area())           # Output: 50
rect.set_height(3)
print(rect.get_perimeter())      # Output: 26
print(rect)                      # Output: Rectangle(width=10, height=3)
print(rect.get_picture())        # Output: A rectangle of stars

sq = Square(9)
print(sq.get_area())             # Output: 81
sq.set_side(4)
print(sq.get_diagonal())         # Output: 5.656854249492381
print(sq)                        # Output: Square(side=4)
print(sq.get_picture())          # Output: A square of stars

rect.set_height(8)
rect.set_width(16)
print(rect.get_amount_inside(sq)) # Output: 8
Close
