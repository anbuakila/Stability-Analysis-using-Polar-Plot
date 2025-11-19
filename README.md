# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
![5](https://github.com/user-attachments/assets/d5bf8c94-91fd-4cac-bf07-4eb45a144f4b)
![6](https://github.com/user-attachments/assets/b25e0e42-2614-4469-b434-1040fa4862b8)
![7](https://github.com/user-attachments/assets/a030a22b-45a7-4620-85f5-ccc78f46a10b)
<img width="944" height="1280" alt="image" src="https://github.com/user-attachments/assets/82f9be31-3cbe-44e5-9fb4-f02718f19800" />








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
<img width="1210" height="997" alt="Screenshot 2025-11-19 142220" src="https://github.com/user-attachments/assets/13f2405f-eb16-46d7-a1d6-3b4e0818b2cc" />



## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin =  7.0000 <br>
Phase Margin =  55.6412  degree <br>
Gain crossover frequency =  0.8979 rad/s<br>
Phase crossover frequency =  3.1623 <br>
The system is Stable
