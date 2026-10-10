% Test Case: Fourier Transform of a Periodic Impulse Train
clear; clc; clf;

% Define time range and sampling interval 
t_min = -5; % Start time
t_max = 5;  % End time
dt = 0.01;  % Time step
t = t_min:dt:t_max; % Time vector

% Define the periodic impulse train
T = 1;      % Period of the impulse train
A = 1;      % Amplitude of the impulses
% Use a small tolerance check to avoid floating-point precision errors with mod()
x_t = A * (abs(mod(t, T)) < 1e-9 | abs(mod(t, -T)) < 1e-9); 

% Compute the Fourier Transform using FFT 
X_f = fft(x_t); % Compute FFT of the signal 
N = length(t);  % Number of points in FFT
f = linspace(-1/(2*dt), 1/(2*dt), N); % Frequency vector

% Shift zero frequency component to the center 
X_f_shifted = fftshift(X_f);

magnitude_X_f = abs(X_f_shifted) / N; % Magnitude of the Fourier Transform 
phase_X_f = atan2(imag(X_f_shifted), real(X_f_shifted)); % Robust phase computation using atan2

% --- Plotting ---

% 1. Plot the original periodic impulse train 
subplot(3,1,1);
plot(t, x_t, 'b', 'LineWidth', 1.5);
xlabel('t (Time)'); ylabel('Amplitude'); 
title('Periodic Impulse Train');
xlim([-6 6]); ylim([0 1.2]);
grid on;

% 2. Plot the magnitude of the Fourier Transform 
subplot(3,1,2);
plot(f, magnitude_X_f, 'r', 'LineWidth', 1.5); 
xlabel('f (Frequency)'); ylabel('|X(f)|');
title('Magnitude of the Fourier Transform');
xlim([-60 60]); ylim([0 0.22]);
grid on;

% 3. Plot the phase of the Fourier Transform 
subplot(3,1,3);
plot(f, phase_X_f, 'g', 'LineWidth', 1.5);
xlabel('f (Frequency)'); ylabel('Phase of X(f)');
title('Phase of the Fourier Transform');
xlim([-60 60]); ylim([-2 2]);
grid on;






<img width="1343" height="495" alt="Image" src="https://github.com/user-attachments/assets/2dc1b401-3b10-412e-9a47-002ac0f0fd89" />
