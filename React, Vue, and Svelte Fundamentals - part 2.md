---
type: NoteCard
createdAt: null
viewedAt: 2025-09-28T14:41:51.013Z
---

# React, Vue, and Svelte Fundamentals - part 2
## Managing an app

Each toolchain will offer ways to manage the development of an app. This includes:

*   scaffolding an app as we just did using Vite, but also
*   installing dependencies, starting a dev server,
*   customizing the build pipeline (e.g., using plugins), and
*   building an optimized bundle of the app (i.e., production build)

Often we manage apps through scripts that a package manager can run for us. Most toolchains provide a set of scripts to perform various tasks when developing an app. Also,

*   We can create our own scripts.
*   Scripts can integrate with package managers in the scripts section in the package.json.

## Todo

* [ ] Add a custom task `build:banner` and script that adds a banner to the production build


Here are some hints:

```js
// will learn about these latter
import fs from "fs";
import path from "path";
```

```js
// Define your banner
const banner = `/*!
 * My Vite App - built by [Your Name]
 * Build date: ${new Date().toISOString()}
 */n`;
```

```js
// Locate the dist/assets folder
const assetsDir = path.resolve("dist/assets");

// Read all files in assetsDir
for (const file of fs.readdirSync(assetsDir)) {
  // js file
  // file path.. path.join(assetsDir, file)
  // read.. fs.readFileSync(filePath, "utf8")
  // prepend banner
  // write.. fs.writeFileSync(filePath, newCode, "utf8");

  console.log(`Banner added to ${file}`);
}
```

