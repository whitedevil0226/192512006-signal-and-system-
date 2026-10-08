% Test Case: Causal and Non-Causal Systems Analysis

clc;
clear;
close all;

% Define parameters
N = 20;                  % Number of samples
n = 0:N-1;               % Discrete-time index vector

% Input sequence: Unit step sequence
x_n = ones(1, N);

% Initialize output sequences
y_causal = zeros(1, N);
y_noncausal = zeros(1, N);

% --------------------------------
% Causal System
% y[n] = x[n] + 0.5*x[n-1]
% --------------------------------

for k = 1:N
    if k > 1
        y_causal(k) = x_n(k) + 0.5*x_n(k-1);
    else
        y_causal(k) = x_n(k);
    end
end

% --------------------------------
% Non-Causal System
% y[n] = 0.5*x[n] + 0.5*x[n+1]
% --------------------------------

for k = 1:N
    if k < N
        y_noncausal(k) = 0.5*x_n(k) + 0.5*x_n(k+1);
    else
        y_noncausal(k) = 0.5*x_n(k);
    end
end

% --------------------------------
% Plot the sequences
% --------------------------------

figure;

% Input sequence
subplot(3,1,1);
stem(n, x_n, 'filled');
grid on;
xlabel('n (Discrete Time Index)');
ylabel('Amplitude');
title('Input Sequence: Unit Step Sequence');

% Causal system output
subplot(3,1,2);
stem(n, y_causal, 'filled');
grid on;
xlabel('n (Discrete Time Index)');
ylabel('Amplitude');
title('Output Sequence: Causal System');

% Non-causal system output
subplot(3,1,3);
stem(n, y_noncausal, 'filled');
grid on;
xlabel('n (Discrete Time Index)');
ylabel('Amplitude');
title('Output Sequence: Non-Causal System');



<img width="1322" height="520" alt="Image" src="https://github.com/user-attachments/assets/0b4412d5-20b9-46c3-a100-fca1a1a86207" />
