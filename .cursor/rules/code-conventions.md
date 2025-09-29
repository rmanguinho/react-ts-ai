- Naming conventions
  - Always respond in english
  - Use camelCase for variables, functions and constants
  - Use PascalCase for classes, types, interfaces and React components
  - Use kebab-case for file and folder names
  - Use verbs for boolean variables (isLoading, hasError)

- TypeScript
  - Use early returns when possible
  - Prefer unknown over any
  - Prefer undefined over null
  - Don't use comments

- Follow eslint rules (esling.config.js), specially:
  - Don't use trailing commas
  - Don't use semicolons
  - Prefer single quotes

- Imports
  - Use @/ for internal imports
  - Group imports by type: first external, then internal, separated by a blank line
  - Use imports in a single line