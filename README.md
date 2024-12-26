# Image_sonification
## Abstract
This project involves working with a galaxy image dataset stored in a .npy file. The goal is to read the dataset, process the images using Python libraries like OpenCV and NumPy, extract pixel information (RGB/BGR), and visualize the images.
## Project Description
This repository contains scripts to:
- Load a dataset of galaxy images stored in an .npy file.
- Process the images to extract pixel data such as RGB or BGR values.
- Display the images using OpenCV and matplotlib.
- Store the pixel data in a CSV file for further analysis.
- Visualize the pixel data via heatmaps and other visualization techniques.
- Explores the creative process of mapping pixel data to audio parameters, resulting in the sonification of visual data.
## Maping Function Description
### 1. RGB to Frequency Ranges 
- **RGB to Frequency**: Each color channel (R, G, B) is mapped to a specific frequency range. 
- **Red**: 30-500 Hz with an offset of 60 Hz. 
- **Green**: 500-2000 Hz with an offset of 250 Hz. 
- **Blue**: 2000-10000 Hz with an offset of 1000 Hz. 
- **Amplitude**: Volume is proportional to the RGB value (0-255). 
- **Combined Sine Waves**: Sine waves for R, G, and B channels are combined for each pixel.
### 2. HSV to Sound Mapping 
- **Hue to Frequency**: Maps the hue component of the pixel's HSV value to a frequency (220-880 Hz). 
- **Saturation to Amplitude**: Maps the saturation component to amplitude (0-1). 
- **Value to Panning**: Maps the brightness component to stereo panning (-1.0 to 1.0).
### 3. Brightness and Dominant Color to Sound 
- **Brightness to Frequency**: The pixel's brightness (0-255) is mapped to a frequency (220-880 Hz). 
- **Dominant Color to Waveform**: The dominant color determines the waveform: sine for red, square for green, and sawtooth for blue.
### Color-Based Sound Effects Sonification
- Average color values (Red, Green, Blue) are calculated for each row of pixels.
- Sine waves are generated for each color channel: - **Red**: 440 Hz - **Green**: 660 Hz - **Blue**: 880 Hz
- The sine waves are combined to create a single wave for each row of pixels.
## Implementation 
- **Libraries Used**: pandas, numpy, pydub, colorsys, and torch.
- **Audio Generation**: Uses sine, square, and sawtooth waves to generate tones with the mapped parameters. 
- **Batch Processing**: Processes the **first 1000 rows** of pixel data to generate a short audio file.
## Image Sonification Tool
### Overview
- This tool allows users to upload an image and select a sonification mode.
- It converts image data into sound using different mappings, enhancing accessibility and providing a unique way to interpret visual data.
### Features
- Pixel extraction from images
- Multiple sonification modes:
  - Color-Based Sound Effects
  - Pitch Mapping Based on Brightness
  - Frequency Mapping
  - HSV Mapping
### Setup Instructions
1. **Clone the repository:**
   ```sh
   git clone <[repository-link](https://github.com/Sambit0110/Astrosonification.git)>
   cd <Image_Sonification_tool>
## Project Structure
- data/: Contains the .npy file of the galaxy images.
- .ipynb: Jupyter notebook for analysis and visualization.
- output/: Stores the extracted pixel data (CSV) and visual outputs.
- Image_Sonification/: Jupyter notebooks for differenet sound mapping function and sound generation.
- Generated_Sound_files/: Sample sound files demonstrating the corressponding mapping.
- Image Sonification Tool/: tool allows users to upload an image and select a sonification mode.
## Instructions 
### Prerequisites 
- Python 3.x
- Install required libraries: ```sh
                              pip install -r requirements.txt
                              ```
