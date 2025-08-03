# Agent Instruction File

## 🎮 Project Overview
This repository contains the source code and assets for a **comic strip-style, choose-your-own-adventure video game**. The game uses **Godot 4.x** as the engine and is written primarily in **GDScript**, with external narrative files defined in **JSON** format.

The goal is to create a visually engaging story-driven experience where the player makes decisions that affect the branching narrative. Comic panels, speech bubbles, and illustrated scenes form the core presentation.

---

## 🧠 Agent Goals
You are an LLM (e.g., OpenAI Codex) assisting with:
- Writing and updating GDScript for the Godot engine.
- Managing external narrative files (JSON).
- Automating repetitive scripting tasks (e.g., new scene templates).
- Assisting with bug fixes, refactoring, and documentation.
- Helping designers write and test narrative content in structured formats.

---

## 🔧 Coding Instructions

### 1. Game Architecture
- The game reads scenes from structured `.json` files.
- Each scene contains:
  - A background image
  - An ordered list of comic panels (images)
  - Dialogue text per panel
  - Optional branching choices with scene IDs

### 2. JSON Scene Format Example

```json
{
  "id": "scene1",
  "background": "forest_day.png",
  "panels": [
    {
      "image": "panel1.png",
      "text": "You wake up in a dark forest."
    },
    {
      "image": "panel2.png",
      "text": "A path splits ahead. Which way will you go?",
      "choices": [
        { "text": "Left", "next": "scene2a" },
        { "text": "Right", "next": "scene2b" }
      ]
    }
  ]
}
```

### 3. GDScript Goals

* Load JSON files dynamically based on current scene.
* Display background, then each panel image and its associated text.
* Show user choices when present and wait for input.
* Transition to the next scene based on user selection.

### 4. Directories

```
/assets/images/      → comic panels and backgrounds
/assets/audio/       → music and sound effects
/scripts/            → GDScript files
/data/scenes/        → JSON scene files
```

### 5. Functions the Agent May Implement

* `load_scene(scene_id: String) -> void`
* `show_panel(panel_data: Dictionary) -> void`
* `display_choices(choices: Array) -> void`
* `transition_to_scene(next_scene_id: String) -> void`
* JSON schema validator or generator

---

## ✍️ Authoring Support

Codex can also:

* Auto-generate a new scene template given plain English description.
* Refactor existing JSON or GDScript for readability or modularity.
* Build visual tools for story designers.

---

## 💬 Behavior Expectations

* Prioritize simplicity and clarity in code.
* Use comments to explain logic, especially around user input and scene transitions.
* Always validate JSON before loading scenes.
* Reuse reusable UI components (e.g., panel display, choice buttons).

---

## ✅ Definition of Done

* Panel images and dialogue are shown in order.
* Choices appear only when defined in the JSON.
* Selecting a choice correctly transitions to the next scene.

---

## 🌍 Deployment

* Pushing to `main` triggers `.github/workflows/deploy.yml`.
* The workflow installs Godot headless and HTML5 export templates.
* It exports the project using the `Web` preset to `build/`.
* The contents of `build/` are published to the `gh-pages` branch via `peaceiris/actions-gh-pages`.
* The latest build is available at `https://<username>.github.io/<repository-name>/`.
