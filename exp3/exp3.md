% Test Case: Addition and Multiplication of Two Sequences

clc;
clear;
close all;

% Define parameters
N = 30;                  % Number of samples
n = 0:N-1;               % Discrete-time index vector

% -----------------------------
% Sequence 1: Sinusoidal
% -----------------------------
f1 = 0.05;               % Frequency in cycles/sample
A1 = 2;                  % Amplitude

x1_n = A1 * sin(2*pi*f1*n);

% -----------------------------
% Sequence 2: Exponentially Decaying
% -----------------------------
a2 = 0.1;                % Decay constant
A2 = 3;                  % Amplitude

x2_n = A2 * exp(-a2*n);

% -----------------------------
% Addition of the two sequences
% -----------------------------
x_add = x1_n + x2_n;

% -----------------------------
% Multiplication of the two sequences
% -----------------------------
x_mult = x1_n .* x2_n;

% -----------------------------
% Plot all sequences
% -----------------------------
figure;

% Sequence 1
subplot(4,1,1);
stem(n, x1_n, 'filled');
grid on;
xlabel('n (Discrete Time Index)');
ylabel('Amplitude');
title('Sequence 1: Sinusoidal Sequence');

% Sequence 2
subplot(4,1,2);
stem(n, x2_n, 'filled');
grid on;
xlabel('n (Discrete Time Index)');
ylabel('Amplitude');
title('Sequence 2: Exponentially Decaying Sequence');

% Addition
subplot(4,1,3);
stem(n, x_add, 'filled');
grid on;
xlabel('n (Discrete Time Index)');
ylabel('Amplitude');
title('Addition of Sequence 1 and Sequence 2');

% Multiplication
subplot(4,1,4);
stem(n, x_mult, 'filled');
grid on;
xlabel('n (Discrete Time Index)');
ylabel('Amplitude');
title('Multiplication of Sequence 1 and Sequence 2');





<img width="1326" height="526" alt="Image" src="https://github.com/user-attachments/assets/802dcca1-d6f6-4ae5-a582-e98ce2b93e35" />
