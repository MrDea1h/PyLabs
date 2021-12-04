//Задания 25.1, 25.2, 25.4
import random
import string

def pass_check(pass, m):
    up = 0
    digit = 0
    for char in pass:
        if char.isupper() == 1:
            up += 1
        if char.isdigit() == 1:
            digit += 1
    if up >= 1 and digit >= 1:
        print(pass)
    else:
        gen_pass(m)

def gen_pass(m):
    alphabet = string.ascii_letters + string.digits
    prohibited = ['l', 'I', '1', 'o', 'O', '0']
    pass = ''
    i = 0
    while i < m:
        char = random.choice(alphabet)
        if char not in prohibited:
            if char not in pass:
                pass += char
                i += 1
    pass_check(pass, m)

def main(n, m):
    for i in range(n):
        gen_pass(m)

//Задание 25.3
def precise_pi(n):
    k = 0.0
    for i in range(n):
        x = random.random()
        y = random.random()
        k += (x * x + y * y < 1.0)
    print(4 * k / n)

#Задание 26.1
from PIL import Image, ImageDraw
def gradient(color):
    img = Image.new("RGB", (512, 200), (0, 0, 0))
    grad = ImageDraw.Draw(img)
    r = 0
    g = 0
    b = 0
    for i in range(img.size[0]):
            grad.line((i, 0, i, 512), fill=(r, g, b), width=2)
            if i % 4 == 0:
                if color == "R":
                    r += 2
                elif color == "G":
                    g += 2
                elif color == "B":
                    b += 2
                elif color == "V":
                    r += 2
                    b += 2
                elif color == "C":
                    g += 2
                    b += 2
                elif color == "Y":
                    r += 2
                    g += 2
                else:
                    r += 2
                    g += 2
                    b += 2
    img.save("Gradient.png", "PNG")

//Задание 26.2
from PIL import Image
from PIL import ImageDraw
def board(num, size):
    new_color = (255, 255, 255)
    new_image = Image.new("RGB", (num * size, num * size), new_color)
    x = size * num
    y = x
    draw = ImageDraw.Draw(new_image)
    for i in range(0, x, size):
        if i % (size * 2) == 0:
            for j in range(0, y, size):
                if j % (size * 2) == 0:
                    draw.rectangle(
                        [i, j, i + size - 1, j + size - 1], fill='black')
        else:
            for j in range(size, y, size):
                if j % (size * 2) != 0:
                    draw.rectangle(
                        [i, j, i + size - 1, j + size - 1], fill='black')
    new_image.save('result.png', "PNG")


//Задание 26.3
def makeanaglyph(filename, delta):
    img = Image.open(filename)
    x, y = img.size
    res = Image.new('RGB', (x, y), (0, 0, 0))
    pixels2 = res.load()
    pixels = img.load()
    for i in range(x):
        for j in range(y):
            if i < delta:
                r, g, b = pixels[i, j]
                pixels2[i, j] = 0, g, b
            else:
                pixels2[i, j] = r, g, b
                g, b = pixels[i, j][1:]
                r = pixels[i - delta, j][0]
        res.save("anaglyph.jpg")

//Задание 26.4
from PIL import Image, ImageDraw
im = Image.open("lena.pgm")
draw = ImageDraw.Draw(im)
draw.line((0, 0) + im.size, fill=128)
draw.line((0, im.size[1], im.size[0], 0), fill=128)
del draw
# write to stdout
im.save(sys.stdout, "PNG")

//Задание 27.1
def make_preview(size, n_colors):
    img = Image.open("kek.jpg")
    x, y = img.size
    res = Image.new('RGB', (size), (0, 0, 0))
    res = img.thumbnail(size)
    res = img.quantize(n_colors)
    res.save("res.bmp", "BMP")

//Задание 27.2
def image_filter():
    img = Image.open("kek.jpg")
    red, green, blue = img.split()
    new_img = Image.merge("RGB", (blue, green, red))
    new_img.save("filter.jpg", "JPEG")

while 1:
    exec(input())
