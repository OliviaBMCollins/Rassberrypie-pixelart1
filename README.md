# Rassberrypie-pixelart1
from sense_hat import SenseHat, ACTION_HELD
w = [225, 225, 225]
r = [225, 0, 0]
b = [0,0,225]



sense = SenseHat()
image1 = [
  w,w,w,w,w,w,w,w,
  w,r,r,r,r,r,r,w,
  w,r,w,w,r,w,w,r,
  w,r,w,w,r,w,w,r,
  w,r,r,r,r,r,r,w,
  w,w,w,w,w,w,w,w,
  w,r,r,r,r,r,r,w,
  w,w,w,w,w,w,w,w]

image2 = [
  b,b,b,b,b,b,b,b,
  b,r,r,r,r,r,r,b,
  b,r,r,r,r,r,r,b,
  b,r,r,r,r,r,r,b,
  b,b,b,b,b,b,b,b,
  b,r,r,r,r,r,r,b,
  b,b,b,b,b,b,b,b,
  b,b,b,b,b,b,b,b]
    
    

image3 = [
         w,b,w,w,b,w,w,b,
         b,w,b,b,w,b,b,w,
         w,b,w,w,b,w,w,b,
         b,w,b,b,w,b,b,w,
         w,b,w,w,b,w,w,b,
         b,w,b,b,w,b,b,w,
         w,b,w,w,b,w,w,b,
         b,w,b,b,w,b,b,w,
         ]

def downMenu(event):
  sense.clear()
  if event.action == ACTION_HELD:
    sense.set_pixels(image1)
    
def upMenu(event):
  sense.clear()
  if event.action == ACTION_HELD:
    sense.set_pixels(image2)

def rightMenu(event):
  sense.clear()
  if event.action == ACTION_HELD:
    sense.set_pixels(image3)
    
def leftMenu(event):
  sense.clear()
  temp = sense.temp
  temp_value = temp / 2.5 + 16
  pixels = [r if i < temp_value else w for i in range(64)]
  sense.set_pixels(pixels)

