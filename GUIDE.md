# VoiceStudio: Complete Beginner's Guide

A practical, step-by-step guide to installing and using **VoiceStudio**, a free, open-source, local AI voice-production app. This guide is written for beginners and advanced users, including people using older PCs, laptops without a graphics card, NVIDIA systems, AMD systems, and Apple Silicon Macs.

> **Watch the quick introduction:** [See my Instagram Reel explaining what VoiceStudio does](https://www.instagram.com/reel/Df9U5YGhNdz/?lqvp=MWg3azgzOGR5Ynl1Zw==)

> **Important:** VoiceStudio is the application. It is not a single AI model. You install or download speech models (engines) inside it. Available features, languages, speed, quality, hardware acceleration and model licences depend on the engine you choose.

## Contents

- [1. What is VoiceStudio?](#1-what-is-voicestudio)
- [2. Features](#2-features)
- [3. PC requirements and compatibility](#3-pc-requirements-and-compatibility)
- [4. Download and install](#4-download-and-install)
- [5. First launch and model download](#5-first-launch-and-model-download)
- [6. Clone your own voice](#6-clone-your-own-voice)
- [7. Generate speech with a cloned voice](#7-generate-speech-with-a-cloned-voice)
- [8. Design a new AI voice](#8-design-a-new-ai-voice)
- [9. Dub a video into another language](#9-dub-a-video-into-another-language)
- [10. Transcription and dictation](#10-transcription-and-dictation)
- [11. Batch generation, narration and audiobooks](#11-batch-generation-narration-and-audiobooks)
- [12. Models and model packs](#12-models-and-model-packs)
- [13. Audio quality and export settings](#13-audio-quality-and-export-settings)
- [14. Advanced tools and automation](#14-advanced-tools-and-automation)
- [15. Tips for better results](#15-tips-for-better-results)
- [16. Troubleshooting](#16-troubleshooting)
- [17. Privacy, permissions and licences](#17-privacy-permissions-and-licences)
- [18. Official links](#18-official-links)

---

## 1. What is VoiceStudio?

VoiceStudio is an AI audio workstation that runs on your own computer. Depending on the installed engine, it can clone a voice from a recording, create a new voice from a description, turn text into speech, dub videos, transcribe audio, and help produce longer narration.

It is useful for:

- YouTube videos, Instagram Reels and other social content.
- Tutorials, explainers and voiceovers.
- Narration, stories and audiobook projects.
- Translating and dubbing videos.
- Transcribing meetings, interviews or recordings.
- Personal accessibility and dictation workflows.

**Does it need a paid subscription?** The desktop application is open source and can run locally without a paid cloud subscription or an account. You still need to download the models you want to use. Model downloads need an internet connection; generation can generally run offline after the required models are installed.

**Is it an ElevenLabs alternative?** It can provide similar kinds of local voice-generation workflows, but results are not identical. Voice quality, languages and speed vary by model and hardware.

## 2. Features

The exact options you see depend on your VoiceStudio version and installed models.

| Feature | What it does |
|---|---|
| Voice cloning | Uses a reference recording to generate speech in a similar voice. |
| Text to speech | Converts typed text into spoken audio. |
| Voice design | Creates a voice from written characteristics such as tone, pitch and accent. |
| Video dubbing | Transcribes, translates and generates speech timed to a video. |
| Transcription | Converts spoken audio into written text. |
| Dictation | Lets you speak and have your words transcribed using a dictation workflow/widget. |
| Speaker diarization | Helps identify and separate different speakers in supported workflows. |
| Vocal isolation | Separates vocals from background audio where supported. |
| Batch queue | Processes multiple narration or generation jobs in a queue. |
| Audiobook and long-form narration | Helps create longer spoken projects from text. |
| Model Manager | Installs and manages different speech and transcription engines. |
| Local API and MCP | Lets developers and compatible AI tools connect to local VoiceStudio features. |
| Recipes and watch folders | Supports repeatable and automated workflows in supported configurations. |

Not every model supports every language or feature. For example, a transcription model is not necessarily a text-to-speech model.

## 3. PC requirements and compatibility

VoiceStudio does not require an expensive gaming PC. A dedicated GPU is optional, but it can make supported models much faster.

### Operating system support

| Computer | Support and notes |
|---|---|
| Windows 10 / 11, Intel or AMD x64 | Supported. This is the easiest starting point for most PC users. |
| Windows laptop/desktop without NVIDIA GPU | Supported using CPU mode. Expect slower generation. |
| Windows with NVIDIA GPU | Supported. A compatible NVIDIA driver enables CUDA acceleration automatically for supported engines. |
| Windows with AMD GPU | CPU mode is the default for PyTorch engines. Some engines/builds can use other supported acceleration paths; check the current official hardware guide. |
| Windows on ARM / Snapdragon X | Experimental. The current backend runs under x64 emulation on CPU; expect limitations. |
| Linux x86_64 | Supported with a graphical desktop environment. NVIDIA CUDA and CPU options are available; AMD support depends on the documented ROCm setup and hardware. |
| macOS with Apple Silicon (M-series) | Supported on macOS 13.3 or newer. Uses Apple acceleration where supported. |
| Intel Mac | The desktop interface may open, but the current local Python backend is not supported. Connect to a backend on another computer instead. |

### Storage and internet

- Keep around **10 GB of free disk space** for the app, its managed environment and model files. Some model collections need much more.
- A stable internet connection is needed for the initial installation and model downloads.
- Keep additional free storage if you plan to install multiple engines or work with long videos.
- Use an SSD if possible. It helps with loading models and handling large media files.

### Which hardware should I use?

- **Basic office PC / no dedicated GPU:** Start with a small, CPU-friendly TTS engine and a small transcription model. Short scripts are a good first test.
- **8 GB RAM system:** Close unnecessary apps and use small models. Large models may fail or run very slowly.
- **16 GB RAM system:** A reasonable starting point for many normal workflows, depending on the model.
- **NVIDIA GPU:** Use a compatible driver and select a model that fits available VRAM. More VRAM gives you more model choices.
- **6 GB NVIDIA GPU (for example, an RTX 4050 laptop):** Start with a balanced or smaller model selection rather than assuming every large model will fit. Close games, browsers and other GPU-heavy apps while generating.
- **Apple Silicon:** Choose engines that explicitly support the Apple Silicon/MPS/MLX path.

These are practical starting points, not guaranteed minimums. Model requirements change and some engines use more memory than others.

## 4. Download and install

Always download the application from the official project. Do not download installers from random file-sharing websites.

### Windows 10 / 11

1. Open the [official VoiceStudio Releases page](https://github.com/debpalash/VoiceStudio/releases/latest).
2. Find the latest stable release and its download files.
3. For a normal Intel or AMD 64-bit PC, download the installer whose name ends in **win-x64.exe**.
4. If you have a Windows ARM PC, use the ARM64 installer only if it is provided for that release. ARM support is experimental.
5. Run the installer and follow the setup wizard. The normal installation is for your current Windows user; administrator access is generally not required.
6. Open VoiceStudio from the Start menu.
7. On the first launch, allow it to prepare its Python environment and download the required components.

Windows may show a security warning because an installer is not signed for that release. Check the release notes and verify the checksum when one is provided. Only proceed if you trust the source and have downloaded it from the official release page.

### Linux

1. Open the [official Releases page](https://github.com/debpalash/VoiceStudio/releases/latest).
2. Download the package provided for your Linux distribution, such as AppImage, Snap or .deb where available.
3. Follow the current [official Linux installation guide](https://github.com/debpalash/VoiceStudio/blob/main/docs/install/linux.md).
4. Install the package and launch VoiceStudio from your application menu.
5. Complete the first-run setup.

The packaged Linux desktop app does not require you to manually install Python or FFmpeg first; the app manages its required components.

### macOS

1. Open the [official Releases page](https://github.com/debpalash/VoiceStudio/releases/latest).
2. On an Apple Silicon Mac (M1, M2, M3, M4 and later), download the **mac-arm64.dmg** file.
3. Open the DMG and drag VoiceStudio into Applications.
4. Launch the app and complete the first-run setup.

The current local backend requires Apple Silicon and macOS 13.3 or newer. Intel Macs cannot run the local backend; use a backend hosted on another supported computer if needed. See the [official macOS guide](https://github.com/debpalash/VoiceStudio/blob/main/docs/install/macos.md).

### Docker / server users

Docker is intended for users who are comfortable with containers and server setup. It provides a browser-based interface and is useful for headless servers or dedicated GPU machines. Follow the [official Docker guide](https://github.com/debpalash/VoiceStudio/blob/main/docs/install/docker.md) rather than copying an old command from an unofficial tutorial.

## 5. First launch and model download

VoiceStudio separates the application from its AI models. The first launch may take time because it prepares the environment and downloads model files.

1. Open VoiceStudio.
2. Complete the setup screen and allow the required runtime components to install.
3. Open **Model Manager / Models** (the exact label can vary by version).
4. Browse the available engines and model packs.
5. Read the model description, hardware requirements and licence.
6. Select the model or pack you want and start the download.
7. Wait until the download and installation finish.
8. Select the installed engine in the relevant workspace.

**Do not download every model.** Start with one TTS engine and one transcription engine if you need transcription. Large models take more storage and memory.

A free Hugging Face account/token may help with downloads or access to certain gated models. Only enter a token through VoiceStudio's own credentials/settings screen. Never share your token publicly.

## 6. Clone your own voice

Voice cloning uses a reference recording to guide the generated voice. For best results, record your own voice in a quiet room.

### Prepare your recording

- Use a clean recording with one speaker only.
- Avoid music, TV, background conversations and echo.
- Speak naturally at a steady volume.
- Do not whisper or shout unless that is the style you want.
- Use a good microphone if available, but a phone recording can work if it is clear.
- A short, clean sample is better than a long recording full of noise.
- Use a language and speaking style that are suitable for your intended output.

### Steps

1. Open **Voice Cloning** (or the Clone workspace).
2. Select the TTS engine you installed.
3. Choose a built-in/demo voice to test the app, or add your own reference recording using the upload/add voice control.
4. If the workspace asks for a transcript, type the exact words spoken in your reference recording. Accurate text helps the model understand the sample.
5. Enter a short sentence in the text/script box.
6. Choose the language and any available voice or generation settings.
7. Click **Generate**.
8. Listen to the result. If it sounds wrong, check the recording quality, transcript, language and selected engine.
9. Adjust the settings and generate another take.
10. Save or export the audio when you are happy with it.

**First test:** Use one or two sentences rather than a full 10-minute script. This makes it easier to check whether your voice reference and model are working correctly.

## 7. Generate speech with a cloned voice

After adding or selecting a voice:

1. Open the Clone / Voice Cloning workspace.
2. Select your saved voice profile or upload the reference sample.
3. Type or paste the script.
4. Select the correct language if the engine offers a language selector.
5. Review the voice controls, such as speed or other supported settings.
6. Click **Generate** and wait for the audio.
7. Play the result inside the app.
8. If the result is good, use the available download/export control to save it.

For long scripts, generate in smaller paragraphs. This makes corrections easier and can reduce the chance of awkward pauses or pronunciation problems.

## 8. Design a new AI voice

Voice Design is for creating a voice from a description instead of cloning an existing recording.

1. Open **Voice Design** / **Design**.
2. Choose a preset if one is available.
3. Describe the voice you want. Include details such as:
   - Perceived voice type.
   - Approximate age range (for a fictional voice).
   - Pitch: low, medium or high.
   - Tone: warm, calm, energetic, serious or friendly.
   - Accent and language.
   - Speaking style and pace.
4. Write a short test script.
5. Generate a sample.
6. Listen and adjust the description or available traits.
7. Use **New seed** if you want a different voice identity while keeping similar traits.
8. Save the design as a voice profile if the option is available.

Example description:

> A clear, friendly adult narrator with a medium-low pitch, warm tone, natural pacing and a neutral Indian English accent. The delivery should sound confident and conversational, not overly dramatic.

The result depends on the selected engine. A description cannot guarantee a particular real person's voice.

## 9. Dub a video into another language

The dubbing workspace can help translate speech and generate replacement audio aligned with the source video.

1. Open **Dub** / **Video Dubbing**.
2. Upload a video or audio file. If the app supports a video URL, use the URL import option.
3. Wait for the file preparation step to finish.
4. Select the spoken/source language, or leave it on Auto if appropriate.
5. Choose the target language.
6. Set the speaker count if the workspace asks for it.
7. Start transcription.
8. Review the source transcript. Correct names, numbers and mistakes.
9. Translate the transcript using the available translation option/provider.
10. Review and edit the translated lines. Machine translation can make mistakes.
11. Assign the correct voice to each speaker. Use different voices for different speakers when needed.
12. Review the timing and fit of each segment.
13. Generate the dubbed audio.
14. Preview the result and correct any lines that sound unnatural or do not fit.
15. Export the completed dub using the export/save control.

**Useful tip:** Always review the translated text before generating. A small translation error can change the meaning of the whole video. Dubbing long videos can take a considerable amount of time.

Some translation workflows require a translation provider to be configured in Settings. That provider may have its own account, API key or usage charges. VoiceStudio being free does not mean every external translation service is free.

## 10. Transcription and dictation

### Transcribe an audio/video file

1. Open the transcription feature or the relevant workspace.
2. Select or install an ASR (speech recognition) model.
3. Import your audio/video file.
4. Choose the spoken language if known, or use automatic detection if supported.
5. Start transcription.
6. Wait for processing to finish.
7. Review the text and correct names, punctuation and technical terms.
8. Copy or export the transcript using the available controls.

### Dictation

Dictation is useful when you want to speak instead of typing.

1. Open the Dictation feature/widget.
2. Choose the available transcription engine and language.
3. Check that your microphone is connected and selected in your operating system.
4. Allow microphone access when prompted.
5. Start dictation and speak clearly.
6. Stop recording and review the recognized text.
7. Copy or insert the result into your document or application using the available workflow.

The exact widget controls and keyboard shortcuts can vary by version and operating system.

## 11. Batch generation, narration and audiobooks

For longer projects, use the batch or queue features if they are available in your installed version.

A simple narration workflow:

1. Prepare your script and split it into chapters or manageable sections.
2. Open the narration/batch workspace.
3. Select the TTS engine and voice profile.
4. Add your text sections or jobs to the queue.
5. Review the order and settings.
6. Start the queue.
7. Monitor progress and retry failed jobs if necessary.
8. Listen to the generated sections.
9. Export the audio files and organize them by chapter.

For audiobooks, keep the narrator voice and speaking settings consistent. Proofread the text before generating because the app will generally speak exactly what you provide.

## 12. Models and model packs

A model is the AI engine that performs a task. Different engines have different strengths.

- **TTS models** generate speech from text.
- **Voice cloning models** use reference audio to imitate a voice.
- **Voice design models** generate voices from descriptions.
- **ASR models** convert speech into text.
- **Diarization models** help identify who spoke when.
- **Vocal separation models** separate vocals from other sounds.

### Choosing a model

Consider these points before downloading:

1. **Hardware:** Does it support CPU, CUDA, Apple Silicon or another accelerator?
2. **Memory:** Does the model fit your available RAM or VRAM?
3. **Language:** Does it support the language and accent you need?
4. **Quality:** Listen to a sample if one is available.
5. **Speed:** Larger models may sound better but take longer.
6. **Licence:** Check whether the model permits personal or commercial use.

VoiceStudio includes a default OmniVoice-based engine and supports additional engines. The Model Manager is the source of truth for what is currently available in your installed release.

## 13. Audio quality and export settings

VoiceStudio offers audio-quality controls. Exact controls depend on the selected engine.

Common settings include:

- **Standard / 16-bit PCM:** A practical option for everyday listening and sharing.
- **24-bit PCM / For editing:** Useful when you plan to edit the audio in an audio editor.
- **32-bit float / Original:** Useful for compatible post-production workflows and larger files.
- **Voice refinement / sampling steps:** More computation can improve refinement for supported engines, but it can take longer.
- **Even out volume / mastering:** Helps balance loud and quiet parts where supported.
- **Speed and duration:** Adjusts delivery where supported.
- **Cleanup:** Applies supported audio cleanup or processing.

A higher WAV bit depth does not magically make a voice sound more realistic. It changes the exported audio format; the model and reference recording have a much bigger effect on voice identity and naturalness.

**Recommended starting point:** Keep the default quality settings, generate a short sample, and only change settings when you know what you want to improve.

For more technical detail, see the [official audio-quality guide](https://github.com/debpalash/VoiceStudio/blob/main/docs/audio-quality.md).

## 14. Advanced tools and automation

These features are mainly for developers and advanced users. You can skip this section if you only want to generate voiceovers.

- **Local API:** Allows compatible software and scripts to send jobs to a local VoiceStudio backend.
- **MCP server:** Allows compatible AI assistants/agents to discover and call supported VoiceStudio tools.
- **Recipes:** Save or reuse repeatable workflows where supported.
- **Watch folders:** Automate supported tasks when files arrive in a configured folder.
- **CLI:** Current desktop releases include a command-line interface. Run `voicestudio --help` in a new terminal after installation to see the commands available in your version.

Use the [official documentation](https://github.com/debpalash/VoiceStudio/tree/main/docs) for API, MCP and CLI setup. Do not expose a local API or server to the public internet without understanding authentication and network security.

## 15. Tips for better results

1. Record in a quiet room.
2. Keep the microphone at a consistent distance.
3. Avoid background music in voice-cloning samples.
4. Use an accurate transcript for the reference recording when requested.
5. Test with a short script before generating a long project.
6. Use punctuation to guide pauses and sentence rhythm.
7. Write numbers, abbreviations and difficult names in a way the model can pronounce correctly.
8. Choose an engine that supports your language.
9. Close games and GPU-heavy applications if you run out of VRAM.
10. Do not install every model. Keep only the models you use.
11. Compare a few short takes before deciding on final settings.
12. Keep a backup of important voice profiles and project files.

## 16. Troubleshooting

### The first launch takes a long time

The app may be preparing its Python environment and downloading models. Keep the app open and check your internet connection and available disk space.

### Model download is stuck or fails

- Check your internet connection.
- Check whether you have enough free disk space.
- Retry the download.
- If the model requires access approval, follow the model's Hugging Face instructions.
- If you use a Hugging Face token, check that it is valid.
- See the [official model-download guide](https://github.com/debpalash/VoiceStudio/blob/main/docs/downloading-models.md).

### Voice generation is very slow

- Check **Settings → Performance** to see whether the app is using CPU, CUDA or another supported device.
- The first generation can be slower because the model has to load.
- Try a smaller or lighter engine.
- Close other applications using RAM or VRAM.
- Reduce the script length for testing.
- Do not assume your GPU is being used just because your PC has one.

### Out of memory / CUDA error

- Close games, browsers and GPU-heavy applications.
- Try a smaller model.
- Restart VoiceStudio to release memory.
- Check that your NVIDIA driver is up to date.
- Use CPU mode if necessary, understanding it will be slower.

### The generated voice does not sound like me

- Use a cleaner reference recording.
- Remove music and background noise.
- Make sure only one person is speaking.
- Check that the transcript matches the recording exactly.
- Try another supported engine or a different reference sample.

### The pronunciation is wrong

- Check the language setting.
- Rewrite difficult names or abbreviations phonetically.
- Add punctuation and split very long sentences.
- Try another engine that supports the language better.

### The app cannot access the microphone

- Check the operating system's microphone privacy settings.
- Select the correct input device.
- Close other apps that may be using the microphone.
- Restart VoiceStudio after changing microphone permissions.

### Where can I find logs and diagnostics?

Use **Settings → About → Run self-check** if available in your release. It checks common issues such as the compute device, disk space, model setup and dependencies. The app may also offer a diagnostic bundle. Review it before sharing because logs can contain local system information.

For more fixes, visit the [official troubleshooting guide](https://github.com/debpalash/VoiceStudio/blob/main/docs/install/troubleshooting.md).

## 17. Privacy, permissions and licences

- VoiceStudio is designed for local processing. Your audio is generally processed on your own computer when using local engines.
- Model downloads require internet access. Optional integrations or external providers may send data to those services.
- Review any first-run analytics consent prompt and the app's privacy settings.
- Only clone a voice that belongs to you or that you have clear permission to use.
- Never use voice cloning to impersonate someone, deceive people, commit fraud or create misleading recordings.
- The application code is licensed under **AGPL-3.0**. Model weights and third-party engines have separate licences. Some models are restricted to non-commercial use.
- Before using generated audio in client work, advertising or monetized content, check the licence for the exact model you used. The app's open-source licence does not automatically grant commercial rights to every model.

## 18. Official links

- [VoiceStudio source repository](https://github.com/debpalash/VoiceStudio)
- [Download the latest release](https://github.com/debpalash/VoiceStudio/releases/latest)
- [Official documentation](https://github.com/debpalash/VoiceStudio/tree/main/docs)
- [Windows installation guide](https://github.com/debpalash/VoiceStudio/blob/main/docs/install/windows.md)
- [Linux installation guide](https://github.com/debpalash/VoiceStudio/blob/main/docs/install/linux.md)
- [macOS installation guide](https://github.com/debpalash/VoiceStudio/blob/main/docs/install/macos.md)
- [Docker installation guide](https://github.com/debpalash/VoiceStudio/blob/main/docs/install/docker.md)
- [Model catalogue and features](https://github.com/debpalash/VoiceStudio/blob/main/docs/feature-catalog.md)
- [Troubleshooting](https://github.com/debpalash/VoiceStudio/blob/main/docs/install/troubleshooting.md)
- [My Instagram introduction video](https://www.instagram.com/reel/Df9U5YGhNdz/?lqvp=MWg3azgzOGR5Ynl1Zw==)

---

**Guide maintained by [The UG Ultimatum](https://github.com/TheUGultimatum).** VoiceStudio is an independent open-source project. This guide is community documentation and is not an official guide from the VoiceStudio developers. Screens, labels and available engines may change as the upstream project updates.
