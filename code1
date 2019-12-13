#!/usr/bin/env python

from random import shuffle
import RPi.GPIO as GPIO
import time 

turns=[67, 66, 67, 67, 66, 67]
card_motor_1 = 13
card_motor_2 = 11
card_motor_3 = 15
card_motor_4 = 12

lever_motor_1=31
lever_motor_2=33
lever_motor_3=29
lever_motor_4=35



BOTTOM_DOOR_PIN=37
TOP_DOOR_PIN=40
AIR_PUMP=38

def turnMotor(x, out1, out2, out3, out4):
  i=0
  positive=0
  negative=0
  y=0
  if x>0 and x<=400:
      for y in range(x,0,-1):
          if negative==1:
              if i==7:
                  i=0
              else:
                  i=i+1
              y=y+2
              negative=0
          positive=1
          #print((x+1)-y)
          if i==0:
              GPIO.output(out1,GPIO.HIGH)
              GPIO.output(out2,GPIO.LOW)
              GPIO.output(out3,GPIO.LOW)
              GPIO.output(out4,GPIO.LOW)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==1:
              GPIO.output(out1,GPIO.HIGH)
              GPIO.output(out2,GPIO.HIGH)
              GPIO.output(out3,GPIO.LOW)
              GPIO.output(out4,GPIO.LOW)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==2:  
              GPIO.output(out1,GPIO.LOW)
              GPIO.output(out2,GPIO.HIGH)
              GPIO.output(out3,GPIO.LOW)
              GPIO.output(out4,GPIO.LOW)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==3:    
              GPIO.output(out1,GPIO.LOW)
              GPIO.output(out2,GPIO.HIGH)
              GPIO.output(out3,GPIO.HIGH)
              GPIO.output(out4,GPIO.LOW)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==4:  
              GPIO.output(out1,GPIO.LOW)
              GPIO.output(out2,GPIO.LOW)
              GPIO.output(out3,GPIO.HIGH)
              GPIO.output(out4,GPIO.LOW)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==5:
              GPIO.output(out1,GPIO.LOW)
              GPIO.output(out2,GPIO.LOW)
              GPIO.output(out3,GPIO.HIGH)
              GPIO.output(out4,GPIO.HIGH)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==6:    
              GPIO.output(out1,GPIO.LOW)
              GPIO.output(out2,GPIO.LOW)
              GPIO.output(out3,GPIO.LOW)
              GPIO.output(out4,GPIO.HIGH)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==7:    
              GPIO.output(out1,GPIO.HIGH)
              GPIO.output(out2,GPIO.LOW)
              GPIO.output(out3,GPIO.LOW)
              GPIO.output(out4,GPIO.HIGH)
              time.sleep(0.03)
              #time.sleep(1)
          if i==7:
              i=0
              continue
          i=i+1
  
  
  elif x<0 and x>=-400:
      x=x*-1
      for y in range(x,0,-1):
          if positive==1:
              if i==0:
                  i=7
              else:
                  i=i-1
              y=y+3
              positive=0
          negative=1
          #print((x+1)-y) 
          if i==0:
              GPIO.output(out1,GPIO.HIGH)
              GPIO.output(out2,GPIO.LOW)
              GPIO.output(out3,GPIO.LOW)
              GPIO.output(out4,GPIO.LOW)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==1:
              GPIO.output(out1,GPIO.HIGH)
              GPIO.output(out2,GPIO.HIGH)
              GPIO.output(out3,GPIO.LOW)
              GPIO.output(out4,GPIO.LOW)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==2:  
              GPIO.output(out1,GPIO.LOW)
              GPIO.output(out2,GPIO.HIGH)
              GPIO.output(out3,GPIO.LOW)
              GPIO.output(out4,GPIO.LOW)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==3:    
              GPIO.output(out1,GPIO.LOW)
              GPIO.output(out2,GPIO.HIGH)
              GPIO.output(out3,GPIO.HIGH)
              GPIO.output(out4,GPIO.LOW)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==4:  
              GPIO.output(out1,GPIO.LOW)
              GPIO.output(out2,GPIO.LOW)
              GPIO.output(out3,GPIO.HIGH)
              GPIO.output(out4,GPIO.LOW)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==5:
              GPIO.output(out1,GPIO.LOW)
              GPIO.output(out2,GPIO.LOW)
              GPIO.output(out3,GPIO.HIGH)
              GPIO.output(out4,GPIO.HIGH)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==6:    
              GPIO.output(out1,GPIO.LOW)
              GPIO.output(out2,GPIO.LOW)
              GPIO.output(out3,GPIO.LOW)
              GPIO.output(out4,GPIO.HIGH)
              time.sleep(0.03)
              #time.sleep(1)
          elif i==7:    
              GPIO.output(out1,GPIO.HIGH)
              GPIO.output(out2,GPIO.LOW)
              GPIO.output(out3,GPIO.LOW)
              GPIO.output(out4,GPIO.HIGH)
              time.sleep(0.03)
              #time.sleep(1)
          if i==0:
              i=7
              continue
          i=i-1 



shuffled_deck=[i for i in range(6)]
shuffle(shuffled_deck)
shuffled_deck.append(0)

GPIO.setmode(GPIO.BOARD)
GPIO.setup(card_motor_1,GPIO.OUT)
GPIO.setup(card_motor_2,GPIO.OUT)
GPIO.setup(card_motor_3,GPIO.OUT)
GPIO.setup(card_motor_4,GPIO.OUT)
GPIO.setup(lever_motor_1,GPIO.OUT)
GPIO.setup(lever_motor_2,GPIO.OUT)
GPIO.setup(lever_motor_3,GPIO.OUT)
GPIO.setup(lever_motor_4,GPIO.OUT)
GPIO.setup(BOTTOM_DOOR_PIN, GPIO.OUT)
GPIO.setup(TOP_DOOR_PIN, GPIO.OUT)
GPIO.setup(AIR_PUMP, GPIO.OUT)

for x in turns:
      GPIO.output(lever_motor_1,GPIO.LOW)
      GPIO.output(lever_motor_2,GPIO.LOW)
      GPIO.output(lever_motor_3,GPIO.LOW)
      GPIO.output(lever_motor_4,GPIO.LOW)
      GPIO.output(card_motor_1,GPIO.LOW)
      GPIO.output(card_motor_2,GPIO.LOW)
      GPIO.output(card_motor_3,GPIO.LOW)
      GPIO.output(card_motor_4,GPIO.LOW)
      turnMotor(x, card_motor_1, card_motor_2, card_motor_3, card_motor_4)
      GPIO.output(TOP_DOOR_PIN, GPIO.HIGH)
      GPIO.output(AIR_PUMP, GPIO.HIGH
      time.sleep(2)
      turnMotor(-33, lever_motor_1, lever_motor_2, lever_motor_3, lever_motor_4)
      time.sleep(2)
      turnMotor(-83, lever_motor_1, lever_motor_2, lever_motor_3, lever_motor_4)
      GPIO.output(AIR_PUMP, GPIO.LOW)
      time.sleep(2)
      GPIO.output(TOP_DOOR_PIN, GPIO.LOW)
      turnMotor(116, lever_motor_1, lever_motor_2, lever_motor_3, lever_motor_4)
      
current_position=0
for card in shuffled_deck:

      print "Moving to card: {}".format(card+1)
      GPIO.output(card_motor_1,GPIO.LOW)
      GPIO.output(card_motor_2,GPIO.LOW)
      GPIO.output(card_motor_3,GPIO.LOW)
      GPIO.output(card_motor_4,GPIO.LOW)
      x=0
      while current_position != card:
        x+=turns[current_position]
        current_position+=1
        current_position%=6
      print "Number of steps: {}".format(x)
      current_position=card
      
      turnMotor(x, card_motor_1, card_motor_2, card_motor_3, card_motor_4)

      GPIO.output(37, GPIO.LOW)

      time.sleep(1)

      GPIO.output(37, GPIO.HIGH)
      time.sleep(1)
      GPIO.output(37, GPIO.LOW)

GPIO.cleanup()


