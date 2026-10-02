# Gait Analysis: From Walking Barefoot to Football Shoes

## Introduction
This repository contains an analysis exploring the differences in gait dynamics between walking barefoot and walking with football (soccer) shoes. The goal of this notebook is to discover and analyze variations in movement dynamics.

Inertial data collected through an accelerometer and a gyroscope are used. Due to the presence of noise in the raw data, a filtering phase is implemented.

Data was collected from 10 subjects with highly heterogeneous physical characteristics (height and body weight). Measurements were divided into two different blocks. Both groups walked in a straight line on a flat, rigid surface.

The project involves extracting features from each signal for subsequent graphical visualization. This graphical analysis aims to verify whether subjects with similar physical characteristics tend to cluster in different areas of a Cartesian plane. Furthermore, it aims to highlight a division between the measurements taken barefoot and those taken with shoes.

### Author
*   **Name:** Marco Mammoliti
*   **Email:** S5564736@studenti.unige.it, mammolo103@gmail.com

*(Axis reference: Please refer to the image `../dati/im.png` in the repository for the direction of the axes).*

## Methods
During the filtering and analysis phase, the signal is processed using several functions:

*   **`pd.read_csv`**: A method used to read data from CSV files. It returns a data structure with labels for each column present in the file.
*   **`gaussian_filter()`**: Applies a Gaussian filter via convolution. It returns an array exactly like the input one but with filtered values.
*   **`np.fft.fft()`**: A function that calculates the discrete Fourier Transform of the input signal. It returns the frequency spectrum of the signal.
*   **`np.fft.fftfreq()`**: This function calculates the frequencies associated with the discrete Fourier Transform. It returns an array containing all the frequencies that can appear in the signal.

## Experiment
As mentioned at the beginning, measurements were taken on 10 different subjects for a total of 20 measurements. 
The experiments were conducted on two different days. All participants examined walked in a straight line on a tiled floor.

### Hypothesis:
Given that football shoes feature studs—which are rigid and distributed non-uniformly on the outer part of the sole—significant differences in the data are expected. 
Variations are primarily expected:
*   **Accelerometer:** along the vertical (y) and horizontal (x) axes.
*   **Gyroscope:** along the horizontal (z) axis, which measures external/internal rotations.

In fact, walking with football shoes results in a sharp, robotic, and unnatural movement, which is why obvious differences are expected.

## Data Structure and Uploading
Below, the data collected during the experiments is imported. 
It is organized into **two 2 x 10 matrices**:
*   One matrix for the **accelerometer**.
*   One matrix for the **gyroscope**.

Within each matrix, there are two rows:
*   **Index 0:** data collected **barefoot**.
*   **Index 1:** data collected **with football shoes**.

The raw data then undergoes a "cutting" process to retain only the significant portions of the recordings.

## Preliminary Analysis
In this initial data exploration, the "z" axis of the accelerometer was examined. Depending on the positioning of the instrument, during the measurement, a positive value indicates forward acceleration, while a negative value represents backward acceleration.

#### What can we notice?
1.  It is immediately noticeable that the walk appears stiffer with shoes. Furthermore, it is evident that the negative acceleration has much stronger peaks.
2.  Additionally, a repeating pattern emerges much more clearly when football shoes are used.
