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
num=[10]
den=[0.1 0.7 1 0]
sys=tf(num,den)
[mag,phase,W]=bode(sys)
mag=squeeze(mag)
phase=squeeze(phase)
phase1=deg2rad(phase)
polarplot(phase1,mag,'linewidth',1.5)
grid on
[Gm Pm Wpc Wgc]=margin(sys)
if(Wpc>Wgc)
    disp('stable')
elseif(Wpc == Wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```

## Output:
<img width="1053" height="985" alt="image" src="https://github.com/user-attachments/assets/f808f1b8-23f9-4993-8d1e-6ce5237a09cb" />


## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.7 <br>
Phase Margin =-8.8865 degree <br>
Gain crossover frequency =3.7565 rad/s<br>
Phase crossover frequency =3.1623<br>
The system is unstable
