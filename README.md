# Comic Strip Story Game

A comic-style, choose-your-own-adventure video game built with **Godot 4.x**. The game presents a narrative through a series of illustrated panels and dialogue, with branching paths based on player choices.

---

## 🎯 Features

- Comic book layout with speech bubbles or panel captions
- JSON-based narrative scripting (easy to edit or auto-generate)
- Scene branching via player decisions
- Modular and expandable structure
- Designed to be easy for Codex/GPT assistance

---

## 📦 Directory Structure

````

/assets/images/      → Comic panel images and backgrounds
/assets/audio/       → Background music and sound effects
/scripts/            → All GDScript files
/data/scenes/        → Narrative JSON files
AGENTS.md            → Codex instructions for AI coding assistant
README.md            → Project overview

````

---

## 🧪 Requirements

- [Godot 4.x](https://godotengine.org/)
- Python (optional, for future tools or validators)
- VS Code (recommended, with GitHub Copilot)

---

## 🚀 Getting Started

1. Clone this repo.
2. Open the project in Godot.
3. Run `main.tscn` to start the game.
4. Add or edit scenes in `/data/scenes/scene_id.json`.

---

## 🧠 Creating a New Scene

Create a new JSON file like this:

```json
{
  "id": "scene_new",
  "background": "desert.png",
  "panels": [
    { "image": "panel1.png", "text": "You wander through the hot sand." },
    {
      "image": "panel2.png",
      "text": "You spot something glinting ahead.",
      "choices": [
        { "text": "Investigate", "next": "scene_gold" },
        { "text": "Ignore it", "next": "scene_ignore" }
      ]
    }
  ]
}
```

---

## 🧑‍💻 Codex Integration

This project is designed to work well with GitHub Copilot or GPT-based assistants. See `AGENTS.md` for AI guidance.

---

## 🛣️ Roadmap

* [ ] Base game loop: load → show panel → wait for input
* [ ] Scene transitions based on choices
* [ ] Sound/music integration
* [ ] UI polish (dialogue boxes, panel animations)
* [ ] Save/load system
* [ ] Export to PC and WebGL

---

## 📄 License

MIT License – feel free to use or adapt.

---

## ✨ Contributors

Created by Ava. AI-assisted by OpenAI Codex. 

