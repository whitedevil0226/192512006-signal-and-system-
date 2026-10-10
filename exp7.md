% Test Case: Fourier Transform of a Rectangular Waveform

clc;
clear;
close all;

% Define time range and sampling interval
t_min = -5;
t_max = 5;
dt = 0.01;
t = t_min:dt:t_max;

% Define the rectangular waveform
A = 1;                      % Amplitude
tau = 2;                    % Pulse width
x_t = A * (abs(t) <= tau/2);

% Compute the Fourier Transform using FFT
N = length(t);
X_f = fft(x_t);

% Shift zero-frequency component to the center
X_f_shifted = fftshift(X_f);

% Define the correct frequency vector
Fs = 1/dt;                  % Sampling frequency
f = (-floor(N/2):ceil(N/2)-1) * (Fs/N);

% Approximate continuous-time Fourier Transform
X_f_shifted = X_f_shifted * dt;

% Calculate magnitude and phase
magnitude_X_f = abs(X_f_shifted);
phase_X_f = angle(X_f_shifted);

% Plot the original rectangular waveform
figure;

subplot(3,1,1);
plot(t, x_t, 'b', 'LineWidth', 1.5);
grid on;
xlabel('Time (s)');
ylabel('Amplitude');
title('Rectangular Waveform');

% Plot the magnitude of the Fourier Transform
subplot(3,1,2);
plot(f, magnitude_X_f, 'r', 'LineWidth', 1.5);
grid on;
xlabel('Frequency (Hz)');
ylabel('|X(f)|');
title('Magnitude of the Fourier Transform');

% Plot the phase of the Fourier Transform
subplot(3,1,3);
plot(f, phase_X_f, 'g', 'LineWidth', 1.5);
grid on;
xlabel('Frequency (Hz)');
ylabel('Phase of X(f) (radians)');
title('Phase of the Fourier Transform');




<img width="1326" height="520" alt="Image" src="https://github.com/user-attachments/assets/8e64ae5b-7bf1-42fe-a742-b077c2ff0a63" />
