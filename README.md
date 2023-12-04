

#Задание 1


from drawbot_skia.drawbot import rect, oval, newPage, saveImage, fill, strokeWidth, stroke, newDrawing
rules = [1, 1, 2, 1, 1, 2, 0] * 5
w, h = 742.5, 1050
newPage(w, h)
margin = 80
x = margin
y = h - margin
step = (w - margin * 2) / 5
fill(None)
stroke(0, 0, 0)
strokeWidth(3)
for rule in rules:
    # круг, если правило == 0
    if rule == 2:
        oval(x, y - step, size, size)
    # квадрат, если правило == 1
    elif rule == 1:
        rect(x, y - step, size, size)
    # всё другое print в консоль
    else:
        print(rule, "<— неизвестное правило")
    # сдвинем x на шаг
    x += step

    # если строка кончилась, вернём x в начало, а y сдвинем вниз на шаг
    if x >= w - margin:
        x = margin
        y -= step
saveImage("draw1.pdf")

        # Задание 2
        

    # если y дошёл до низа страницы, создадим новую и обнулим координаты
    if y - step < margin:
        newPage(w, h)
        x = margin
        y = h - margin
        newDrawing()
rules = [1, 0, 2, 1, 0, 2, 0, 1] * 20
w, h = 742.5, 1050
newPage(w, h)

margin = 90
x = margin
y = h - margin

step = (w - margin * 2) / 6
size = step

for rule in rules:
    if rule == 0:
        fill(1, 0, 0, .5)
        stroke(0, 0, 0)
        strokeWidth(3)
        oval(x, y - step, size, size)
    elif rule == 1:
        fill(0, .5)
        stroke(0, 0, 0)
        strokeWidth(3)
        rect(x, y - step, size, size)
    elif rule == 2:
        fill(None)
        stroke(1, 0, 0)
        strokeWidth(3)
        oval (x, y - step, size, size)
    else:
        print(rule, "<— неизвестное правило")
    
    x += step

    if x >= w - margin:
        x = margin
        y -= step

    if y - step < margin:
        newPage(w, h)
        x = margin
        y = h - margin

saveImage("draw2.pdf")
