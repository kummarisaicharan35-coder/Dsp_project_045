# Dsp_project_045
🚨 Emergency Vehicle Siren Detection Using Digital Signal Processing in MATLAB

📌 Project Overview

Emergency vehicles such as ambulances, fire engines, and police vehicles use sirens to alert nearby traffic. Detecting these sirens in noisy environments can help develop intelligent traffic monitoring and emergency vehicle alert systems.

This project implements an Emergency Vehicle Siren Detection System using Digital Signal Processing (DSP) in MATLAB. It analyzes audio recordings, applies frequency-based filtering, examines spectral characteristics, and determines whether a siren is likely present.

The system uses Fast Fourier Transform (FFT), a Butterworth band-pass filter, a spectrogram, Welch Power Spectral Density (PSD), and siren-band power ratio analysis to make a detection decision.

🎯 Objectives

- Load and analyze audio recordings containing siren and traffic sounds.
- Visualize audio signals in the time domain.
- Extract frequency information using FFT.
- Isolate the expected siren frequency range using a Butterworth band-pass filter.
- Analyze audio characteristics using a spectrogram and Welch PSD.
- Calculate the proportion of signal power within the expected siren frequency band.
- Display the final result as SIREN DETECTED or NO SIREN DETECTED.
- Save detection measurements in a CSV file for further analysis.

🛠️ Technologies Used

- MATLAB – Signal processing and implementation
- Digital Signal Processing (DSP) – Audio analysis
- Signal Processing Toolbox – Filtering, spectral analysis, and signal visualization
- Audio files (.wav) – Input recordings
- CSV – Exporting detection results

⚙️ System Workflow

1. Audio Input: Load a WAV audio file.
2. Preprocessing: Convert stereo audio to mono and remove the DC component.
3. Waveform Analysis: Plot the complete waveform and the first two seconds.
4. Band-Pass Filtering: Apply a fourth-order Butterworth filter over 500–1300 Hz.
5. FFT Analysis: Identify the dominant frequency in the input signal and examine the filtered signal.
6. Spectrogram Analysis: Visualize how the signal's frequency content changes over time.
7. Welch PSD Analysis: Estimate the signal's power spectral density.
8. Band-Power Calculation: Calculate the proportion of signal power within the 500–1300 Hz band.
9. Detection Decision: Compare the dominant Welch PSD frequency and band-power ratio against predefined thresholds.
10. Result Export: Display the detection result and save measurements to "Siren_Detection_Result.csv".

📊 Detection Method

The detector uses two main conditions:

- The dominant frequency identified from Welch PSD must lie between 500 Hz and 1300 Hz.
- The siren-band power ratio must be at least 0.15.

The band-power ratio is calculated as:

[
R=\frac{P_{\text{siren band}}}{P_{\text{total}}}
]

where:

- (P_{\text{siren band}}) is the estimated power between 500 Hz and 1300 Hz.
- (P_{\text{total}}) is the estimated total signal power.

The decision rule is:

- If the dominant frequency lies in the selected band and (R \geq 0.15), the system reports SIREN DETECTED.
- Otherwise, it reports NO SIREN DETECTED.

Note: These are initial rule-based thresholds. They may need calibration using different siren recordings and traffic-noise samples. This method is not a trained machine-learning classifier, and other sounds within the same frequency band can cause false detections.

📁 Project Structure

Emergency-Siren-Detection/
│
├── githubcodematlab.m
├── Noisy_Siren.wav
├── Non_Siren_Test.wav
├── Siren_Detection_Result.csv
└── README.md

The WAV files and CSV file are generated or supplied separately. Add them to the repository only if you have the appropriate rights to share them.

💻 Requirements

- MATLAB
- Signal Processing Toolbox
- A WAV audio file for testing
- Sampling frequency greater than 2600 Hz

🚀 How to Run

1. Clone or download this repository.

2. Open MATLAB and navigate to the project folder.

3. Place your test WAV audio file in the Current Folder or in one of the folders searched by the script.

4. Open "githubcodematlab.m".

5. Set the input filename:
   
   INPUT_FILE = 'Noisy_Siren.wav';

6. Run the MATLAB script.

7. Examine the generated plots and the final detection window.

8. To test a recording without a siren, change the filename:
   
   INPUT_FILE = 'Non_Siren_Test.wav';

9. Run the script again and compare the results.

10. Open "Siren_Detection_Result.csv" to inspect the recorded measurements.

Important: Use the exact filenames of your audio files. The script searches the Current Folder and specific MATLAB Drive folders; if your file is elsewhere, update the folder search paths.

📈 Outputs

The script generates the following visualizations:

- Input audio waveform
- First two seconds of the input waveform
- Filtered audio waveform
- Butterworth filter frequency response
- FFT spectrum of the input audio
- FFT spectrum of the filtered audio
- Input audio spectrogram
- Welch Power Spectral Density plot
- Siren-band versus outside-band power comparison
- Final detection result window

It also saves a CSV containing the input filename, sampling rate, audio duration, FFT peak frequency, Welch peak frequency, band-power ratio, and final decision.

🔬 Applications

- Emergency vehicle alert systems
- Intelligent transportation systems
- Smart traffic management research
- Audio-based event detection
- Digital signal processing education and experimentation

⚠️ Limitations

- The detector relies on predefined frequency and power thresholds.
- Traffic noise, horns, alarms, and other sounds can overlap with the selected frequency band.
- Detection accuracy depends on the quality and duration of the audio recording.
- The current implementation does not use machine learning or deep learning.
- Real-world deployment would require extensive testing and calibration.

🔮 Future Improvements

- Use adaptive thresholds for different noise conditions.
- Add noise reduction and signal-to-noise ratio analysis.
- Analyze frequency variations over time to better identify siren patterns.
- Evaluate detection accuracy using precision, recall, F1-score, and a confusion matrix.
- Develop a real-time siren detection system using a microphone input.
- Explore machine-learning models for improved classification.

👨‍💻 Project Information

Project Title: Emergency Vehicle Siren Detection Using Digital Signal Processing in MATLAB

Domain: Digital Signal Processing, Audio Signal Processing, MATLAB

Project Type: Academic Mini Project

📜 License

Choose an appropriate open-source license before distributing this project publicly. If you do not want to grant reuse permissions yet, you can leave this section out until you decide.

---

⭐ If you find this project useful for learning MATLAB and digital signal processing, consider starring the repository!
