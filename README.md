# Waves AI Assistant

A Japanese-first, installable PWA chat interface for the Groq API, with an animated, layered wave visual language inspired by the public Libraries.dev Waves reference. This project is an independent UI implementation; it does not bundle or claim to use Libraries.dev's Pro-only Studio component.

## Run locally

```sh
pnpm install
pnpm dev
```

## Connect Groq

Each person supplies their own Groq API key in Settings. The key is sent directly by the browser to `https://api.groq.com/openai/v1/` and is never embedded in the published source or sent to this app's hosting server. By default it is kept in the current browser session. The optional “save on this device” checkbox stores it in that browser's local storage. Chat history is stored in local storage on that device. Do not use this design with a shared API key: any key shipped to a public browser app can be extracted and abused.

Create a key at [Groq Console](https://console.groq.com/keys). API use is subject to Groq account access, model availability and its current rate/usage limits.

## Features

- Responsive chat interface, sidebar history, model selector and light/dark themes.
- Fetches the models available to the configured key and sends chat completions directly to Groq.
- Installable PWA manifest and a small offline app shell; AI requests require internet access.
- Reduced-motion support.

## Design reference and limitations

The reference is [Libraries.dev — Waves](https://libraries.dev/waves). The accompanying Studio FAQ describes Studio as a Libraries Pro feature, and the named `distortion-waves` package was not available from the public npm registry during implementation. The page's visual direction inspired a custom CSS/SVG wave treatment, rather than importing proprietary Studio assets or code.

## Deployment

Static Vite build output is in `dist/`; this repository is configured for Vercel's standard Vite build (`pnpm build`, output `dist`).
