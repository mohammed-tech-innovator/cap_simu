#my frind asked me abount sum problem in electrical engineering
#the problem is aboum a capacitor in a room
#its required to measure the humidity in the room as a function of the capacity
#my frind asked me about what the wetness capacity relation will look like 
#the code will caluclate the equivlant permittivity according to the model used
#the model is based on dividing the volume insid the capacitor into n^3 equal cubes
#the water is randomly distributed inside the volume
import random
import numpy as np
import matplotlib.pyplot as plt
def simulation(w,n):
        temp = np.random.randint(0,100,(n,n,n))#the water particles are randomly distributed inside the volume
        volume = np.zeros((n,n,n))#assume a cube shaped capacitor 
        for i in range(n):
                for j in range (n):
                        for k in range(n):
                                if (temp[i][j][k] < w) :
                                        ((volume[i])[j])[k] = 1
                                
        return volume# 1=water 0=air
def calculate_e(v,e0,e1,n):
        etotal = 0#equilant permittivity
        for i in range(n):
                for j in range(n):
                        temp = 0
                        for k in range(n):
                                if (v[i][j][k] == 0):
                                        temp = temp + 1/((e0))
                                if (v[i][j][k] == 1):
                                        temp = temp + 1/((e1))
                        temp = n*temp
                        etotal = etotal + 1/(temp)
        return etotal
        
n = 25 #resolution 
e0=1#air permittivity
e1=80#water permittivity
w =np.arange(start=0,stop=101,step=0.5)#wetness array
e = []#permittivity array
for i in w :
        volume = simulation(i,n)
        e.append(calculate_e(volume,e0,e1,n))
plt.plot(w,e)
plt.ylabel('permittivity')
plt.xlabel('wetness % of volume')
plt.show()
#plotting results
