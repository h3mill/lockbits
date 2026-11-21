# Lockbits 0.2.2
Habits, tasks, notes, insights and themes. One codebase (Tauri 2) for macOS, Windows, iOS and Android. Data stays on your device.
The whole interface is one file: `ui/index.html`. There is no build step for it, so editing it and reloading is all you need.

## Run and install on your Mac
    npm install
    npx tauri icon app-icon.png     # only needed once, if src-tauri/icons is missing
    npm run dev                     # opens the app; edits to ui/index.html show after a reload (Cmd+R)
    npm run build                   # makes the .dmg in src-tauri/target/release/bundle/dmg/

## Updating an existing install (nothing is lost)
Your habits and notes are tied to the app ID `com.lockbits.app`, which has not changed. Build the new version and install it over the old one.

## Moving from the old project folder
Copy the `ui` folder, `package.json` and `src-tauri/tauri.conf.json` into it, then delete the old `index.html`, `src`, `vite.config.ts` and `tsconfig.json`. This keeps your Rust build cache so the first build is fast.

## Other platforms
- Windows: run `npm run build` on a Windows PC.
- iPhone/iPad: install Xcode, then `npm run tauri ios init` and `npm run tauri ios dev`.
- Android: install Android Studio, then `npm run tauri android init` and `npm run tauri android dev`.
