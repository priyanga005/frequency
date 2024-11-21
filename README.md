import numpy as np
import matplotlib.pyplot as plt

def frequency_analysis(signal, fs):
    """
    Perform frequency analysis using FFT.
    
    Parameters:
    signal : array
        Input signal.
    fs : float
        Sampling frequency of the signal.
    
    Returns:
    f : array
        Frequency bins.
    magnitude : array
        Magnitude spectrum of the signal.
    """
    N = len(signal)  # Number of samples
    fft_result = np.fft.fft(signal)  # Perform FFT
    fft_result = fft_result[:N//2]  # Take only the positive half of the spectrum
    magnitude = np.abs(fft_result) * (2 / N)  # Normalize and compute magnitude
    f = np.fft.fftfreq(N, 1/fs)[:N//2]  # Generate
