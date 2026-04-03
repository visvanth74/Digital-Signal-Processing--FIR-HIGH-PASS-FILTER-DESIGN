# Digital-Signal-Processing--FIR-HIGH-PASS-FILTER-DESIGN
## AIM:
To generate design of High pass FIR digital filter using Window.
## Software Required:
MAT LAB R2012.
## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the hIGH Pass filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM: 
% P.S.VISVANTH 212223050061
clc; % clear screen
clear all; % clear variables
close all; % close all figure windows

wc = input('Enter the value of cut off frequency: ');
N = input('Enter the value of filter (M+1): ');

alpha = (N-1)/2;
eps = 0.001;

% High Pass Filter Coefficient
n = 0:1:N-1;
hd = (sin(pi*(n-alpha+eps)) - sin((n-alpha+eps)*wc)) ./ (pi*(n-alpha+eps));

% Bartlett Window Sequence
n = 0:1:N-1;
wb = 1 - 2*abs((n - alpha)/N);

% Windowed impulse response
hn = hd .* wb;

% Frequency response
w = 0:0.01:pi;
h = freqz(hn,1,w);

% Plot
plot(w/pi, abs(h), 'blue');
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('High Pass Filter using Bartlett Window');
grid on;
## OUTPUT:

## RESULT:
