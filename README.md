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
