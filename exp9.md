% Test Case: Analysis of a Discrete-Time System

clc;
clear;
close all;

% Define the input signal x[n]
n = 0:20;                         % Discrete-time index
x_n = double(n >= 0 & n < 10);    % Rectangular pulse from n=0 to n=9

% Initialize the output signal
y_n = zeros(1, length(n));

% Define system coefficients
b = [0.5, 0.3, 0.2];

% Compute output using the difference equation
% y[n] = 0.5*x[n] + 0.3*x[n-1] + 0.2*x[n-2]

for i = 1:length(n)

    y_n(i) = b(1) * x_n(i);

    if i >= 2
        y_n(i) = y_n(i) + b(2) * x_n(i-1);
    end

    if i >= 3
        y_n(i) = y_n(i) + b(3) * x_n(i-2);
    end

end

% Plot the input signal
figure;

subplot(2,1,1);
stem(n, x_n, 'b', 'filled');
grid on;
xlabel('n (Discrete Time Index)');
ylabel('x[n]');
title('Input Signal x[n]');

% Plot the output signal
subplot(2,1,2);
stem(n, y_n, 'r', 'filled');
grid on;
xlabel('n (Discrete Time Index)');
ylabel('y[n]');
title('Output Signal y[n] of the System');


<img width="1335" height="521" alt="Image" src="https://github.com/user-attachments/assets/75c2380a-308a-42e2-ac90-c7d83e49520d" />
