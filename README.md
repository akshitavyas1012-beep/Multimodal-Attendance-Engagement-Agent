# Multimodal Attendance & Engagement Agent

An offline, AI-assisted classroom intelligence prototype that combines computer vision and session activity indicators to support attendance tracking and teaching decisions.

> **Privacy and responsible use:** Use only with informed consent. The current prototype detects anonymous faces; it does not identify students. Activity indicators are not validated measurements of attention or learning and must not be used for grading or disciplinary decisions.

## Project Overview

Traditional attendance systems often record only presence and provide little information about classroom dynamics. This project demonstrates a local application that can:

- Process a webcam feed or uploaded classroom video.
- Detect faces anonymously using OpenCV.
- Confirm sustained presence after a configurable time threshold.
- Save timestamped attendance records in a local CSV file.
- Estimate a rough motion/activity proxy from video frames.
- Display session-level activity indicators.
- Generate transparent, offline teaching suggestions.
- Export attendance records for review.

## Technology Stack

- **Python** — application logic
- **Streamlit** — interactive dashboard
- **OpenCV** — video input and face detection
- **NumPy** — frame calculations
- **Pandas** — data display and CSV handling

## Project Structure

```text
Multimodal_Attendance_Engagement_Agent/
├── app.py
├── requirements.txt
├── README.md
└── data/
    └── attendance.csv   # created when attendance is logged
```

## Requirements

- Windows, macOS, or Linux
- Python 3.10–3.12 recommended
- Webcam for live analysis, or a supported video file
- Internet is not required to run the application after dependencies are installed

## Installation and Setup

### 1. Extract the project

Extract the ZIP file and open the project directory in VS Code or a terminal.

### 2. Create a virtual environment

```bash
python -m venv .venv
```

### 3. Activate the environment

**Windows (Command Prompt):**

```bat
.venv\Scripts\activate
```

**Windows (PowerShell):**

```powershell
.venv\Scripts\Activate.ps1
```

**macOS / Linux:**

```bash
source .venv/bin/activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the application

```bash
streamlit run app.py
```

Streamlit will display a local address, usually:

```text
http://localhost:8501
```

Open that address in your browser.

## How to Use

1. Start the application.
2. Enter a session name or subject in the sidebar.
3. Choose **Webcam** or **Upload video**.
4. For a video, select an MP4, AVI, or MOV file.
5. Click **Start analysis**.
6. Review detected anonymous faces and activity indicators.
7. Open **Session analytics** to review records and export a CSV.
8. Open **Teaching suggestions** to see offline suggestions based on the session activity inputs.

## Data and Privacy

- Video processing is performed locally by the application.
- The prototype does not upload video to a cloud service.
- It does not store face images or perform face identity recognition.
- Attendance records are stored in `data/attendance.csv`.
- Delete that CSV file to clear the locally stored attendance records.
- Obtain informed consent and provide an opt-out method before any real classroom use.

## Current Limitations

This is a demonstration prototype, not a production-ready attendance solution.

- Face labels are temporary and are not persistent person identities.
- Multiple people may be incorrectly counted or associated across frames.
- The current audio activity field is a manual input; the app does not record or analyze classroom audio.
- Motion is only a rough activity proxy and cannot establish attention, comprehension, or engagement.
- Teaching suggestions use transparent offline rules, not a trained AI model.
- Attendance output should be reviewed by an instructor before being treated as an official record.

## Possible Future Improvements

- Robust multi-person tracking with consent-based enrollment.
- Optional offline face matching with clear privacy controls.
- Audio energy and speech-activity analysis without storing audio.
- Session timeline charts and per-session report generation.
- Instructor review and correction workflow.
- Configurable retention periods and access controls.
- Evaluation on consented test data before classroom deployment.

## License

For academic demonstration and learning. Add a license and third-party notices before redistributing or deploying the project.
