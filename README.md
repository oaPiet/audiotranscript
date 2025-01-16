# Audio Transcription and Hesitation Detection Script

This script records audio, transcribes it using Whisper, and detects hesitation markers from the transcription. It saves the audio and transcription files in an organized output folder.

## Requirements

Before running the script, ensure you have Python 3.7 or later installed on your machine. Additionally, you need to have **ffmpeg** installed as a prerequisite for audio processing.

You will also need the following dependencies:

- **pyaudio** - for audio recording
- **whisper** - for audio transcription using Whisper model
- **re** - for regular expressions to detect hesitation markers
- **os, datetime, wave** - for file management and handling

You can install the necessary dependencies using the provided `requirements.txt` file.

### Prerequisites

1. Install **Python 3.7+** if you haven't already. You can download it from [here](https://www.python.org/downloads/).
2. Install **ffmpeg** on your system:
   - For **Windows**: Download and install ffmpeg from [FFmpeg Downloads](https://ffmpeg.org/download.html).
   - For **macOS**: Use Homebrew: `brew install ffmpeg`.
   - For **Linux**: Use your package manager, for example, `sudo apt install ffmpeg` on Ubuntu.

## Setup Instructions

### Step 1: Clone the Repository
Clone the repository or download the project files to your local machine.

### Step 2: Set Up a Virtual Environment

#### Windows
1. Open a terminal and navigate to the project directory.
2. Create a virtual environment:
   ```sh
   python -m venv venv
   ```
3. Activate the virtual environment:
   ```sh
   .\venv\Scripts\activate
   ```

#### macOS / Linux
1. Open a terminal and navigate to the project directory.
2. Create a virtual environment:
   ```sh
   python3 -m venv venv
   ```
3. Activate the virtual environment:
   ```sh
   source venv/bin/activate
   ```
### Step 3: Install Dependencies
With the virtual environment activated, install the required dependencies by running:
```sh
pip install -r requirements.txt
```
### Step 4: Running the Script
After the setup is complete, you can run the script as follows:
```sh
python main.py
```
The script will:
- Record audio until you press **Ctrl+C** to stop.
- Transcribe the audio using Whisper.
- Detect hesitation markers from the transcription.
- Save the transcription and detected markers to a `.txt` file.

You can also customize the recording behavior by providing additional arguments:

- `--prep-time <seconds>`: Specifies the preparation time before the recording starts.
- `--seconds <seconds>`: Defines the recording duration in seconds.

### Example Command:
To start recording with a 5-second preparation time and a 30-second recording duration, you would run:
```sh
python main.py --prep-time 5 --seconds 30
```

### Step 5: Output Files
The script generates two output files:

1. **Audio File**:  
   The recorded audio will be saved as a `.wav` file in the `output_transcription` folder with a timestamp in its filename. Example:
```sh
output_transcription/recorded_audio_20250116_103045.wav
```
2. **Transcription File**:  
The transcription and detected hesitation markers will be saved in a `.txt` file with the same base name as the audio file. Example:
```sh
output_transcription/recorded_audio_20250116_103045_transcript.txt
```

### Example Output:

**Transcription:**
```sh
You know what they call a Quarter Pounder with Cheese in Paris?
They don’t, um, call it a Quarter Pounder with Cheese, 
they got the, uh, metric system... they call it a Royale with Cheese!
```

**Detected Hesitations:**
`um, uh`

### Troubleshooting

- **PyAudio installation on Windows**: If you encounter issues installing PyAudio, try installing the precompiled binary using:
  ```sh
  pip install pipwin pipwin install pyaudio
  ```
  
- **Whisper installation**: Whisper should install automatically via the requirements.txt. Ensure you have the necessary hardware to run the models (for example, a GPU for larger models).

## Additional Information

### Whisper Model Variants

The Whisper model can be set to different variants for better performance:

- **"base"** (default)
- "small"
- "medium"
- "large"

You can change the model in the script by modifying the `MODEL` variable.

### Customizing Hesitation Markers

The script uses a predefined list of hesitation markers, but you can expand or modify this list by editing the `HESITATION_MARKERS` array in the script.

## requirements.txt

Here’s the `requirements.txt` file with necessary dependencies:
pyaudio==0.2.11 whisper==1.0.0

If you're having trouble installing pyaudio, especially on macOS or Linux, you might need to install additional dependencies, such as `portaudio` or `libportaudio-dev`.

## Troubleshooting

- **PyAudio installation on Windows**: If you encounter issues installing pyaudio, try installing the precompiled binary using:
    ```sh
    pip install pipwin
    pipwin install pyaudio
    ```

- **Whisper installation**: Whisper should install automatically via the requirements.txt. Ensure you have the necessary hardware to run the models (for example, a GPU for larger models).

## References

- [Whisper GitHub Repository](https://github.com/openai/whisper)
- [PyAudio Documentation](https://pypi.org/project/PyAudio/)

