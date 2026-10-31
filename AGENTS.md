This is PlayLoop, an Expo/React Native mobile app to organize your games, decide what to play, and find people to play with. Prioritize mobile-first patterns, performance, and cross-platform compatibility. A web version is a future goal, so prefer libraries that also work on web (`pnpm web`).

## Expo has changed — do not trust your training data

Expo ships breaking changes every SDK release. APIs you remember are likely renamed, moved, or removed. Before writing any code that touches an Expo, EAS, or React Native API:

1. Read the major version of the `expo` package in `package.json`.
2. Fetch the matching versioned docs: `https://docs.expo.dev/versions/v<major>.0.0/`
3. For anything else, fetch https://docs.expo.dev/llms.txt — an index of all Expo docs with corrections to common LLM misconceptions. Follow its links to the specific page you need; never answer from memory.

## Commands

This project uses **pnpm**. Never use `npm`, `yarn`, or `bun`, and never commit a `package-lock.json`.

```bash
pnpm expo install <package>                # ALWAYS use instead of pnpm add — resolves SDK-compatible versions
pnpm expo install <package> -- --save-dev  # dev dependency
pnpm start                                 # start the dev server
pnpm lint                                  # lint (ESLint)
pnpm format                                # format (Prettier)
pnpm format:check                          # check formatting
pnpm exec tsc --noEmit                     # typecheck
pnpm dlx expo-doctor                       # diagnose dependency and config issues
pnpm expo install --fix                    # fix incompatible package versions
```

Run `pnpm lint`, `pnpm format:check`, and `pnpm exec tsc --noEmit` before declaring any task done.

## Navigation & Routing

- Use **Expo Router** for all navigation. Routes live in `src/app/` — every file there is a screen, `_layout.tsx` files define navigators. Keep non-route code (components, hooks, utils) outside `src/app/`.
- Import `Link`, `router`, and `useLocalSearchParams` from `expo-router`.
- Docs: https://docs.expo.dev/router/introduction.md

## Building with EAS

Use EAS to build, sign, and submit the app in the cloud (`eas build`, `eas submit`) and to ship over-the-air updates (`eas update`) — no local Xcode or Android Studio required. Run EAS CLI as `pnpm dlx eas-cli@latest <command>`; substitute that for bare `eas` in docs examples.
Docs: https://docs.expo.dev/eas/index.md

## Conventions

- Write code, comments, commit messages, branch names, and docs in English.
- Write PR titles, descriptions, and review comments in Spanish, following `.github/pull_request_template.md`.
- Use the Node version in `.nvmrc`.
- Commits follow [Conventional Commits](https://www.conventionalcommits.org/) and stay short: `feat:`, `fix:`, `chore:`, `docs:`, `refactor:`.
- Branch names: `feature/<name>`, `fix/<name>`, `chore/<name>`.
- Code style is enforced by Prettier (single quotes, semicolons) — don't fight it, run `pnpm format`.

## Rules

- If `ios/` and `android/` directories do not exist, they are generated (Continuous Native Generation). Never create or edit them by hand — configure native behavior in `app.json` and config plugins.
- Expo Go only includes its bundled native modules. After adding a library with native code, the app needs a development build: `pnpm expo run:ios|android` locally, or `eas build --profile development`.
- Prefer recommended Expo modules over third-party libraries, and check your available skills before adding dependencies. Docs: https://docs.expo.dev/versions/latest/index.md
