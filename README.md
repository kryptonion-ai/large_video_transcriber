# Whisper ASR Video Transcription

This Python script utilizes the Whisper ASR (Automatic Speech Recognition) model to transcribe audio from video files. It includes functionality to handle large video files by segmenting them into 20-minute audio clips, transcribing each segment individually, and combining the results.

## Dependencies

- **whisper:** Python library for interfacing with the Whisper ASR model.
- **os:** Python library for interacting with the operating system.
- **shutil:** Python library for file operations.
- **moviepy:** Python library for video editing operations.
- **AudioFileClip:** Class from the moviepy library for handling audio from video files.
- **VideoFileClip:** Class from the moviepy library for handling video files.

## Usage

1. **Installation of Dependencies:**

   ```bash
   pip install whisper moviepy
   ```

2. **Run the Script:**

   ```bash
   python script_name.py
   ```

3. **Script Parameters:**

   - `mp4_file_path`: Path to the input video file (e.g., "a1.mp4").
   - `language`: Language code for transcription (e.g., "en" for English).
   - `file_id`: Unique identifier for the video file.

4. **Output:**
   - The script will generate a transcribed text output for the provided video file.

## Script Overview

1. **Segmentation Function: `segments_twenty_minutes`**

   - Divides the input audio file into 20-minute segments to accommodate large video files.

2. **Transcription Function: `get_transcript`**

   - Checks the size of the input audio file.
   - If smaller than 25 MB, directly transcribes the file using the Whisper ASR model.
   - If larger, segments the file, transcribes each segment, and combines the results.

3. **Main Function: `convert_to_mp3_and_transcript`**
   - Converts the input video file to an MP3 audio file.
   - Calls the `get_transcript` function to transcribe the audio.
   - Returns the transcribed text.

## Example

```python
transcript = convert_to_mp3_and_transcript("a1.mp4", "en", "2222")
print(transcript)
```

## Notes

- Ensure that the Whisper ASR model is properly loaded and available in the specified path.
- Adjust the language code and file_id according to your requirements.
- This script is a basic example and may require additional error handling and customization for specific use cases.
