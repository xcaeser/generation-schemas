# 🎨 Image Generation Prompt Schema

This repository defines a structured **JSON Schema** for describing scenes used in **AI-based image generation** (e.g. with ChatGPT, etc).

## ✅ Usage in JSON

```json
{
  "$schema": "https://raw.githubusercontent.com/xcaeser/generation-schemas/main/schemas/v1.0.0/image-generation.schema.json",
  "scene": "urban café terrace in Paris during golden hour",
  ...
}
```

## 🧠 Schema Fields Overview

| Field           | Type   | Description                            | Example                                                     |
| --------------- | ------ | -------------------------------------- | ----------------------------------------------------------- |
| `version`       | string | Schema version                         | `"1.0.0"`                                                   |
| `scene`         | string | Summary of the overall scene           | `"urban café terrace in Paris during golden hour"`          |
| `subjects`      | array  | List of people/characters in the image | see below (#example-subject-entry)                          |
| `style`         | string | Visual style of the image              | `"hyper-realistic photography"`                             |
| `lighting`      | string | Type of lighting used                  | `"golden hour with soft shadows and sun flare"`             |
| `mood`          | string | Emotional tone of the scene            | `"warm and intimate"`                                       |
| `background`    | object | Background elements and depth of field | `{ "elements": ["bicycles"], "depth_of_field": "blurred" }` |
| `composition`   | string | Visual layout strategy                 | `"framed using rule of thirds"`                             |
| `camera`        | object | Camera angle, distance, and focus      | `{ "angle": "eye level", "distance": "medium", ... }`       |
| `color_palette` | array  | Main colors to include                 | `["warm gold", "navy", "espresso brown"]`                   |
| `props`         | array  | Physical objects in the image          | `["coffee cups", "croissants", "notebook"]`                 |
| `resolution`    | string | Output resolution                      | `"4K"`                                                      |
| `text_overlays` | array  | Text elements shown inside the image   | see below (#example-text-overlay)                           |

## 👥 Example Subject Entry

```json
{
  "type": "young woman",
  "description": "30s, black hair in a bun, white blouse, tan trench coat",
  "pose": "sitting at a café table, leaning forward slightly",
  "position": "left foreground",
  "expression": "engaged, smiling softly"
}
```

## 📝 Example Text Overlay

```json
{
  "content": "Café de Paris",
  "position": "top-center",
  "style": "elegant script in gold",
  "size": "large"
}
```

## 🔗 Latest Schema

- [v1.0.0 JSON Schema](./schemas/v1.0.0/prompt.schema.json)
- `$id`: `https://raw.githubusercontent.com/xcaeser/generation-schemas/main/schemas/v1.0.0/image-generation.schema.json`

## 📦 Validation (optional)

```bash
npm install -g ajv-cli
ajv validate -s schemas/v1.0.0/prompt.schema.json -d your-prompt.json
```

## 🗂 Versions

| Version | Path                                | Status    |
| ------- | ----------------------------------- | --------- |
| 1.0.0   | `schemas/v1.0.0/prompt.schema.json` | ✅ Stable |

## 📄 License

MIT
