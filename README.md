# PlayLoop — Frontend

Mobile app to organize your games, decide what to play, and find people to play with.

## Stack

- [Expo](https://docs.expo.dev/) + [Expo Router](https://docs.expo.dev/router/introduction/)
- [React Native](https://reactnative.dev/)
- [TypeScript](https://www.typescriptlang.org/docs/)
- [pnpm](https://pnpm.io/)

## Requirements

- Node.js 26 (see `.nvmrc`)
- pnpm 12 (`npm i -g pnpm` or your system package manager)

## Getting started

```bash
pnpm install
pnpm start
```

## Commands

```bash
pnpm start                 # start the dev server
pnpm android               # open on Android
pnpm ios                   # open on iOS
pnpm lint                  # lint
pnpm format                # format with Prettier
pnpm format:check          # check formatting
pnpm exec tsc --noEmit     # typecheck
pnpm expo install <pkg>    # add dependencies (don't use npm/yarn)
```
