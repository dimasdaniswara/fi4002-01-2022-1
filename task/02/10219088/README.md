# 10219088 Dimas Fasdhia D
NamaLengkap


## materi sebelumnya
+ Persamaan diferensial , predator-prey, lorentz attractor
+ Monte carlo
+ Runge-kuta orde 4
+ DFT & FFT
+ Matriks Temperatur
+ Metode Euler
+ Rekursif faktorial



## materi paling menarik
+ Materi yang paling menarik adalah adalah persamaan predator-prey karena dapat mensimulasikan ketika suatu populasi memiliki banyak predator dan ketika sedikit predator


## materi paling membosankan
+ Osilasi Harmonik 


## materi yang sudah dipami
+ Predator Prey
+ Monte Carlo
+ Runge-kuta order 4


## materi yang belum dipahami
+ DFT & FFT
+ Matriks Temperatur
+ Metode Euler
+ Rekursif faktorial


## contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarnnya.

```python
# Mendefinisikan library
import numpy as np
import matplotlib.pyplot as plt

def F(t, x, y):
    return (-x + (x * y), y - (x * y))
    
# Mendefinisikan euler method
def eulerMethod(t_0, t_n, num_steps, x_0, y_0):
    h = abs(t_n - t_0)/num_steps
    t = np.linspace(t_0, t_n, num_steps + 1)
    x = np.zeros(num_steps + 1)
    y = np.zeros(num_steps + 1)
    x[0] = x_0
    y[0] = y_0
    for k in range(0, num_steps):
        (dx, dy) = F(t[k], x[k], y[k])
        x[k + 1] = x[k] + h * dx
        y[k + 1] = y[k] + h * dy
    return (x, y)
    
    
# Mendefinisikan Runge Kutta method
def rungeKutta(t_0, t_n, num_steps, x_0, y_0):
    h = abs(t_n - t_0)/num_steps
    t = np.linspace(t_0, t_n , num_steps + 1)
    x = np.zeros(num_steps + 1)
    y = np.zeros(num_steps + 1)
    x[0] = x_0
    y[0] = y_0
    for k in range(0, num_steps):
        (x1, y1) = F(t[k], x[k], y[k])
        (x2, y2) = F(t[k] + h/2, x[k] + x1 * h/2, y[k] + y1 * h/2)
        (x3, y3) = F(t[k] + h/2, x[k] + x2 * h/2, y[k] + y2 * h/2)
        (x4, y4) = F(t[k] + h, x[k] + x3 * h, y[k] + y3*h)
        x[k + 1] = x[k] + h * (x1 + 2 * x2 + 2 * x3 + x4)/6
        y[k + 1] = y[k] + h * (y1 + 2 * y2 + 2 * y3 + y4)/6
    return (x,y)
    
# Input nilai parameter yang dibutuhkan
t_0 = 0
t_n = 100
x_0 = 0.3
y_0 = 2
num_steps = 3000

# Plotting grafik yang diperoleh berdasarkan
# persamaan euler untuk visualisasi predator - prey
plt.figure(1)
(x_pt,y_pt) = eulerMethod(t_0, t_n, num_steps, x_0, y_0)
plt.plot(x_pt,y_pt,color='blue',label='Euler')
plt.title('Grafik Populasi Predator Terhadap Mangsa - Persamaan Euler')
plt.xlabel('Populasi Predator')
plt.ylabel('Populasi Mangsa')
plt.axis([-1, 5, -1, 5])
plt.savefig('Figure (1) Grafik Predator - Prey berdasarkan Persamaan Euler.png')
```

Hasilnya adalah


<img width="230" alt="Cuplikan layar 2022-10-19 100938" src="https://user-images.githubusercontent.com/67426210/196588506-3b24d013-a078-4a7f-ac28-acc142da8c2a.png">




## cara perkuliahan
+ Menuru saya perkuliahan selama ini cukup membosankan karena kebanyakan teori dan praktik nya kurang . Sehingga lebih baik jika perkuliahan diadakan di Labcom agar mahasiswa juga memiliki banyak pengalaman hands-on


## topik sistem fisis
+ Tuliskan sistem fisis yang menarik bagi Anda untuk dikaji lebih dalam dan jelaskan alasannya mengapa.
+ Pasar saham menurut saya suatu sistem fisis yang menarik untuk di kaji , karena terdapat banyak aktor dan variabel yang mempengaruhi pasar saham dengan cara yang tidak terduga dan dapat memberikan dampak yang berbeda-beda sehingga pasar saham dapat dikaji dengan berbagai sudut pandang .  


## simulasi dan visualisasi
+ Apakah Anda tertarik dengan simulasi dan visualisasi? Jelaskan topik yang ingin Anda simulasikan / visualisasikan serta cantumkan alasannya dan perkiraan pusataka Python yang perlu digunakan.
+ tidak tertarik
