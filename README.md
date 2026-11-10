# ReadVault

A Chrome extension for your reading list. While you are on a page you want to read later, open the extension, pick a folder and press Add. The page is saved with its title and icon, and you find it again in the popup.

## What it does

- **Save the page you are on** into a folder you choose or create.
- **Folders** you can open, close, rename and delete, each showing its saved pages.
- **Three lists:** *All* (your folders), *Urgent* (pages you marked urgent, from every folder) and *Archive* (pages you have read).
- **Mark** a page as urgent or as read from its menu, or delete it.
- **Shows you if the current page is already saved.**
- A short built-in **FAQ** inside the popup.

Your list is stored in your browser (in IndexedDB) and is not sent anywhere. The extension makes no network requests of its own. The flip side is that the list does not sync between devices, and you cannot drag items to reorder them: they show in the order you added them.

The only permission it asks for is `tabs`, to read the title and address of the page you are on.

## Install it from source

You need Node and a Chromium-based browser (Chrome, Edge, Brave).

```
npm install
npm run build
```

Then open `chrome://extensions`, switch on **Developer mode**, choose **Load unpacked** and pick the `dist` folder.

For development, `npm run dev` starts Vite with hot reload on port 5177. Load the `dist` folder the same way. In `manifest.config.ts` there is a commented-out `host_permissions` line that hot reload may need; keep it off for a real build.

`npm run check` runs the type checks. There are no tests.

## Built with

Svelte 5, TypeScript, Vite with the CRXJS plugin, Tailwind CSS 4, shadcn-svelte (bits-ui). A Manifest V3 extension.

## Status

It works as a small, finished first version (the last feature change was in March 2025), but it is a hobby project, not a polished product. Known loose ends:

- No sync, no reordering, no import or export.
- The `package.json` name is still `website-blocker-svelte-extension`, left over from the project this one was started from.