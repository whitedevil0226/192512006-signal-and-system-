% Test Case: Fourier Series of Half-Wave Rectifier Output

clc;
clear;
close all;

% Define parameters
A = 1;                  % Amplitude of input sinusoidal signal
f = 1;                  % Frequency in Hz
T = 1/f;                % Time period
dt = 0.01;              % Sampling interval
t = 0:dt:2*T;           % Time vector for two periods

% Generate input sinusoidal signal
x_t = A * sin(2*pi*f*t);

% Generate half-wave rectified output
y_t = max(x_t, 0);

% Number of harmonics
N_harmonics = 10;

% Calculate Fourier series coefficients over one period
t_one = 0:dt:T;
y_one = max(A * sin(2*pi*f*t_one), 0);

% DC coefficient
a0 = (2/T) * trapz(t_one, y_one);

% Initialize Fourier coefficients
an = zeros(1, N_harmonics);
bn = zeros(1, N_harmonics);

% Calculate cosine and sine coefficients
for n = 1:N_harmonics
    an(n) = (2/T) * trapz(t_one, ...
        y_one .* cos(2*pi*n*f*t_one));

    bn(n) = (2/T) * trapz(t_one, ...
        y_one .* sin(2*pi*n*f*t_one));
end

% Reconstruct the signal using Fourier series
y_reconstructed = (a0/2) * ones(size(t));

for n = 1:N_harmonics
    y_reconstructed = y_reconstructed ...
        + an(n) * cos(2*pi*n*f*t) ...
        + bn(n) * sin(2*pi*n*f*t);
end

% Plot the original half-wave rectified signal
figure;

subplot(3,1,1);
plot(t, y_t, 'r', 'LineWidth', 1.5);
grid on;
xlabel('Time (s)');
ylabel('Amplitude');
title('Half-Wave Rectified Output Signal');

% Plot the reconstructed signal
subplot(3,1,2);
plot(t, y_reconstructed, 'b', 'LineWidth', 1.5);
grid on;
xlabel('Time (s)');
ylabel('Amplitude');
title(['Fourier Series Reconstruction with ', ...
    num2str(N_harmonics), ' Harmonics']);

% Compare original and reconstructed signals
subplot(3,1,3);
plot(t, y_t, 'r', 'LineWidth', 1.5);
hold on;
plot(t, y_reconstructed, 'b--', 'LineWidth', 1.5);
grid on;
xlabel('Time (s)');
ylabel('Amplitude');
title('Original vs Reconstructed Signal');
legend('Original Signal', 'Reconstructed Signal');
hold off;






<img width="1390" height="546" alt="Image" src="https://github.com/user-attachments/assets/a13ae230-6fb2-493a-968d-b38440923478" />
