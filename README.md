# ClaudeOS

ClaudeOS is an AI-native operating system concept for Raspberry Pi–powered AR glasses and drones. It organizes everything by meaning instead of folders, and treats Claude as a supervised operator that plans, explains and acts within clear safety rules.

**Status:** Phase 1 prototype (v0.1). The local-first Object Core is implemented as a Rust CLI and lightweight web view backed by SQLite. Hardware integration, cloud sync, Claude API access, and flight control are not implemented.

## Design spec

Read the full design: [ClaudeOS-Design-Spec.md](ClaudeOS-Design-Spec.md)

It covers:

- An object-based organization model (inspired by Anytype, ArcGIS Pro and FME Workbench) with automatic labeling and "Claude AI, find…" search
- ClaudeOS Cloud sync, quantum-readiness (post-quantum security, a QPU slot, a Quantum Lab) and the system architecture
- Diagnostics and emailed bug reports
- Privacy and consent rules, including signed introductions between glasses wearers
- Voice: the "Claude AI" assistant, universal headset support, calls between drone operators and drone voice commands
- Blueprint, the built-in engineering design app (3D, GIS and AutoCAD-compatible drawings)
- Street Safety: area risk, real-time approach alerts, place risk factors and theft protection
- Safety rules, a worked drone-survey example, the roadmap and open decisions

## Phase 1 prototype

Requires Rust stable and Cargo. Run commands from this directory:

```powershell
cargo run -- space list
cargo run -- object create --type Note --title "North field survey" --properties '{"status":"planned"}'
cargo run -- query --type Note --search survey
cargo run -- serve
```

The web view is available at `http://127.0.0.1:8765`. Data is stored locally in `.claudeos/claudeos.sqlite`; set `CLAUDEOS_HOME` or pass `--database <path>` to choose another location. The CLI supports Spaces, Objects, typed Links, graph queries, undo, and editable redacted bug reports (`cargo run -- bug-report`). Unexpected panics automatically write a privacy-safe report under `reports/`. Reports are local files; review them and send them yourself.

Every property records its setter and timestamp. The built-in `Personal` Space is local-only by default. Created objects, links, and Spaces are written to the Journal, and `undo` reverses the latest creation.
