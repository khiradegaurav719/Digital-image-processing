% Digital Image Processing : Lab Task - 3
% Student: BT20ECE027(AMIT YADAV)
% Professor: Dr. Tapan Jain
% Date: 30 Jan 2023

% Task 1.0 - Read a Colour Image and Convert it to a GreyScale Image.
% Task 1.1 - Perform Bit Plane Slicing on the obtained GreyScale Image and Show all
%            the Bit Planes as Images.
% Task 1.2 - Make the Least Significant Bit(LSB) Plane as Zero and Then Combine all
%            the Bit Planes. Display the Reconstructed Image.

clc; 
clear; 
close all;

% Task - 1.0
I = imread('map.png');
Ig = rgb2gray(I);

% Task - 1.1
[row, col, layers] = size(Ig);
if (layers==3)
    error('Input Image should be a Greyscale Image in order to perform Bit Plane Slicing');
else
    [B1,B2,B3,B4,B5,B6,B7,B8] = BitPlaneSlicing(Ig);
end

%Bit Plane 1(LSB)
subplot(3,3,1);
imshow(B1);
title('I0(LSB)');

%Bit Plane 2
subplot(3,3,2);
imshow(B2);
title('I1');

%Bit Plane 3
subplot(3,3,3);
imshow(B3);
title('I2');

%Bit Plane 4
subplot(3,3,4);
imshow(B4);
title('I3');

%Bit Plane 5
subplot(3,3,5);
imshow(B5);
title('I4');

%Bit Plane 6
subplot(3,3,6);
imshow(B6);
title('I5');

%Bit Plane 7
subplot(3,3,7);
imshow(B7);
title('I6');

%Bit Plane 8(MSB)
subplot(3,3,8);
imshow(B8);
title('I7(MSB)');
 
% Task - 1.2
B1 = zeros(row,col);
Recombined_Planes = B1*(2^0) + B2*(2^1) + B3*(2^2) + B4*(2^3) + B5*(2^4) + B6*(2^5) + B7*(2^6) + B8*(2^7);
Ir = uint8(Recombined_Planes);
subplot(3,3,9);
imshow(Ir);
title('Reconstructed Image');
 
% Bit Plane Slicer (Function) using bitget command
function [B1, B2, B3, B4, B5, B6, B7, B8] = BitPlaneSlicing(Ig)
[row, col] = size(Ig);
B=zeros(row,col,8);
for k = 1:8
    for i = 1:row
        for j = 1:col
            B(i,j,k) = bitget(Ig(i,j),k); % Extracting Kth Bit of Each Pixel(i,j)of Ig
                                          % and storing Extracted Kth bit in I(k-1) Matrix 
        end
    end
end

B1 = B(:,:,1);
B2 = B(:,:,2);
B3 = B(:,:,3);
B4 = B(:,:,4);
B5 = B(:,:,5);
B6 = B(:,:,6);
B7 = B(:,:,7);
B8 = B(:,:,8);
end
