# GDD — Dialogue System

*Tidewrack — Fogline Games · design doc · last updated 2026-03-06 · gdd, dialogue, code*

## DialogueManager
`scripts/autoload/dialogue_manager.gd` — an autoload that loads a **JSON branching graph** and walks it
node by node. Each node has an id, a speaker, lines, and a list of choices; each choice names the next
node and, optionally, a flag to set. The graph is data, not code, so writing is editing JSON — not GDScript.

## The vertical-slice conversation
`keeper_intro.json` is the slice's long pole: the first real conversation, exercising every system at once
(dialogue, flags, interactables). If it holds up, the architecture holds up.

## Validation
`validate_dialogue.py` is an **engine-free** checker (stdlib Python): it loads every graph, confirms every
choice points at a node that exists, flags orphan nodes and dead ends, and lists every flag the graph sets.
It runs in CI-for-one — before I commit a graph, I run the validator. See the
[dialogue-graph spec](../narrative/dialogue-graph-spec.md).
