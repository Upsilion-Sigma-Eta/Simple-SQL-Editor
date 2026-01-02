# Repository Guidelines

## Project Structure & Module Organization
- Root contains the solution entry and repository-level files like `.gitignore` and `LICENSE`.
- `Solution/Solution.slnx` is the solution definition.
- `Solution/Main/` is the WPF app project (`Main.csproj`).
- `Solution/Main/App.xaml` defines app-wide resources and startup.
- `Solution/Main/MainWindow.xaml` is the primary UI view.
- `Solution/Main/bin/` and `Solution/Main/obj/` are build outputs.

## Architecture Overview
- Single WPF desktop app; `App.xaml` bootstraps `MainWindow`.
- UI lives in XAML with code-behind in `*.xaml.cs`; keep business logic in separate C# classes as it grows.

## Build, Test, and Development Commands
- `dotnet build Solution/Solution.slnx` builds all projects.
- `dotnet run --project Solution/Main/Main.csproj` runs the WPF app (Windows only).
- `dotnet clean Solution/Solution.slnx` removes build outputs.

## Coding Style & Naming Conventions
- C# uses 4-space indentation, braces on new lines, `PascalCase` for types/methods, and `camelCase` for locals/parameters.
- XAML uses 4-space indentation and aligned attributes for readability.
- Keep namespaces aligned with the folder path (for example, `Main` for `Solution/Main`).
- Prefer nullable-aware code; keep `Nullable` enabled.

## Testing Guidelines
- No test project yet. If you add tests, place them under `Solution/Tests/` or a new `*Tests` project, and run `dotnet test Solution/Solution.slnx`.
- Name test classes `*Tests` and test methods with clear behavior-driven names (for example, `Loads_Default_Window`).

## Commit & Pull Request Guidelines
- Use Conventional Commits (for example, `feat: add query editor`, `fix: handle empty connection string`). Keep the scope optional and the subject in imperative mood.
- PRs should include a short description, steps to verify (commands run), and screenshots for UI changes.

## Security & Configuration
- Do not commit secrets or connection strings. Prefer user secrets or local config files and add them to `.gitignore` when introduced.
