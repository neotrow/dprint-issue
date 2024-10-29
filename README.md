# dprint vs code extension issue with multiple projects

## Issue

When opening a folder in VS code with multiple projects, the dprint extension will fail with the following error:

```
[ERROR] Problem launching dprint. '"dprint"' is not recognized as an internal or external command,
operable program or batch file.

[ERROR] Error initializing dprint. Ensure it is globally installed on the path (see https://dprint.dev/install) or specify a "dprint.path" setting to the executable.
[ERROR] Problem launching dprint. '"dprint"' is not recognized as an internal or external command,
operable program or batch file.

[ERROR] Error initializing dprint. Ensure it is globally installed on the path (see https://dprint.dev/install) or specify a "dprint.path" setting to the executable.
[ERROR] Problem launching dprint. '"dprint"' is not recognized as an internal or external command,
operable program or batch file.

[ERROR] Error initializing dprint. Ensure it is globally installed on the path (see https://dprint.dev/install) or specify a "dprint.path" setting to the executable.
[INFO] Configuration file not found.
[INFO] Extension active!
```

## To reproduce

1. Clone this repository
2. Open the folder in VS code
3. run `npm install` in both `project-a` and `project-b`
4. Open a file in `project-a` and try to format it with dprint (ctrl+shift+p -> format document with -> dprint isn't available)

## Solution

The extension should be able to find the `dprint` executable closest to the file being formatted. Especially when there is a `.dprint.jsonc` file in the project.
