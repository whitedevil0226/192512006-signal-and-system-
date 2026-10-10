% Test Case: Analysis of a Continuous-Time System

clc;
clear;
close all;

% Define time range and sampling interval
t_min = -1;
t_max = 5;
dt = 0.01;
t = t_min:dt:t_max;

% Define system parameters
a = 2;
b = 1;

% ---------------------------------
% Input Signals
% ---------------------------------

% Unit impulse approximation with unit area
x_impulse = zeros(size(t));
x_impulse(t == 0) = 1/dt;

% Unit step signal
x_step = double(t >= 0);

% ---------------------------------
% Output for Impulse Input
% h(t) = b*exp(-a*t)*u(t)
% ---------------------------------

y_impulse = zeros(size(t));
idx = t >= 0;
y_impulse(idx) = b * exp(-a * t(idx));

% ---------------------------------
% Output for Step Input
% y(t) = (b/a)*(1-exp(-a*t))*u(t)
% ---------------------------------

y_step = zeros(size(t));
y_step(idx) = (b/a) * (1 - exp(-a * t(idx)));

% ---------------------------------
% Plot Input and Output Signals
% ---------------------------------

figure;

% Input impulse
subplot(4,1,1);
stem(t, x_impulse, 'b', 'filled');
grid on;
xlabel('Time (s)');
ylabel('x(t)');
title('Input Signal x(t) - Impulse Function');

% Output for impulse input
subplot(4,1,2);
plot(t, y_impulse, 'r', 'LineWidth', 1.5);
grid on;
xlabel('Time (s)');
ylabel('y(t)');
title('Output Signal y(t) for Impulse Input');

% Input step
subplot(4,1,3);
plot(t, x_step, 'b', 'LineWidth', 1.5);
grid on;
xlabel('Time (s)');
ylabel('x(t)');
title('Input Signal x(t) - Step Function');

% Output for step input
subplot(4,1,4);
plot(t, y_step, 'r', 'LineWidth', 1.5);
grid on;
xlabel('Time (s)');
ylabel('y(t)');
title('Output Signal y(t) for Step Input');



<img width="1323" height="507" alt="Image" src="https://github.com/user-attachments/assets/6b9ab33b-78d8-4210-b9ae-a135d5620702" />
