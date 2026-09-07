# FIR-FILTER-DESIGN
# EXP 4 b: Design-of-FIR-Digital-Filter-using-Hamming-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Hamming-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
<br>clc ; 
<br>close ; 
<br>M=input('Enter the Odd Filter Length ='); 
<br>Wc=input('Enter the Digital Cut off frequency ='); 
<br>alpha= (M -1)/2 // Center Value 
<br>for n = 1:M 
<br>if (n ==alpha+1) 
<br>hd(n) = Wc/ %pi ; 
<br>else 
<br>hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
<br>end 
<br>end 
<br>// Hamming Window 
<br>for n = 1:M 
<br>W(n) = 0.54-(0.46*cos((2*%pi*(n-1))/(M-1))); 
<br>end 
<br>//Windowing filter coefficients 
<br>h = hd.*W; 
<br>disp(h,'Filter Coefficients are') 
<br>[hzm,fr]= frmag (h,256) ; 
<br>subplot(2 ,1 ,1) 
<br>plot(2*fr, hzm) 
<br>xlabel( ' Normalized Digital Frequency w'); 
<br>ylabel( 'Magnitude '); 
<br>title( ' Frequency Response of FIR LPF using Hamming Window ') 
<br>hzm_dB = 20* log10 (hzm); 
<br>subplot (2 ,1 ,2); 
<br>plot(2*fr , hzm_dB); 
<br>xlabel( ' Normalized Digital Frequency W' ); 
<br>ylabel( 'Magnitude in dB'); 
<br>title('Frequency Response of FIR LPF using Hamming Window');

# OUTPUT: 
<img width="557" height="349" alt="image" src="https://github.com/user-attachments/assets/398f540b-1dd3-4380-b902-20de21fe9a5c" />

<img width="458" height="376" alt="image" src="https://github.com/user-attachments/assets/c9152b9a-3fc8-44d6-9568-3dd92efb1cb3" />


# RESULT: 

Thus design of low pass FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
<br>clc ; 
<br>close ; 
<br>M=input('Enter the Odd Filter Length ='); 
<br>Wc=input('Enter the Digital Cut off frequency ='); 
<br>alpha= (M -1)/2 // Center Value 
<br>for n = 1:M 
<br>if (n ==alpha+1) 
<br>hd(n) =1-Wc/ %pi ; 
<br>else 
<br>hd(n) =-sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
<br>end 
<br>end 
<br>// Hamming Window 
<br>for n = 1:M 
<br>W(n) = 0.54-(0.46*cos((2*%pi*(n-1))/(M-1))); 
<br>end 
<br>//Windowing filter coefficients 
<br>h = hd.*W; 
<br>disp(h,'Filter Coefficients are') 
<br>[hzm,fr]= frmag (h,256) ; 
<br>subplot(2 ,1 ,1) 
<br>plot(2*fr, hzm) 
<br>xlabel( ' Normalized Digital Frequency w'); 
<br>ylabel( 'Magnitude '); 
<br>title( ' Frequency Response of FIR HPF using Hamming Window ') 
<br>hzm_dB = 20* log10 (hzm); 
<br>subplot (2 ,1 ,2); 
<br>plot(2*fr , hzm_dB); 
<br>xlabel( ' Normalized Digital Frequency W' ); 
<br>ylabel( 'Magnitude in dB'); 
<br>title('Frequency Response of FIR HPF using Hamming Window'); 


# OUTPUT: 
<img width="410" height="375" alt="image" src="https://github.com/user-attachments/assets/87fb6403-e2bb-4f52-aee5-65387a9a1baf" />

<img width="455" height="374" alt="image" src="https://github.com/user-attachments/assets/e11566fe-c60f-4db0-830d-858669a845b9" />


# RESULT: 
Thus design of HIGH pass FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =(Wc2-Wc1)/%pi ; 
else 
hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Hamming Window 
for n = 1:M 
W(n) = 0.54-(0.46*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Hamming Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Hamming Window');
```

# Manual Calculation :
<img width="1481" height="1600" alt="image" src="https://github.com/user-attachments/assets/0acd2cce-1f43-4518-9d56-e709324f0131" />
<img width="858" height="1427" alt="image" src="https://github.com/user-attachments/assets/54cf4022-f197-4819-b6dd-aa1559174ff1" />

# OUTPUT: 
<img width="760" height="700" alt="image" src="https://github.com/user-attachments/assets/93d54c70-5571-4829-a167-039499ffdfe5" />
<img width="573" height="776" alt="image" src="https://github.com/user-attachments/assets/cf31d6b8-016d-4b5f-a8c1-1b018401b74d" />


# RESULT: 
Thus design of BAND pass FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =1-((Wc2-Wc1)/%pi) ; 
else 
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Hamming Window 
for n = 1:M 
W(n) = 0.54-(0.46*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Hamming Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Hamming Window');
```
# OUTPUT: 
<img width="757" height="691" alt="image" src="https://github.com/user-attachments/assets/bafb5150-a6a1-476b-b966-f5d127897262" />
<img width="567" height="812" alt="image" src="https://github.com/user-attachments/assets/f41ab509-6fc5-4a80-9182-1bc6df29842f" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

# Manual Calculation :
<img width="1481" height="1600" alt="image" src="https://github.com/user-attachments/assets/0acd2cce-1f43-4518-9d56-e709324f0131" />
<img width="858" height="1427" alt="image" src="https://github.com/user-attachments/assets/54cf4022-f197-4819-b6dd-aa1559174ff1" />

# OUTPUT: 
<img width="760" height="700" alt="image" src="https://github.com/user-attachments/assets/93d54c70-5571-4829-a167-039499ffdfe5" />
<img width="573" height="776" alt="image" src="https://github.com/user-attachments/assets/cf31d6b8-016d-4b5f-a8c1-1b018401b74d" />
<img width="567" height="812" alt="image" src="https://github.com/user-attachments/assets/f41ab509-6fc5-4a80-9182-1bc6df29842f" />
