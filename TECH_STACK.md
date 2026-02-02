# Technology Stack

This document outlines the technology stack and computer languages used in the TailwindCSS project.

## Core Programming Languages

### Rust
- **Version**: 1.85.0 (specified in `rust-toolchain.toml`)
- **Purpose**: High-performance CSS engine and core processing logic
- **Location**: `crates/` directory
  - `oxide` - Main CSS processing engine
  - `node` - Node.js bindings via N-API
  - `ignore` - File pattern matching and gitignore handling
  - `classification-macros` - Macro utilities

**Key Rust Dependencies**:
- `napi` & `napi-derive` - Node.js N-API bindings
- `rayon` - Data parallelism
- `regex` - Regular expression support
- `walkdir` & `globwalk` - File system traversal
- `tracing` - Diagnostic logging

### TypeScript
- **Version**: ^5.5.4
- **Purpose**: Type-safe JavaScript development for tooling and integrations
- **Location**: All `packages/` and integration code
- **Configuration**: Multiple `tsconfig.json` files for different packages

### JavaScript
- **Purpose**: Build scripts, configuration files, and runtime code
- **Module System**: CommonJS and ES Modules (dual exports)

### CSS
- **Purpose**: Core utility framework styles, theme definitions, and preflight styles
- **Files**: `index.css`, `preflight.css`, `theme.css`, `utilities.css`

## Build Tools & Package Management

### Package Managers
- **pnpm**: v9.6.0 (specified in `packageManager` field)
- **pnpm Workspace**: Monorepo management across multiple packages
- **Cargo**: Rust package manager

### Build Systems
- **Turbo**: v2.7.2 - Monorepo build orchestration
- **tsup**: v8.5.1 - TypeScript bundler
- **Cargo**: Rust build system with workspace support

### Bundlers & Tooling
- **Vite**: v7.0.0 (catalog) - Next-generation frontend tooling
- **Webpack**: v5 (catalog) - Module bundler integration
- **PostCSS**: v8.5.6 - CSS transformation tool
  - `postcss-import` v16.1.1 - Import handling

## CSS Processing

### LightningCSS
- **Version**: 1.30.2
- **Purpose**: Fast CSS parser, transformer, and minifier
- **Platform Support**: Multiple platform-specific binaries
  - darwin-arm64, darwin-x64
  - linux-arm64-gnu, linux-arm64-musl
  - linux-x64-gnu, linux-x64-musl
  - win32-x64-msvc

## Testing Framework

### Vitest
- **Version**: ^4.0.3
- **Purpose**: Unit and integration testing
- **Configuration**: `vitest.config.ts`
- **Coverage**: Tests across all packages

### Playwright
- **Version**: ^1.57.0
- **Purpose**: End-to-end and UI testing
- **Tests**: UI validation for browser and core packages

## Development Tools

### Code Quality
- **Prettier**: v3.6.2 (catalog) - Code formatter
  - `prettier-plugin-organize-imports` v4.3.0
  - `prettier-plugin-embed` v0.5.1
- **TypeScript Compiler**: Type checking and linting

### Source Maps
- **magic-string**: ^0.30.21 - String manipulation with source maps
- **source-map-js**: ^1.2.1 - Source map generation
- **@jridgewell/remapping**: ^2.3.4 - Source map remapping

## Package Ecosystem

### Core Packages
- `tailwindcss` - Main framework package
- `@tailwindcss/oxide` - Rust-powered CSS engine
- `@tailwindcss/cli` - Command-line interface
- `@tailwindcss/node` - Node.js bindings
- `@tailwindcss/browser` - Browser-compatible version

### Framework Integrations
- `@tailwindcss/postcss` - PostCSS plugin
- `@tailwindcss/vite` - Vite plugin
- `@tailwindcss/webpack` - Webpack plugin

### Utilities
- `@tailwindcss/upgrade` - Migration tooling
- `@tailwindcss/standalone` - Standalone distribution
- `internal-example-plugin` - Plugin development example

## Runtime Environments

### Node.js
- **Supported Versions**: Compatible via N-API (Node-API version 4+)
- **Type Definitions**: @types/node v20.19.0 (catalog)

### Browsers
- Modern browsers with CSS support
- Browser-specific package for client-side usage

## Development Playgrounds

### Framework Examples
- **Next.js playground**: React framework integration
- **Vite playground**: Modern build tool integration
- **V3 playground**: Version 3 compatibility testing

### File Types
- `.tsx` - TypeScript + JSX (React components)
- `.ts` - TypeScript files
- `.js` - JavaScript files
- `.rs` - Rust source files
- `.css` - Stylesheet files

## Additional Tools

### Other Dependencies
- `dedent`: Template string formatting
- `tempfile`: Temporary file creation (Rust)
- `fxhash` (rustc-hash): Fast hashing
- `bexpand`: Brace expansion
- `fast-glob`: Fast glob matching

## License

MIT License (as specified in package.json and LICENSE file)

## Repository

- **URL**: https://github.com/tailwindlabs/tailwindcss
- **Structure**: Monorepo with multiple packages and Rust crates
- **Workspace**: pnpm workspace + Cargo workspace

---

*This document reflects the technology stack as of the latest version. For specific version requirements, refer to `package.json`, `Cargo.toml`, and configuration files in the repository.*
