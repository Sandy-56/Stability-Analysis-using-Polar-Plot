# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
Stability analysis using a polar plot is based on Nyquist stability criteria, where the open-loop frequency response G(jω)G(j\omega)G(jω) is plotted in the complex plane.


For the system G(s)=10s/(1+0.5s)(1+0.2s), the polar plot shows how the real and imaginary parts of the transfer function vary with frequency.


The main objective is to check whether the plot encircles the critical point (−1, 0)(-1,\,0)(−1,0), which determines closed-loop stability.


If there are no clockwise encirclements of −1+j0-1 + j0−1+j0, the system is stable for unity feedback.


MATLAB is used to generate the polar plot and verify stability by visually confirming encirclement conditions and validating Nyquist-based observations.





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
<img width="658" height="501" alt="image" src="https://github.com/user-attachments/assets/b742615c-60ee-4f29-b57c-e9ca290f6795" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.7
Phase Margin = -8.8865
Gain crossover frequency = 3.7565
Phase crossover frequency = 3.1623
The system is  Unstable.
