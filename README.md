# Threading-
#In this actually simple code like square and cube and save it on creating file using file handling

import threading
import time

def sq(num):
    fp = open("square.txt","w")
    fp.write('********Calculates the sq of a number*********')
    for i in num:
        #Aritficial Dealay
        time.sleep(0.5)
        fp.write("\n")
        fp.write(str(i*i))
        
    fp.close()        
        
    fp.seek(0)
def cub(num):
    fp = open("cube.txt","w")
    fp.write('********Calculates the cube of a number********')
    for i in num:
        #Aritficial Dealay
        time.sleep(0.5)
        fp.write("\n")
        fp.write(str(i*i*i))
        
    fp.close()
        
      
        
l =[8,10,12,14,15,16]

t1 = threading.Thread(target=sq, args=(l,))
t2 = threading.Thread(target=cub, args=(l,))
        
#t1.start()
#t1.join()
t1.start()
t1.join()
 
t2.start()
t2.join()
print('Finished')

