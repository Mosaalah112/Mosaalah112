- 👋 Hi, I’m @Mosaalah112
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Mosaalah112/Mosaalah112 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
clc;clear
%Givens:-
r=0.03;
L=1;
T_alpha1=100;
T_alpha2=25;
Delta_T=T_alpha1-T_alpha2;
h=5;
%---------------------------------------------------------------------------------------
%General Forms:-
%A_before=2*pi*r*L;
%A_after=2*pi*R*L;
%Volume=pi*(R-r)^2*L;
%Cost_Total=Cost*Volume
Q_loss_before=(Delta_T)/(1/(h*2*pi*r*L));
Q_loss_after=0.5*Q_loss_before;
%Material A: 
syms R_A
K_A=0.5; 
Cost_A=1000;
R_A = solve (Q_loss_after == (Delta_T)./((1./(2*pi.*R_A*L*h))+(log(R_A./r))/(2*pi*K_A*L)))
Cost_Total_A = Cost_A*pi*L.*(R_A-r).^2
%----------------------------------------------------------------------------------------
%Material B: 
syms R_B
K_B=0.4; 
Cost_B=3000;
R_B = solve (Q_loss_after == (Delta_T)./((1./(2*pi.*R_B*L*h))+(log(R_B./r))/(2*pi*K_B*L)))
Cost_Total_B = Cost_B*pi*L.*(R_B-r).^2
%----------------------------------------------------------------------------------------
%Material C: 
syms R_C
K_C=0.3; 
Cost_C=5000;
R_C = solve (Q_loss_after == (Delta_T)./((1./(2*pi.*R_C*L*h))+(log(R_C./r))/(2*pi*K_C*L)))
Cost_Total_C = Cost_C*pi*L.*(R_C-r).^2
%----------------------------------------------------------------------------------------
%Material D: 
syms R_D
K_D=0.2; 
Cost_D=8000;
R_D = solve (Q_loss_after == (Delta_T)./((1./(2*pi.*R_D*L*h))+(log(R_D./r))/(2*pi*K_D*L)))
Cost_Total_D = Cost_D*pi*L.*(R_D-r).^2
%----------------------------------------------------------------------------------------
%Material E: 
syms R_E
K_E=0.05; 
Cost_E=15000;
R_E = solve (Q_loss_after == (Delta_T)./((1./(2*pi.*R_E*L*h))+(log(R_E./r))/(2*pi*K_E*L)))
Cost_Total_E = Cost_E*pi*L.*(R_E-r).^2
