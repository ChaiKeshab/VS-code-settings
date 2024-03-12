## Adding Tailwind IntelliSense for Object and Variable Names Ending with "Classes"

To enable Tailwind IntelliSense for objects and variables with names ending in "Classes", follow these steps:

1. Open the command palette by pressing `Ctrl + Shift + P`.
2. Select `Preferences: Open Settings (UI)` from the options.
3. In the Settings window, search for `tailwind CSS IntelliSense`.
4. Scroll down until you find `Tailwind CSS › Experimental: Class Regex`.
5. Click on `Edit in settings.json` below the option.

In the `settings.json` file, add the following configuration:

```json
"tailwindCSS.experimental.classRegex": [
    ["Classes \\=([^;]*);", "'([^']*)'"],
    ["Classes \\=([^;]*);", "\"([^\"]*)\""],
    ["Classes \\=([^;]*);", "\\`([^\\`]*)\\`"]
]
```

Tailwind IntelliSense will now recognize all of the following strings:

```javascript
const defaultClasses = `text-grey`;

const componentClasses = {
  default: 'text-grey',
  danger: `text-red`,
  warning: "text-yellow",
};
```
Note: the regex matches code blocks that start with `Classes =` and ends with `;` 
You can replace `Classes =` with your own matcher, like. "`CatLord`"