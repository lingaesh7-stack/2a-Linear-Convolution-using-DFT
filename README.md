**EXPT 2a: LINEAR CONVOLUTION-USING-DFT**

**AIM:**

To perform and verify linear convolution operation of two given sequences using SCILAB.

**APPARATUS REQUIRED:**

PC installed with SCILAB

**PROGRAM:**

LINEAR CONVOLUTION

```clear;
clc;

// 1. Define Input Sequences
x = [1, 1, 1, 1];
h = [1, 2, 3, 4];

m = length(x);
n = length(h);

n_x = 0:(m-1);
n_h = 0:(n-1);

// 2. Linear Convolution (Manual Direct Formula Method)
len_y = m + n - 1;
y = zeros(1, len_y);

for i = 1:len_y
    for j = 1:m
        if ((i - j + 1) > 0) & ((i - j + 1) <= n) then
            y(i) = y(i) + x(j) * h(i - j + 1);
        end
    end
end

n_y = 0:(len_y-1);

// --- 3. Visualization Setup ---
figure(1);
clf();
bg_grid = color("gray95"); // Extremely faint, almost white grid

// Subplot 1: Input Signal x(n)
subplot(3, 1, 1);
plot2d3(n_x, x, style=2);
plot(n_x, x, 'ro', "MarkerFaceColor", "red", "MarkerSize", 6);
xtitle('Input Signal x(n)', 'Time (n)', 'Amplitude');
a = gca();
a.data_bounds = [-0.5, 0; 3.5, 2]; // Adds padding so 0 and 3 are clearly visible
xgrid(bg_grid);

// Subplot 2: Impulse Signal h(n)
subplot(3, 1, 2);
plot2d3(n_h, h, style=2);
plot(n_h, h, 'ro', "MarkerFaceColor", "red", "MarkerSize", 6);
xtitle('Impulse Signal h(n)', 'Time (n)', 'Amplitude');
a = gca();
a.data_bounds = [-0.5, 0; 3.5, 5]; // Adds padding for the peak at amplitude 4
xgrid(bg_grid);

// Subplot 3: Output Signal y(n)
subplot(3, 1, 3);
plot2d3(n_y, y, style=2);
plot(n_y, y, 'ro', "MarkerFaceColor", "red", "MarkerSize", 6);
xtitle('Linear Convolution Output y(n)', 'Time (n)', 'Amplitude');
a = gca();
a.data_bounds = [-0.5, 0; 6.5, 12]; // Extends x-axis to 6.5 to fit all output points
xgrid(bg_grid);
```

### CALCULATIONS:

<img width="1005" height="1600" alt="image" src="https://github.com/user-attachments/assets/4ca0e8b7-9c50-416c-8f86-0aee67ce8641" />
<img width="1076" height="1600" alt="image" src="https://github.com/user-attachments/assets/ba32b8f8-9d8d-4cd8-8bc7-14113acaf1f2" />


### SAMPLE OUTPUT:

<img width="1917" height="897" alt="image" src="https://github.com/user-attachments/assets/da96ee03-e440-4903-8870-594c551f4f3a" />


RESULT:

Thus, the linear convolution of the two given sequences were performed and its result was verified.
