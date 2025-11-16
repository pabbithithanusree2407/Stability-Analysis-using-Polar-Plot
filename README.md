# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
![WhatsApp Image 2025-11-16 at 19 23 12_33e53272](https://github.com/user-attachments/assets/78f7983c-6ace-4373-905d-bbfa0425732a)
![WhatsApp Image 2025-11-16 at 19 23 17_ffbc9dc7](https://github.com/user-attachments/assets/703c2505-f176-4f03-aa15-d890c00ef7f4)
![WhatsApp Image 2025-11-16 at 19 23 21_3d8aa3b5](https://github.com/user-attachments/assets/73645ce1-6ef8-4a37-a780-5f7d54a0209b)
![WhatsApp Image 2025-11-16 at 19 29 01_e60a6ba0](https://github.com/user-attachments/assets/5155503f-879b-4e6d-9946-7ec6af057430)


## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[1]
den=[conv(1,0),conv(1,0.5),conv(1,0.2)]
sys=tf(num,den)
w=logspace(-1,2,1000)
[mag phase]= bode(sys,w)
mag=squeeze(mag)
phase=squeeze(phase)
theta=deg2rad(phase)
polarplot(theta,mag,'LineWidth',1.5)
[gm pm wpc wgc]=margin(sys)
if (wpc > wgc)
    disp('stable')
elseif (wpc == wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```
## Output:
<img width="1211" height="1007" alt="Screenshot 2025-11-16 191311" src="https://github.com/user-attachments/assets/8d9565bb-eb2a-4f37-8d2b-b013258f0f54" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 3.57 dB

Phase Margin = 27.9 degrees

Gain crossover frequency = 1.76 rad/sec

Phase crossover frequency = 4.47 rad/sec

The system is  stable
