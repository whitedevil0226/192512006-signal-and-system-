% Test Case: Impulse Response of a Continuous-Time System
clear; clc; clf;

% Define time range and sampling interval 
t_min = -1; % Start time
t_max = 5;  % End time
dt = 0.01;  % Time step
t = t_min:dt:t_max; % Time vector

% Define the impulse function 
x_impulse = zeros(1, length(t));
x_impulse(t == 0) = 1; % Approximate impulse function

% Initialize the output signal with zeros 
y_impulse = zeros(1, length(t));

% Define the system parameters
a = 2; % Coefficient for y(t)
b = 1; % Coefficient for x(t)

% Compute the impulse response using the analytical solution
for i = 1:length(t)
    if t(i) >= 0
        y_impulse(i) = (b / a) * exp(-a * t(i));
    end 
end

% --- Plotting ---

% 1. Plot the input signal x(t) - Impulse Function
subplot(2,1,1);
plot(t, x_impulse, 'b', 'LineWidth', 1.5);
xlabel('t (Time)'); ylabel('x(t)');
title('Input Signal x(t) - Impulse Function');
xlim([-1 5]); ylim([0 1]);
xticks(-1:0.5:5);

% 2. Plot the impulse response y(t) of the System
subplot(2,1,2);
plot(t, y_impulse, 'r', 'LineWidth', 1.5);
xlabel('t (Time)'); ylabel('y(t)');
title('Impulse Response y(t) of the System');
xlim([-1 5]); ylim([0 0.5]);
xticks(-1:0.5:5);





<img width="1313" height="478" alt="Image" src="https://github.com/user-attachments/assets/899b0285-fff5-4aa5-8602-e42c76c55cc2" />
