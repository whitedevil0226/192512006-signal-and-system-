% Test Case: Discrete-Time Unit Impulse Signal Generation
clear; clc; close all;

% Define parameters
N  = 21;            % Length of the signal
n0 = 11;            % Index at which the impulse occurs

n = 1:N;            % Discrete time index vector

% Generate the unit impulse signal
x_n = zeros(1, N);  % Initialize signal with zeros
x_n(n0) = 1;        % Set the impulse at the desired location

% Plot the signal
figure('Color', 'w');                   % white figure background
plot(n, x_n, 'k');                      % black line
set(gca, 'Color', 'w');                 % white axes background
axis([0 22 0 1]);                       % axis limits
set(gca, 'XTick', 0:2:22, 'YTick', 0:0.1:1);
xlabel('n (Discrete Time Index)');
ylabel('Amplitude');
title('Discrete-Time Unit Impulse Signal');



<img width="1430" height="533" alt="Image" src="https://github.com/user-attachments/assets/8be1fbe3-6bd9-463a-b72a-f5028def6fef" />
