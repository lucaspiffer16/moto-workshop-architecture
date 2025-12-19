# ADR-001: Use .NET MAUI for the Desktop Application

## Status
Accepted

## Context
The project is a Windows-first management system for a small motorcycle workshop. The application must be reliable, maintainable, and capable of evolving to mobile in the future without rewriting the core.

Alternatives considered:
- Tauri/Electron (web wrapper)
- Flutter (cross-platform UI framework)
- WinUI/WPF (Windows-only)

## Decision
Use **.NET MAUI** for the desktop application.

## Consequences
### Positive
- Native .NET ecosystem, strong tooling, and long-term support.
- Shared approach for future mobile expansion (Android/iOS) without changing the language/runtime.
- Fits well with MVVM, DI, and feature-based organization.

### Negative / Trade-offs
- UI polish and community examples may be less abundant than web stacks.
- Requires care to keep UI responsive (async, background tasks).
- Windows-first now; multi-platform UI parity may require future adjustments.
