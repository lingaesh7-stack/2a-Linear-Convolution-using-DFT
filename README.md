### EXPT 2a: LINEAR CONVOLUTION-USING-DFT
### AIM
To perform and verify linear convolution operation of two given sequences using SCILAB.

### APPARATUS REQUIRED
PC installed with SCILAB

### PROGRAM:
LINEAR CONVOLUTION
```
clc;
clear;
x = [1 1 1 1];
h = [1 2 3 4];
m = length(x);
n = length(h);
a=0:1:m-1;
b=0:1:n-1;
subplot(3,1,1);
plot2d3(a,x);
xlabel('Time');
ylabel('Amplitude');
title('Graphical Representation of Input Signal X');
subplot(3,1,2);
plot2d3(b,h);
xlabel('Time');
ylabel('Amplitude');
title('Graphical Representation of Impulse Signal h');
for i = 1: n+m-1
conv_sum = 0;
for j = 1:i
if (((i-j+1) <= n)&(j <=m))
conv_sum = conv_sum + x(j)*h(i-j+1);
end;
y(i) = conv_sum;
end;
end;
disp(y,'Convolution Sum using Direct Formula Method = ')
subplot(3,1,3);
plot2d3(y)
title('Graphical Representation of output Signal y');
```



### CALCULATIONS:
<img width="974" height="1600" alt="WhatsApp Image 2026-08-25 at 11 24 02" src="https://github.com/user-attachments/assets/5075d014-d7b7-4cc7-8c69-456686fac5bc" />


<img width="1600" height="759" alt="WhatsApp Image 2026-08-25 at 11 24 19" src="https://github.com/user-attachments/assets/bb30fb0f-e404-4ca0-94c0-172ebdbe8dc0" />


### SAMPLE OUTPUT:

<img width="1372" height="631" alt="WhatsApp Image 2026-08-07 at 22 38 03" src="https://github.com/user-attachments/assets/d1df7f47-f931-4720-b1a0-4b1655eff4f6" />




RESULT:
Thus, the linear convolution of the two given sequences were performed and its result was verified.
