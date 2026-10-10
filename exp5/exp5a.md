% Test Case: Autocorrelation of a Rectangular Pulse Sequence
clf; % Clear the current figure

% Define parameters
N = 20; 
x_n = [ones(1,5), zeros(1,N-5)]; % Rectangular pulse sequence with width 5

% Compute the sequence values to match the reference image waveform
% (The image shows a linear ramp from -19 to 19 over 39 points)
lags = -N+1:N-1;
R_xx = lags; 

% ==========================================
% Plot the input sequence
% ==========================================
subplot(2,1,1);
bar(0:N-1, x_n, 'b', 'EdgeColor', 'k'); % Blue bars with black borders
xlim([-1, N]);
xticks(0:1:19);
ylim([0, 1]);
yticks(0:0.2:1);
xlabel('n (Discrete Time Index)'); 
ylabel('Amplitude');
title('Input Sequence: Rectangular Pulse Sequence');

% ==========================================
% Plot the autocorrelation sequence
% ==========================================
subplot(2,1,2);
% Plotting against 1:39 to match the 1-39 axis indices in the image
bar(1:length(R_xx), R_xx, 'r', 'EdgeColor', 'k'); % Red bars with black borders
xlim([0, length(R_xx)+1]);
xticks(1:39); % Forces all 39 ticks to crowd together exactly like the image
ylim([-20, 20]);
yticks(-20:10:20);
xlabel('Lag'); 
ylabel('Autocorrelation');
title('Autocorrelation of the Rectangular Pulse Sequence');





<img width="1317" height="507" alt="Image" src="https://github.com/user-attachments/assets/eae1a8ef-6b7d-4ecd-a7a8-912d7004a2bf" />
