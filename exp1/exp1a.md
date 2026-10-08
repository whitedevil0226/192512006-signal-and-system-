% Test Case: Sinusoidal Signal Generation

% Define parameters
f = 5;                  % Frequency in Hz
A = 2;                  % Amplitude
phi = pi/4;             % Phase shift in radians

% Time vector from 0 to 1 second
t = 0:0.001:1;

% Generate the sinusoidal signal
x_t = A * sin(2 * pi * f * t + phi);

% Plot the signal
figure;
plot(t, x_t, 'LineWidth', 1.5);
grid on;

% Add labels and title
xlabel('Time (s)');
ylabel('Amplitude');
title('Continuous Time Sinusoidal Signal');



<img width="1311" height="521" alt="Image" src="https://github.com/user-attachments/assets/f55a7250-e2bf-4fa9-9deb-8bc922008028" />
