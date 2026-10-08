% Test Case: Generation of Periodic and Aperiodic Signals

clc;
clear;
close all;

% -----------------------------
% Periodic Signal
% -----------------------------

f_periodic = 1;              % Frequency in Hz
A_periodic = 1;              % Amplitude
t_periodic = 0:0.01:2;       % Time from 0 to 2 seconds

% Generate periodic sinusoidal signal
x_periodic = A_periodic * sin(2*pi*f_periodic*t_periodic);

% -----------------------------
% Aperiodic Signal
% -----------------------------

a_aperiodic = 0.5;           % Decay constant
A_aperiodic = 2;              % Amplitude
t_aperiodic = 0:0.01:2;       % Time from 0 to 2 seconds

% Generate aperiodic exponentially decaying signal
x_aperiodic = A_aperiodic * exp(-a_aperiodic*t_aperiodic);

% -----------------------------
% Plot Signals
% -----------------------------

figure;

% Periodic signal
subplot(2,1,1);
plot(t_periodic, x_periodic, 'LineWidth', 1.5);
grid on;
xlabel('Time (s)');
ylabel('Amplitude');
title('Periodic Signal - Sinusoidal Wave (1 Hz)');

% Aperiodic signal
subplot(2,1,2);
plot(t_aperiodic, x_aperiodic, 'LineWidth', 1.5);
grid on;
xlabel('Time (s)');
ylabel('Amplitude');
title('Aperiodic Signal - Exponentially Decaying Signal');   



<img width="1330" height="532" alt="Image" src="https://github.com/user-attachments/assets/d2543d19-ace7-4ff2-8710-f5c3dc19a757" />





