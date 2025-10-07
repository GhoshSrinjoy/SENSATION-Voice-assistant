*“I asked my assistant to relax. It replied, ‘System optimization complete.’”*  

# 🗣️ SENSATION – Voice Assistant  

A fully offline, Python-based **voice-controlled assistant** that listens, speaks, and acts.  
It tells you the time, your location, takes photos, shuts down your system, and more , all without an internet connection.  

Powered by **Vosk** for speech recognition and **pyttsx3** for text-to-speech, Sensation turns your Python environment into a smart, privacy-first voice companion.  

🔗 **Repo:** https://github.com/GhoshSrinjoy/SENSATION-Voice-assistant  

---

## Executive Summary  

Sensation listens for a simple wake word , “**Sensation**” , followed by your command.  
It recognizes intent, executes the task, and speaks back naturally.  

All of this happens **locally**, without sending audio to external servers.  
That means it’s fast, private, and completely under your control.  

**Example interactions:**  
> 🗣️ *“Sensation, what’s the time?”*  
> 🗣️ *“Sensation, take a picture.”*  
> 🗣️ *“Sensation, shut down the system.”*  

Whether you’re automating your desktop or experimenting with voice AI, this project gives you a working foundation for intelligent offline assistants.  

---

## Business Problem  

Most voice assistants (Alexa, Siri, Google Assistant) rely on cloud APIs , which are:  
- ❌ Slow when network conditions are poor  
- ❌ Privacy-invasive by design  
- ❌ Hard to customize or extend  

**Sensation** solves this by using **Vosk**, an open-source offline speech model.  
Everything runs locally , from recognition to response.  

Ideal for developers, researchers, and anyone curious about building **edge AI** assistants that don’t depend on the cloud.  

---

## Methodology  

### 🧠 Core Components  
- **Vosk** – Speech-to-text (offline ASR)  
- **pyttsx3** – Text-to-speech (TTS)  
- **OpenCV (cv2)** – Camera access for taking photos  
- **Geocoder + Requests** – Location fetching  
- **psutil + OS** – System control (shutdown, process handling)  
- **NLTK** – Natural language tokenization and parsing  

### ⚙️ How it Works  
1. Listens for the trigger word **“Sensation”**  
2. Converts voice to text via **Vosk**  
3. Matches the intent (time, date, photo, etc.)  
4. Executes the corresponding function  
5. Uses **pyttsx3** to respond audibly  

All of this happens inside a continuous loop with real-time threading for smooth performance.  

---

## Dependencies

The following python libraries are required for the implementation:

- os
- cv2 (OpenCV)
- datetime
- requests
- psutil
- re
- json
- time
- threading
- nltk
- sounddevice
- pyttsx3
- geocoder
- vosk
- queue

I have provided a build file that installs all the above-required dependencies and starts the Sensation application automatically:
```
python build.py
```

Alternatively, You can install the required dependencies using pip:

```
pip install opencv-python datetime requests psutil nltk sounddevice pyttsx3 geocoder vosk
```

Also, make sure to download the NLTK tokenizer data by running the following in your Python environment:

```python
import nltk
nltk.download('punkt')
```

## Setup

1. **Vosk Language Model**: To use the Vosk speech recognition model, you need to download the appropriate model for your language. Replace `"path/vosk-model-small-en-in-0.4"` in the code with the actual path to your Vosk language model. You can download the model for your language from the Vosk GitHub repository: https://github.com/alphacep/vosk-api/tree/master/model

- Make sure you have up-to-date pip and python3 versions:
  **Python version**: 3.5-3.9
  **pip version**: 20.3 and newer.

2. **Camera Access**: For taking pictures, the code uses OpenCV (`cv2`) to access the camera. Make sure you have a camera connected to your computer, and the OpenCV library is properly installed.

3. **User Picture Folder**: In the `take_picture()` function, replace `"C:/Users/Pictures/Clicked pictures"` with the path where you want to save the captured pictures.

## How to Use

1. Run the script in your Python environment, and the Sensation assistant will welcome you.

2. The assistant listens to your voice input. Just say the trigger word "Sensation" followed by a specific command (e.g., "Sensation, what's the time?").

3. The assistant will recognize your command and perform the corresponding task.

4. For the "shutdown_system" command, the assistant will ask for your confirmation before shutting down the system.

5. To exit the assistant, simply say "Stop Sensation," and it will bid you goodbye.

## Supported Commands

- `time`: Get the current time.
- `date`: Get today's date.
- `day`: Get the current day.
- `position`, `address`, `location`, `where am i now`: Get your current location.
- `picture`, `photo`, `selfie`, `shot`: Take a picture using the connected camera and save it.
- `shut`, `down`, `turn`, `off`: Shut down the system. The assistant will ask for confirmation before proceeding.
- `stop`: Stop the voice assistant and exit.

**Note**: The assistant is designed to recognize the specific trigger word "Sensation" followed by a valid command from the list above. If you encounter issues with command recognition, try speaking clearly and ensure that the command you want to execute is included in the list of supported commands.

## Important Considerations

- The Vosk language model is responsible for recognizing your voice commands. Please ensure you have the correct model loaded and it supports your language.
- The camera access is necessary for the `take_picture()` function to work correctly.
- Be cautious when using the "shut down" command, as it will immediately shut down your system without further confirmation.
- This code is designed for educational purposes and may require additional error handling and improvements for production use.
