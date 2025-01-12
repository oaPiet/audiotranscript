# Audio Transcription and Hesitation Detection Script

This script records audio, transcribes it using Whisper, and detects hesitation markers from the transcription. It saves the audio and transcription files in an organized output folder.

## Requirements

Before running the script, ensure you have Python 3.7 or later installed on your machine. You will also need the following dependencies:

- **pyaudio** - for audio recording
- **whisper** - for audio transcription using Whisper model
- **re** - for regular expressions to detect hesitation markers
- **os, datetime, wave, sys** - for file management and handling

You can install the necessary dependencies using the provided `requirements.txt` file.

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

## Output Files
- The audio will be saved as a `.wav` file in the `output_transcription` folder with a timestamp.
- The transcription and detected hesitation markers will be saved in a `.txt` file with the same base name as the audio file.

### Example Output

**Transcription:**

You know what they call a Quarter Pounder with Cheese in Paris? They don’t, um, call it a Quarter Pounder with Cheese, they got the, uh, metric system... they call it a Royale with Cheese!

**Detected Hesitations:**

um, uh

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

