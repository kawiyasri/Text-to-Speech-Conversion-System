# 🔊 Text-to-Speech Conversion System Using Python

A simple desktop application that converts written text into spoken audio using Python. The application provides a graphical user interface (GUI) where users can enter text, generate speech, and listen to the generated audio.

Built using **Python, Tkinter, Google Text-to-Speech (gTTS), and pygame**, this project demonstrates GUI development, speech generation, and audio playback.

## 📌 Table of Contents

* [About the Project](#-about-the-project)
* [Features](#-features)
* [Technologies Used](#-technologies-used)
* [How It Works](#-how-it-works)
* [Project Structure](#-project-structure)
* [Prerequisites](#-prerequisites)
* [Installation](#-installation)
* [Usage](#-usage)
* [Code Overview](#-code-overview)
* [Screenshots](#-screenshots)
* [Limitations](#-limitations)
* [Future Enhancements](#-future-enhancements)
* [Contributing](#-contributing)
* [License](#-license)
* [Author](#-author)

## 📖 About the Project

Text-to-Speech (TTS) is a technology that converts written text into spoken language.

This project implements a Python-based TTS application with a graphical interface. Users can type text into the application and click the **PLAY** button to convert it into speech. The generated audio is saved as an MP3 file and played through the computer's speakers or headphones.

The application also includes RESET and EXIT buttons for convenient interaction.

This project is suitable for beginners who want to learn Python GUI programming, work with external libraries, and build a practical desktop application.

## ✨ Features

* **Text Input:** Enter text through a graphical text box.
* **Speech Generation:** Convert written text into speech using gTTS.
* **Audio Playback:** Listen to generated speech using pygame.
* **PLAY Button:** Generate and play the speech audio.
* **RESET Button:** Clear the text box and stop current playback.
* **EXIT Button:** Stop audio playback and close the application.
* **Input Validation:** Display a warning when the user attempts to generate speech without entering text.
* **Error Handling:** Display errors when speech generation or playback fails.

## 🛠️ Technologies Used

| Technology | Purpose                                  |
| ---------- | ---------------------------------------- |
| Python     | Main programming language                |
| Tkinter    | Creates the graphical user interface     |
| gTTS       | Converts text into speech audio          |
| pygame     | Plays the generated MP3 file             |
| threading  | Runs speech generation in the background |
| MP3        | Audio output format                      |

**Note:** Tkinter is included with most standard Windows Python installations. It generally does not need to be installed separately using pip.

## 🔄 How It Works

The application follows this workflow:

```text
          ┌─────────────────────┐
          │   Launch the App    │
          └──────────┬──────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │   Enter Text        │
          └──────────┬──────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │ Validate User Input │
          └──────────┬──────────┘
                     │
              ┌──────┴──────┐
              │             │
          Empty Text     Valid Text
              │             │
              ▼             ▼
       ┌────────────┐ ┌──────────────┐
       │ Show       │ │ Generate     │
       │ Warning    │ │ Speech gTTS  │
       └────────────┘ └──────┬───────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ Save speech.mp3 │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ Play Audio      │
                    │ Using pygame    │
                    └─────────────────┘
```

Speech generation through gTTS normally requires an active internet connection.

## 📂 Project Structure

```text
Text-to-Speech-Conversion/
│
├── text_to_speech.py       # Main Python application
├── speech.mp3              # Generated audio file (created at runtime)
├── README.md               # Project documentation
└── requirements.txt        # Python dependencies
```

The `speech.mp3` file is generated when the application converts text into speech. It does not need to be included in the repository.

## 💻 Prerequisites

Before running the project, ensure you have:

* Python 3 installed.
* An internet connection for gTTS speech generation.
* Speakers or headphones.
* A terminal or Python editor, such as VS Code.
* Tkinter support in your Python installation.

**Recommended:** Python 3.12 or 3.13 can be useful if you encounter compatibility problems with older audio libraries. Other versions may work depending on package support.

## ⚙️ Installation

### Step 1: Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/Text-to-Speech-Conversion.git
```

Replace `YOUR-USERNAME` with your GitHub username and adjust the repository name if necessary.

### Step 2: Navigate to the project directory

```bash
cd Text-to-Speech-Conversion
```

### Step 3: Create a virtual environment (recommended)

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

### Step 4: Install dependencies

```bash
python -m pip install --upgrade pip
python -m pip install gTTS pygame
```

Check that Tkinter is available:

```bash
python -c "import tkinter; print('Tkinter is available')"
```

If this command fails, check your Python installation for Tcl/Tk support.

### Step 5: Run the application

```bash
python text_to_speech.py
```

The application window should open, allowing you to enter text and generate speech.

## 🚀 Usage

1. Launch the application.
2. Enter the text you want to convert into speech.
3. Click **PLAY** to generate and listen to the speech.
4. Click **RESET** to clear the text and stop playback.
5. Click **EXIT** to close the application.

### Example

**Input text:**

```text
Hello! Welcome to my Text-to-Speech application.
```

**Expected output:**

The application generates an MP3 file named `speech.mp3` and plays the spoken sentence.

Actual output depends on internet availability and successful audio playback.

## 🧩 Code Overview

The application is divided into a few main components.

### 1. GUI Creation

Tkinter creates the main window, text box, labels, and buttons.

```python
import tkinter as tk

root = tk.Tk()
root.title("Text to Speech")
root.geometry("450x300")
```

### 2. Speech Generation

gTTS converts the input text into an MP3 file.

```python
from gtts import gTTS

speech = gTTS(text="Hello World", lang="en")
speech.save("speech.mp3")
```

### 3. Audio Playback

pygame loads and plays the generated audio.

```python
import pygame

pygame.mixer.init()
pygame.mixer.music.load("speech.mp3")
pygame.mixer.music.play()
```

### 4. User Controls

* `Text_to_speech()` generates and plays speech.
* `Reset()` stops playback and clears the text box.
* `Exit()` releases audio resources and closes the application.

## 📸 Screenshots

Add screenshots of your actual running application to a folder named `screenshots`.

Example structure:

```text
Text-to-Speech-Conversion/
├── screenshots/
│   ├── application.png
│   └── speech-output.png
├── text_to_speech.py
└── README.md
```

Once you upload the screenshots to GitHub, display them in this section:

```markdown
### Application Interface

![Text-to-Speech Application](screenshots/application.png)

### Speech Output

![Speech Output](screenshots/speech-output.png)
```

These are example paths. Replace them with the actual filenames of your screenshots.

## ⚠️ Limitations

* An internet connection is normally required to generate speech using gTTS.
* Speech generation depends on the availability of the external service.
* The current implementation uses English as the default language.
* Long text may take additional time to process.
* Audio playback depends on the computer's audio configuration.

## 🔮 Future Enhancements

Potential improvements include:

* Add support for multiple languages.
* Add pause and resume controls.
* Allow users to upload text files.
* Add audio speed controls where supported.
* Let users choose output filenames and save locations.
* Add a progress indicator during speech generation.
* Improve the interface with a modern layout and theme options.
* Explore offline text-to-speech engines.

## 🤝 Contributing

Contributions are welcome!

If you would like to improve the project:

1. Fork the repository.

2. Create a new branch.

   ```bash
   git checkout -b feature/your-feature
   ```

3. Make your changes and test them.

4. Commit your changes.

   ```bash
   git commit -m "Add your feature"
   ```

5. Push your branch to GitHub.

   ```bash
   git push origin feature/your-feature
   ```

