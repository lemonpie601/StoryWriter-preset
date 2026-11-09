# Source and license

Story Writer Presets 1.0.2 is distributed under AGPL-3.0-only. See LICENSE.

It includes pure helpers from Pasta-Devs/Marinara-Engine (main) and Pasta-Devs/Marinara-Agents (staging), consulted 2026-11-09:

- https://github.com/Pasta-Devs/Marinara-Agents/tree/staging/packages/story-writer/src/engine/packages/client/src/lib/story-writer — model.ts and prompt.ts.
- https://github.com/Pasta-Devs/Marinara-Engine/blob/main/packages/shared/src/utils/macro-engine.ts
- https://github.com/Pasta-Devs/Marinara-Engine/blob/main/packages/shared/src/utils/dice-notation.ts
- https://github.com/Pasta-Devs/Marinara-Engine/blob/main/packages/shared/src/utils/preset-choices.ts
- https://github.com/Pasta-Devs/Marinara-Engine/blob/main/packages/shared/src/features/tactical-combat/rng.ts

Copyright remains with the upstream authors. This is an independent personal extension, not an official Marinara release.

Original TypeScript is included in vendor/source. Generated vendor JavaScript is produced by Node's stripTypeScriptTypes. Changes: prompt.ts gets additional exports of its pure section builders and a .js model import; dice-notation.ts's rng import is relocated within the vendor directory. The upstream logic is otherwise retained. src/core.js and src/extension.js implement this extension. build.mjs assembles a self-contained browser bundle without executing downloaded code.

The Story Writer main branch's 0.1.1 prompt builder is also included as prompt011.ts for compatibility regression testing only; it is not bundled into the runtime.

Build from source: Node 24+, `node prepare-vendor.mjs` (optional when vendor JS exists), `node build.mjs`. Tests use Node's test runner and Playwright with installed Chrome; `npm install` then `npm test` on a normal development machine. Packaging uses JSZip: `node package.mjs`. No dependencies are installed into Marinara to run the extension.
