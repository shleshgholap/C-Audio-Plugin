# SimpleEQ Audio Processor

## Overview

The **SimpleEQ Audio Processor** is a digital audio processing plugin created using the JUCE framework. This plugin is designed to implement a simple equalizer (EQ) with customizable filters to process audio signals. The project is built on a basic framework provided by JUCE, and it includes both low-pass and high-pass filters, as well as a peak filter for frequency adjustment.

## Features

- **Low-Cut Filter**: Removes low-frequency content from the audio signal.
- **High-Cut Filter**: Removes high-frequency content from the audio signal.
- **Peak Filter**: Allows boosting or attenuating a specific frequency band.
- **Customizable Slope**: The slopes of the filters can be set to different levels (12 dB/octave, 24 dB/octave, etc.).
- **Stereo Processing**: Processes left and right audio channels independently.
- **FIFO Buffers**: Utilizes FIFO buffers for efficient audio data handling.

## Project Structure

### 1. `PluginProcessor.h`

This header file defines the main processing structure for the audio plugin. It includes the following key components:

- **ChainSettings**: A struct that holds the parameters for the filters, including frequency, gain, quality, and bypass states.
- **Filter Types**: Definitions for low-cut, high-cut, and peak filters using JUCE's DSP module.
- **MonoChain**: A processor chain that applies filters to the audio signal.
- **SingleChannelSampleFifo**: A FIFO buffer implementation for handling audio data samples efficiently.

### 2. `PluginProcessor.cpp`

This file contains the implementation of the `SimpleEQAudioProcessor` class. Key functions include:

- **prepareToPlay**: Initializes the plugin, prepares the filters, and sets up the oscillator.
- **processBlock**: Main processing loop where audio data is passed through the filters.
- **updateFilters**: Updates the filter coefficients based on the current settings.
- **getStateInformation/setStateInformation**: Manages the plugin state, allowing for saving and loading of settings.

### 3. `PluginEditor.cpp`

The GUI for the plugin is handled in this file. It includes the creation of the user interface and the mapping of UI controls to the audio processor's parameters.

## Dependencies

- **JUCE Framework**: A C++ framework for developing cross-platform audio applications.

## Installation

1. Clone the repository.
2. Ensure JUCE is installed and configured on your system.
3. Open the project in your preferred IDE (e.g., Visual Studio, Xcode) via the Projucer.
4. Build the project to create the plugin.

## Usage

Once compiled, the plugin can be loaded into any DAW that supports VST3/AU plugins. The user can adjust the frequency bands, slopes, and bypass states directly from the plugin's interface.



