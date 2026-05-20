---
name: tdd-vitest
description: |
  Use ONLY when working with TypeScript and Vitest test files in this project.
  Provides rules for test file creation, running tests via npm scripts, and TDD best practices.
---

# TDD with TypeScript and Vitest

## Test File Creation
1. **Create specification file** with `.spec.ts` extension
2. **Import with explicit extensions** for local modules (e.g., `from "./module.js"`)
3. **Use Vitest testing functions** (`describe`, `it`, `expect`)
4. **Follow TDD red-green-refactor** cycle
5. **Leverage TypeScript's type checking** during development

## Running Tests — CRITICAL REQUIREMENTS

**🚨 ALWAYS use npm scripts defined in `package.json`**

### ✅ CORRECT — Use npm scripts:
```bash
npm test                   # Run all tests (vitest run)
npm run test:watch         # Run tests in watch mode
```

### ❌ WRONG — DO NOT use these:
```bash
npx vitest                        # Don't call vitest directly
vitest --run SomeFile.spec.ts     # Don't call vitest directly
npx vitest SomeFile.spec.ts       # Don't use npx
```

### Why This Matters
- **npm scripts provide a consistent interface** for running tests
- **Configuration is managed centrally** in package.json
- **Consistency across development and CI** environments

## Example Test Template
```typescript
// calculator.spec.ts
import { describe, it, expect } from "vitest";
import { calculate } from "./calculator.js";

describe("Calculator", () => {
  it.todo("should handle basic operations");
  it.todo("should validate input types");
  it.todo("should handle edge cases");
});
```
