# Transform-and-Filtering
Apply Fourier Transform and filtering to an image in the frequency domain using OpenCV.
import cv2
import numpy as np
from matplotlib import pyplot as plt

image = cv2.imread('input.jpg', 0)
f = np.fft.fft2(image)
fshift = np.fft.fftshift(f)

# Implement filtering in the frequency domain (e.g., high-pass, low-pass)

magnitude_spectrum = 20 * np.log(np.abs(fshift))

plt.subplot(121), plt.imshow(image, cmap='gray')
plt.title('Input Image'), plt.xticks([]), plt.yticks([])
plt.subplot(122), plt.imshow(magnitude_spectrum, cmap='gray')
plt.title('Magnitude Spectrum'), plt.xticks([]), plt.yticks([])
plt.show()
