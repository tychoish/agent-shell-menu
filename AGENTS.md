# Agent Instructions for agent-shell-menu

This repository provides Emacs UI components for `agent-shell`. When working on this codebase, follow these guidelines:

## Architecture & Patterns

- **ACR Integration**: Extensive use of `annotated-completing-read` for interactive selection with metadata.
- **Transient Menus**: Primary UI entry points are `transient` prefixes. Use `transient-define-prefix` for new menus.
- **Buffer Context**: Many functions rely on identifying the relevant `agent-shell` buffer. Use `agent-shell--session-shell-buffer` to find the buffer from the current context (including viewports).
- **Separation of Concerns**: Keep UI logic (menus, completion) separate from the core `agent-shell` logic where possible.

## Testing

- **ERT**: All tests use the Emacs Regression Testing (ERT) framework.
- **Mocking**: Use `cl-letf` to mock external dependencies (like `agent-shell` or `annotated-completing-read`) in tests.
- **Location**: Tests are located in the `test/` directory.

## Style

- Use `lexical-binding: t`.
- Follow standard Emacs Lisp naming conventions (prefix symbols with `agent-shell-menu-` or `agent-shell-` as appropriate).
- Use `cl-lib` for functional utilities and `seq` for sequence operations.
