# ADR-004: Feature-Based MVVM Architecture

## Status
Accepted

## Context
The system will grow across multiple functional areas (work orders, customers, motorcycles, stock, payments). Without clear boundaries, MAUI projects can devolve into cross-referenced folders and tightly coupled UI/data code.

Alternatives considered:
- Layer-only organization (Views/ViewModels/Services)
- Feature-only without layers (mixed responsibilities)

## Decision
Use **MVVM** with a **feature-based (vertical slice)** structure:
- Each feature owns its Presentation (Views/ViewModels), Application (use cases), and Domain elements.
- Infrastructure (SQLite, printing) implements interfaces and stays isolated from UI.

Dependency rules:
- Presentation → Application → Domain/Core
- Infrastructure → Domain/Core
- No direct Presentation → Infrastructure access

## Consequences
### Positive
- Clear boundaries, easier maintenance, and safer refactoring.
- Features remain isolated and testable.
- Scales better as new features are added.

### Negative / Trade-offs
- Requires discipline to avoid shortcut dependencies.
- Slight upfront structure cost, repaid as the project grows.
