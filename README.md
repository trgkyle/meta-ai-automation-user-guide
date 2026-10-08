[![Download Here](https://img.shields.io/badge/⬇_Download-Here-success?style=for-the-badge)](https://chromewebstore.google.com/detail/meta-automation-auto-meta/pcmcomcmgpmnpdmkdgjnipeipchbfchf?authuser=2&hl=vi)

# 🚀 Meta Automation v1.0.0 - Meta.ai AI Automation [![Tiếng Việt](https://img.shields.io/badge/Tiếng%20Việt-green)](README_vi.md) [![中文](https://img.shields.io/badge/中文-red)](README_zh.md)

**Meta Automation** is a productivity tool that automates your creative workflow on Meta.ai. Stop manually entering prompts one by one—automate the process and generate videos and images at scale.

-----

## ✨ Key Features

* **🚀 Batch Processing:** Queue dozens or hundreds of prompts and let the extension handle submission and generation automatically.
* **🧩 Workflow (visual drag-and-drop editor):** Connect prompts, images and generators on a canvas — e.g. generate images, then turn those images into videos automatically. Save several workflows, run one node or all of them, import/export them as files.
* **🎬 Text-to-Video Automation:** Generate videos from text descriptions. Supports batch processing with custom delays.
* **🎬 Image-to-Video:** Use a source image and prompts to create dynamic videos.
* **🖼️ Text-to-Image Batching:** Create multiple images with support for aspect ratios (16:9, 9:16, 1:1).
* **🖼️ Image-to-Image:** Generate image variations from a source image and prompts.
* **⚙️ Professional Controls:**
    * **Concurrent Prompts:** Process multiple prompts at once to save time.
    * **Smart Delays:** Set custom intervals between prompts to manage rate limits.
    * **Auto Download:** Automatically download results when generation completes.
* **📊 Real-time Queue Monitoring:** Monitor progress with a visual status bar and active prompt list in the Side Panel.
* **📂 Organized File Management:** Downloads are sorted into project-based folders.
* **🌐 Multi-language Support:** English, Vietnamese, Chinese, Korean, Japanese, Spanish.

-----

## 📥 Installation

### Method 1: Chrome Web Store (Recommended)
1. Visit the [Chrome Web Store](https://chromewebstore.google.com/detail/meta-automation-auto-meta/pcmcomcmgpmnpdmkdgjnipeipchbfchf?authuser=2&hl=vi) and click **Add to Chrome**.

---

## 📖 User Guide

### Getting Started

1. **Navigate to Meta.ai**
   - Open [meta.ai/media](https://www.meta.ai/media) (or [meta.ai](https://meta.ai))
   - The extension works on Meta.ai Media pages.

2. **Open the Extension**
   - Click the extension icon in the Chrome toolbar. Pin it for easier access!

3. **Configure Batch Settings**
   - In the **Control** tab, you can set:
     - **Concurrent Prompts:** How many prompts to run at the same time.
     - **Prompt Delay:** Wait time between each prompt submission.

4. **Select a Mode**
   - Choose from: **Text to Video**, **Image to Video**, **Text to Image**, or **Image to Image**.

### 1. Text-to-Video Mode

1. Select **Text to Video** mode.
2. Enter prompts into the input box (separate each prompt with a **blank line**).
3. Alternatively, click the **Upload** icon to import prompts from a `.txt` file.
4. Click **Run** to start the batch.

**Example Prompt:**
```
A futuristic cyberpunk city with neon lights reflecting in the rain.
The camera glides through the narrow alleys.

A peaceful Japanese garden with cherry blossoms falling into a pond.
A slow zoom into the koi fish swimming below.
```

### 2. Image-to-Video Mode

1. Select **Image to Video** mode.
2. Click to upload or drag & drop a source image.
3. Enter prompts (separate with blank lines). The image will be used with each prompt.
4. Click **Run**.

### 3. Text-to-Image Mode

1. Select **Text to Image** mode.
2. Enter detailed descriptions for your images.
3. Configure the desired **Aspect Ratio** in the Settings tab.
4. Click **Run**.

### 4. Image-to-Image Mode

1. Select **Image to Image** mode.
2. Upload a source image.
3. Enter prompts for image variations.
4. Click **Run**.

### 🧩 Workflow (Visual Drag-and-Drop Editor)

Workflow is a visual drag-and-drop editor for flows with several steps — for example: generate a few images, then use those images to make videos, then continue each video with another prompt. It opens in its own window and runs on your open meta.ai tab.

#### Open it

* Click **Workflow** in the Control tab (bottom row).
* Already typed prompts or uploaded images in the side panel? Hover **Workflow** and click **Convert to workflow**: your prompts, each prompt's mode and your images become nodes in the editor, ready to run.

#### The screen

| Area | What it holds |
| :--- | :--- |
| **Left** | **Nodes** (click or drag one onto the canvas) and **Your workflows** (all saved workflows) |
| **Top bar** | The canvas tools: Undo/Redo, **Auto arrange**, fit view, **Example**, clear. On the right: the **Details** button, **Shortcuts** and the meta.ai tab status |
| **Canvas** | Your nodes. Top-left: **Run all** (and **Stop** while running) and **Enable background mode** |

The **Details** button shows what needs attention: **Issues (n)** in red/yellow when something blocks a run, **Running 3/8** while generating. Click it to open a panel with the issues (click one to jump to the node), live progress, the run plan and the settings it uses.

#### Nodes

| Node | What it does |
| :--- | :--- |
| **Enter prompt** | One or more prompts, separated by a **blank line** |
| **Upload image** | Your images (drop files on it). Hover an image: 🔍 to view it larger, ✕ to remove it, the grip in the corner to drag it to another position. The order (or the sort menu) decides which prompt gets which image |
| **Generate Image** | Text to Image, or Image to Image when images are connected. Options: **Image Mode per Prompt**, **Max Input Images per Prompt**, **Auto-add character images** |
| **Generate Video** | Text to Video, or with images connected **Frame to Video** / **Components to Video**. Options: **Video Mode per Prompt**, images per prompt (shared with the side panel settings), **Auto-add character images** (Components to Video) |

Generate nodes are named automatically from their first prompt (`image_…` / `video_…`). Each prompt row shows the images it will receive, so you can check before running. Their preview takes the **aspect ratio** from the settings (a 9:16 node is narrower and taller).

**Frame to Video** can use a start frame only, or a **start frame and end frame** (same setting as the side panel). With start and end frame each prompt takes 2 images in order (a prompt continuing the previous video takes 1); if there are not enough images, the node shows a warning and can't run.

#### Connect nodes

Drag from the round handle on the right of a node and **drop it anywhere on the other node** — the right input is picked for you. Nodes that accept the connection light up while you drag.

| From | To | Meaning |
| :--- | :--- | :--- |
| Enter prompt | Generate Image / Generate Video | The prompts to generate |
| Upload image | Generate Image / Generate Video | Reference images, start frames or components |
| Generate Image | Generate Image / Generate Video | The **generated images** become that node's input (it runs after the images are ready) |
| Generate Video — **last frame** output | Generate Video | The next video **continues from the last frame** of this one |
| Generate Video — **last frame** output | Generate Image | The **last frame** of each video becomes an input image (it runs after the video is ready) |

#### Run

* **Run all** (top-left, or `Ctrl/⌘ + Enter`) runs the whole workflow in the right order: nodes waiting for generated images start automatically once those images exist.
* If **Run all** is disabled, the top bar shows **Issues (n)**: click it to see what to fix.
* Each Generate node also has its own **Run** button to run only that node. It is disabled until the nodes it depends on have finished (hover to see why).
* **Stop** cancels what is still running.
* While running, the connections into the node that is generating light up and flow, so you can see where the workflow is.

> ⚠️ **Chrome pauses meta.ai when its tab isn't visible** (for example when the workflow window covers it full screen). Click **Enable background mode** (under **Run all** in the workflow, or in the side panel), then pick the meta.ai tab in Chrome's dialog. This shares the meta.ai tab (nothing is recorded or sent anywhere) so it keeps generating behind other windows. The green **Running in background** badge shows it's on; click ✕ to stop it.

#### Results

Results appear inside each Generate node. Hover a result: 🔍 opens it large, ✕ removes it (the eraser clears all results of the node). Videos play on hover. Files are still downloaded as usual.

The next node uses the **first result of each prompt**. To choose which one, drag a result by the grip in its top-left corner onto another result to swap them (images and videos).

#### Manage workflows

Under **Your workflows** (left): **New**, **Import**, and for each workflow the **⋯** menu — **Rename** (or double-click the name), **Duplicate**, **Export**, **Delete**. Everything is saved automatically.

* **Export** downloads a `.json` file. It starts with `//` comment lines that describe every node, property and connection, so you can give the file to an AI assistant and ask it to write new workflows. The comment lines are removed on import.
* **Import** a file with the button, or simply **drag the `.json` file onto the canvas**.

#### Editing shortcuts

Click **Shortcuts** in the top bar (or press `?`) to see them all.

| Action | Keys |
| :--- | :--- |
| Undo / Redo | `Ctrl/⌘ + Z` / `Ctrl/⌘ + Shift + Z` |
| Copy / Cut / Paste nodes (also into another workflow) | `Ctrl/⌘ + C / X / V` |
| Duplicate selection | `Ctrl/⌘ + D` |
| Select all / Add to selection / Box select | `Ctrl/⌘ + A` / `Ctrl/⌘ + click` / `Shift + drag` |
| Auto arrange | `Shift + A` |
| Delete selected | `Delete` |
| Run all / Run in background | `Ctrl/⌘ + Enter` / `Ctrl/⌘ + Shift + Enter` |

---

## ⚙️ Settings Configuration

Access the **Settings** tab to customize your experience:

* **Default Mode:** Set which mode opens by default.
* **Default Aspect Ratio:** Choose from 16:9, 9:16, or 1:1.
* **Outputs per Prompt:** Set how many videos or images to generate per prompt.
* **Auto Download:** Enable automatic download when generation completes.
* **Language:** Switch between English, Tiếng Việt, 中文, 한국어, 日本語, Español.

---

## 💡 Tips & Best Practices

1. **Wait Times:** If you hit rate limits, increase **Prompt Delay** in the Control tab.
2. **Concurrent Runs:** Start with 1 concurrent prompt and increase slowly based on what your account allows.
3. **Prompting:** Be specific. Detailed prompts lead to better results. Separate multiple prompts with a blank line.
4. **File Organization:** Downloads are automatically sorted into project-based folders.

---

## 🔧 Troubleshooting

| Issue | Solution |
| :--- | :--- |
| **Extension not active** | Ensure you are on [meta.ai](https://meta.ai) or [meta.ai/media](https://www.meta.ai/media). Refresh the page if needed. |
| **Generation Errors** | Meta.ai may be busy. The extension will retry based on your settings. |
| **Downloads not working** | Ensure "Ask where to save each file before downloading" is **OFF** in Chrome Settings. |
| **Login Required** | Make sure you are logged into your Meta.ai account. |
| **Workflow: generation stays at "Generating" forever** | Chrome paused the hidden meta.ai tab. Turn on **Enable background mode** (or **Run in background**), or keep meta.ai visible. |
| **Workflow: a node's Run button is disabled** | Hover it: run the node it depends on first, or fix the issue shown (e.g. no prompt connected). |
| **Workflow: Run all is disabled** | Click **Issues (n)** in the top bar to see what to fix; click an issue to jump to its node. |
| **Workflow: "No meta.ai tab found"** | Open [meta.ai](https://www.meta.ai) in a tab (the green dot in the top bar shows it's connected). |

---

## 🔒 Privacy & Data

* **Local Processing:** All automation logic runs locally in your browser.
* **No Data Collection:** We do not store or collect your prompts, images, or account data.
* **Secure Storage:** Settings are saved only in your browser's local storage.

---

## 📞 Support

- **Author:** Trường Nguyễn
- **Website:** [kylenguyen.me](https://kylenguyen.me)
- **Feedback:** Use the "Report a bug" link in the extension.

---

## 📦 Version

Current version: **1.0.0**

---

## 📜 License

Copyright © 2026 **Trường Nguyễn**. All Rights Reserved.

This software is proprietary. Unauthorized copying or distribution is prohibited.

---

**Made with ❤️ by Trường Nguyễn**
