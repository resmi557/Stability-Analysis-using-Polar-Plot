# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
<img width="517" height="846" alt="image" src="https://github.com/user-attachments/assets/2f5b066f-44a2-433f-9e49-d2492ae78948" />
## Graph:
<img width="565" height="846" alt="image" src="https://github.com/user-attachments/assets/115e54d4-e9ac-4004-b87e-6fe5d5775da2" />




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
den = conv([1 0], conv([0.5 1], [0.2 1]));
sys=tf(num,den)
w=logspace(-1,2,1000);
[mag phase]=bode(sys,w);
mag=squeeze(mag);
phase=squeeze(phase);
theta=deg2rad(phase);
polarplot(theta,mag,'LineWidth',1.5)
[gm pm wpc wgc]=margin(sys)
if (wpc>wgc)
    disp('stable')
elseif (wpc==wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```
## Output:
<img width="697" height="620" alt="image" src="https://github.com/user-attachments/assets/08a06773-967e-4692-ae98-c860b9ec5de0" />


## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.7000 dB<br>
Phase Margin = 55.6412 deg<br>
Gain crossover frequency =0.8979 rad/sec <br>
Phase crossover frequency =3.1623 rad/sec <br>
The system is stable
 

