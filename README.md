# -Frequency-Modulation-and-Demodulation-using-NumPy-and-Matplotlib-

__Aim:__

To implement and analyze frequency modulation (FM) using Python's NumPy and Matplotlib libraries.

__Apparatus Required:__ 

1. Software: Python with NumPy and Matplotlib libraries
   
2. Hardware: Personal Computer

 
__Theory:__

Frequency Modulation (FM) is a method of transmitting information over a carrier wave by varying its 
frequency in accordance with the amplitude of the input signal (message signal). The frequency of the carrier 
wave is varied according to the instantaneous amplitude of the message signal.

__Algorithm:__

1. Initialize Parameters: Set the values for carrier frequency, message frequency, sampling frequency, and 
   frequency deviation.
   
2. Generate Time Axis: Create a time vector for the signal duration.
    
3. Generate Message Signal: Define the message signal as a cosine wave.
    
4. Compute the Integral of the Message Signal: Calculate the integral of the message signal over time.
    
5. Generate FM Signal: Apply the FM modulation formula to obtain the modulated signal.
 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

__Programme:__
```asm
import numpy as np
import matplotlib.pyplot as plt
Am = 12.7
Ac = 15.7
fm = 910
fc = 9100
fs = 91000
kf = 100
t = np.arange(0, 2/fm, 1/fs)
m = Am * np.cos(2 * np.pi * fm * t)
plt.subplot(3, 1, 1)
plt.plot(t, m)
c = Ac * np.cos(2 * np.pi * fc * t)
plt.subplot(3, 1, 2)
plt.plot(t, c)
integral_m = np.cumsum(m) / fs
s = Ac * np.cos(2 * np.pi * fc * t + 2 * np.pi * kf * integral_m)
plt.subplot(3, 1, 3)
plt.plot(t, s)
plt.tight_layout()
plt.show()
```
__Output:__

<img width="630" height="469" alt="image" src="https://github.com/user-attachments/assets/c29c620d-0c19-4e01-ba31-b80bcd1949eb" />

![WhatsApp Image 2025-11-22 at 17 45 45_0d591e02](https://github.com/user-attachments/assets/74e8a0cd-68c8-4cc2-8b9f-ffa2b80ef48a)

__Result:__

The message signal, carrier signal, and frequency modulated (FM) signal will be displayed in separate plots. The modulated signal will show frequency variations corresponding to the amplitude of the message signal.
