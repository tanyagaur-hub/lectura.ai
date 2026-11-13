# LecturaVoice AI — Live PDF Voice Teacher & Priority Scroll Bot

An interactive, browser-based AI voice teacher that reads and explains any uploaded PDF aloud while smoothly auto-scrolling through each section—while **always giving manual user scrolling top priority**.

## Core Features

1. **Drag-and-Drop PDF Parsing (`PDF.js`)**:
   - Drag and drop any `.pdf` lecture slide deck, textbook chapter, or research paper directly onto the classroom viewport.
   - Automatically extracts and chunks pages into structured teaching blocks with synchronized scroll coordinates.
2. **Explanation Depth Scroller (`1: High Efficiency` ↔ `5: High Depth`)**:
   - **Level 1 (High Efficiency / TL;DR)**: 1-sentence core takeaway + governing formula for rapid revision.
   - **Level 2 (Concise Overview)**: Brisk 2-sentence conceptual summary.
   - **Level 3 (Balanced Classroom)**: Standard live professor explanation.
   - **Level 4 (Detailed Analytical)**: Adds physical intuition and real-world engineering analogies.
   - **Level 5 (High Depth / First-Principles)**: Full deep-dive lecture covering physical mechanisms, derivations, analogies, and limiting/frequency behavior.
3. **Priority Scroll Arbiter (Human Always Beats Bot)**:
   - Listens to `wheel`, `touchmove`, scrollbar drag, and keyboard navigation events.
   - The moment you scroll manually, the bot yields scroll control (`USER_OVERRIDE`) with a configurable cooldown timer and a **"Teach This Visible Section"** button so it never fights your hand on the mouse or trackpad.
4. **Active Listening Feedback & Wake-Word State Machine**:
   - Continuous Web Speech API (`SpeechRecognition`) with echo-suppression guard and on-screen simulator triggers:
     - **`"doubt"`**: Immediately interrupts speech, highlights the active passage, and listens to your question.
     - **`"give me a minute"`**: Pauses speech and auto-scroll with an elapsed pause timer.
     - **`"continue"`**: Resumes teaching and auto-scrolling from the current section.

## Quick Start & Deploying to GitHub Pages

```bash
# 1. Initialize Git repository
git init
git add index.html README.md LICENSE .gitignore
git commit -m "Initial commit: LecturaVoice AI PDF Voice Teacher"

# 2. Push to your GitHub repository
git branch -M main
git remote add origin https://github.com/<your-username>/lecturavoice-ai-pdf-teacher.git
git push -u origin main
```

Once pushed, go to **Settings → Pages → Build and deployment**, select **Deploy from a branch (`main` / `/root`)**, and your live PDF voice teacher will be hosted on GitHub Pages.
