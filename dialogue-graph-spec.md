# Narrative — Dialogue Graph Spec

*Tidewrack — Fogline Games · design doc · last updated 2026-03-06 · narrative, dialogue, spec*

## Format
A dialogue graph is one JSON object: `{ "start": "<node id>", "nodes": { ... } }`. Each node:

```json
{
  "id": "edith_log_01",
  "speaker": "Edith (log)",
  "lines": ["The north light answered again tonight.", "Three long, one short. The same as Tuesday."],
  "choices": [
    { "text": "Write it down.",        "next": "log_recorded", "set": "believer" },
    { "text": "It's a passing ship.",  "next": "log_dismissed", "set": "skeptic" }
  ]
}
```

## Rules
- Every `next` must name a node that exists (checked by `validate_dialogue.py`).
- `set` is optional and names one of the canonical flags.
- A node with no choices is a leaf (an ending or a return-to-world).
- No node may be unreachable from `start`.

## Validation
`validate_dialogue.py` (engine-free) enforces all of the above and prints the flag set each graph touches,
so writing stays honest without opening Godot.
