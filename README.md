# Clueless — AI-Powered Interactive Workflow Assistant

**Intelligent, real-time desktop guidance for smarter software onboarding, automation, and contextual user assistance.**

Clueless is an AI-powered desktop assistant designed to simplify complex software workflows through interactive visual guidance, conversational AI, and voice-assisted instructions.

Instead of relying on traditional documentation, video tutorials, or manual support, Clueless helps users complete tasks directly within their applications through contextual, step-by-step walkthroughs.

The platform combines multimodal large language models, UI interaction guidance, workflow orchestration, and text-to-speech technologies to create a more intuitive software experience.

---

## Overview

Learning unfamiliar software can be time-consuming, especially when users must navigate complicated interfaces or perform multi-step tasks.

Clueless addresses this challenge by providing a conversational desktop assistant that understands user requests and translates them into actionable instructions.

For example, a user can ask:

> How do I send an email using Gmail?

Clueless guides the user through the required actions, highlights relevant interface elements, and provides optional voice instructions.

The goal is to make software interactions more accessible, reduce repetitive support requests, and improve productivity.

## Key Features

### Interactive Workflow Guidance

Transform natural-language requests into structured, step-by-step instructions.

- Contextual task guidance.
- Sequential workflow navigation.
- Visual instructions for interface interactions.
- Interactive walkthrough progression.
- Support for multi-step software tasks.

### AI-Powered Conversational Assistance

Use natural language to communicate with the assistant.

- Interpret user requests.
- Generate contextual guidance.
- Support conversational task assistance.
- Integrate LLM reasoning into workflow orchestration.

### Visual UI Guidance

Provide assistance directly on the user's screen through an overlay interface.

- Highlight relevant interface elements.
- Indicate the next action.
- Display interactive hotspots.
- Reduce dependence on external tutorials.
- Guide users without requiring changes to the target application's interface.

### Voice-Guided Instructions

ElevenLabs text-to-speech integration enables spoken guidance.

- Natural-sounding speech synthesis.
- Audio instructions for workflow steps.
- Configurable voice selection.
- Adjustable playback volume.
- Optional audio testing during setup.

### Desktop Application Experience

Built with Electron.js to deliver a desktop-based interface.

- Floating assistant interface.
- Conversational interaction panel.
- Workflow status feedback.
- Integrated audio controls.
- Overlay-based assistance.

---

## Technology Stack

| Category | Technologies | Purpose |
|---|---|---|
| Backend | Python | Application logic and services |
| AI Orchestration | LangChain, LangGraph | LLM workflows and state management |
| AI Model | Anthropic Claude | Contextual reasoning and multimodal assistance |
| Desktop Frontend | Electron.js, JavaScript | Cross-platform desktop interface |
| Voice Synthesis | ElevenLabs | Audio instructions |
| AI Infrastructure | ACI.dev | Tool and service integration |
| Interface | HTML, CSS, JavaScript | UI components and interactive overlays |

## System Architecture

```text
                  +-----------------------+
                  |         USER          |
                  |   Natural Language    |
                  |        Request        |
                  +-----------+-----------+
                              |
                              v
                  +-----------------------+
                  |    ELECTRON DESKTOP   |
                  |       ASSISTANT       |
                  |  Chat / Overlay / UI  |
                  +-----------+-----------+
                              |
                              v
                  +-----------------------+
                  |     PYTHON BACKEND    |
                  |    Workflow Engine    |
                  +-----------+-----------+
                              |
                  +-----------+-----------+
                  |                       |
                  v                       v
       +---------------------+  +-------------------+
       |   AI ORCHESTRATION  |  |   TOOL SERVICES   |
       | LangChain/LangGraph |  |      ACI.dev      |
       |   Anthropic Claude  |  +-------------------+
       +----------+----------+
                  |
         +--------+--------+
         |                 |
         v                 v
 +---------------+ +----------------+
 |  VISUAL GUIDE | |   ELEVENLABS   |
 |  UI Hotspots  | |  Voice Output  |
 |  Step Actions | +----------------+
 +---------------+
```

### Workflow Execution

1. The user enters a task using natural language.
2. The Electron interface forwards the request to the backend.
3. The backend uses AI orchestration to interpret the task.
4. The workflow engine generates sequential instructions.
5. The desktop overlay highlights the relevant UI elements.
6. ElevenLabs provides spoken instructions when enabled.
7. The user completes each step and proceeds through the workflow.

---

## Project Structure

```text
clueless/
|
+-- backend/
|   +-- main.py
|   +-- requirements.txt
|   +-- setup_elevenlabs.py
|   +-- test_tts.py
|   +-- tts_service.py
|   +-- .env.example
|   +-- README.md
|   +-- ELEVENLABS_SETUP.md
|
+-- frontend/
|   +-- components/
|   |   +-- floatingBox.js
|   |
|   +-- styles.css
|   +-- consolidated.css
|   +-- package.json
|
+-- README_TTS.md
+-- README.md
```

*This represents the key files referenced in the project's documentation, not necessarily its complete directory tree.*

---

## Installation and Setup

### Prerequisites

Ensure the following are available:

- Python and pip.
- Node.js and npm.
- Git.
- Anthropic API credentials.
- ElevenLabs API key for voice functionality.
- Any required ACI.dev configuration.

### Step 1 — Clone the Repository

```bash
git clone <YOUR-REPOSITORY-URL>
cd clueless
```

Replace the placeholder with the actual repository URL.

### Step 2 — Configure the Backend

Navigate to the backend directory:

```bash
cd backend
```

Create the environment configuration file.

**Windows PowerShell:**

```powershell
Copy-Item .env.example .env
```

**Linux / macOS:**

```bash
cp .env.example .env
```

Configure the required API credentials using the variable names defined in `.env.example`.

Install Python dependencies:

```bash
pip install -r requirements.txt
```

For ElevenLabs configuration, run:

```bash
python setup_elevenlabs.py
```

Alternatively, configure the supported voice API variables manually.

Test text-to-speech functionality:

```bash
python test_tts.py
```

Start the backend:

```bash
python main.py
```

The documented development backend runs at:

http://localhost:8000

### Step 3 — Start the Electron Frontend

Open a separate terminal and navigate to the frontend directory:

```bash
cd frontend
```

Install the required dependencies:

```bash
npm install
```

Launch the desktop application:

```bash
npm start
```

Make sure the backend service is running before initiating AI workflows.

---

## How to Use Clueless

### 1. Launch the Application

Start the Python backend and Electron desktop client.

### 2. Enter Your Request

Type a natural-language instruction such as:

> Help me send an email to a contact using Gmail.

Other examples include:

- Guide me through adding a new user.
- Show me how to update my profile settings.
- Help me find a specific feature.
- Walk me through a software configuration process.

### 3. Follow the Interactive Guidance

The assistant processes the task and presents step-by-step instructions.

Depending on the workflow, users can:

- Read the instruction displayed in the assistant.
- Listen to synthesized voice guidance.
- Identify highlighted screen elements.
- Click the relevant interface hotspots.
- Progress through the workflow.

### 4. Manage the Assistant

Use the conversation interface to monitor workflow progress and control audio playback.

---

## Business Applications

### Customer Onboarding

Help new customers learn software features through interactive walkthroughs rather than lengthy documentation.

### Employee Training

Provide guided experiences for employees learning internal applications and operational workflows.

### Technical Support

Assist users with common software questions through contextual, sequential instructions.

### Software Feature Adoption

Guide users toward underutilized features and explain how to use them effectively.

### Operational Productivity

Reduce the effort required to learn and repeat complex software processes.

---

## Configuration and Customization

### Change the Default Voice

Modify the `voice_id` configuration in:

`backend/tts_service.py`

### Adjust Audio Volume

Modify the `audio.volume` configuration in:

`frontend/components/floatingBox.js`

### Customize the Interface

The frontend styling can be modified through:

- `frontend/styles.css`
- `frontend/consolidated.css`

Changes to overlays, hotspots, and floating assistant components should be tested against the supported target applications.

---

## Engineering Considerations

### AI-Based Workflow Orchestration

LangChain and LangGraph provide an architectural foundation for organizing multi-step AI interactions and maintaining workflow state.

### Desktop UI Assistance

Electron provides a desktop application layer that can display guidance independently of the target software.

Visual targeting accuracy depends on application layout, screen configuration, permissions, and the underlying UI interaction implementation.

### External AI Services

Anthropic Claude, ACI.dev, and ElevenLabs introduce external API dependencies.

API credentials should be stored securely, usage costs should be monitored, and sensitive information should not be exposed unnecessarily.

### Workflow Reliability

UI-based workflows can become unreliable when target applications change their layouts or interaction behavior.

A production implementation would benefit from robust element detection, error recovery, workflow validation, and user confirmation before sensitive actions.

---

## Future Roadmap

Potential enhancements include:

- Dynamic workflow generation using deeper API integrations.
- Workflow completion analytics and reporting.
- Browser extension support.
- Mobile-compatible assistance.
- Multilingual voice and text interactions.
- Improved accessibility.
- More robust application-state recognition.
- Automated recovery from failed workflow steps.
- Enterprise authentication and organization-level configuration.
- Support for reusable workflow templates.

---

## Documentation

Additional technical documentation is available in the repository:

- [Backend Documentation](backend/README.md)
- [Text-to-Speech Documentation](README_TTS.md)
- [ElevenLabs Setup Guide](backend/ELEVENLABS_SETUP.md)

---

## Development and Attribution

The source README credits the following developers:

- Adam O'Neill
- Jeremy Shorter
- Pratyaksh Mishra

**Portfolio maintainer:** Mashiel Khan  
GitHub: [github.com/Mashielkhan](https://github.com/Mashielkhan)

Specific contributions, modifications, and development ownership should be documented according to the repository's actual history.

---

## Project Vision

Clueless explores how conversational AI can bridge the gap between software functionality and user understanding.

By combining interactive visual assistance, natural-language processing, and accessible voice guidance, the project demonstrates an approach to making software easier to learn, navigate, and use.

**Clueless — Ask naturally. Learn visually. Work confidently.**
