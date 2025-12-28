# Agent Guidelines for ram

## Build Commands
- `npm start` - Start Angular dev server (port 1420)
- `npm run build` - Build Angular for production
- `npm run tauri dev` - Run Tauri + Angular in dev mode
- `npm run tauri build` - Build Tauri application
- `npm test` - Run Angular tests (if test script exists)
- Single test: `ng test --include="**/component-name.spec.ts"`

## Code Style - Angular/TypeScript
- Use Angular 21+ standalone components with `standalone: true`
- TypeScript strict mode enabled: explicit types, no implicit returns
- Event handlers return `void`
- Tauri commands: `invoke<Type>("commandName", { params }).then((result) => {...})`
- Import order: @angular packages first, then third-party, then relative imports
- Component naming: PascalCase for classes, kebab-case for selectors

## Code Style - Rust
- Rust 2021 edition
- Use `#[tauri::command]` macro for Tauri commands
- Commands take `&str` or deserialized structs, return `String` or `Result<T, E>`
- Use `format!` macro for string formatting
- Panic handling with `.expect()` for fatal errors

## General
- No ESLint/Prettier configured - follow Angular Style Guide
- CSS files: kebab-case naming (component-name.css)
- HTML templates: use Angular template syntax, no custom tags
