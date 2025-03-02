# zipignore-py

A Python utility to zip a directory while respecting `.gitignore` rules. This is useful for creating clean project snapshots without unnecessary files (caches, build artifacts, local configs, etc.).

## Features

- Reads `.gitignore` and excludes files and folders matching the patterns.
- Supports:
    - Exact file/folder ignores
    - Wildcard ignores (e.g., `*.log`)
    - Directory ignores (e.g., `build/`)
- Adds a **timestamp** to the zip filename.
- Provides clear **log output** including:
    - Number of files added
    - Number of files skipped
    - Total duration of the process
    - Start and end timestamps

## Usage

1. Place `zip_with_ignore.py` in the root of your project.
2. Run the script:

    ```bash
    python zip_with_ignore.py
    ```

3. The script will produce a zip file like:

    ```
    snapshot-20250302_161245.zip
    ```

4. Files and directories listed in `.gitignore` will be excluded from the zip.

## Example Output

```text
Starting zip process at 2025-03-02 16:12:45...
Zipping directory: .
Output file will be: snapshot-20250302_161245.zip
Loading .gitignore from .gitignore...
Loaded 12 ignore patterns.
✅ Zipping complete! Added 134 files.
⚠️ Skipped 27 files due to .gitignore rules.
✅ Snapshot saved as snapshot-20250302_161245.zip
Finished at 2025-03-02 16:12:49
⏱️ Total duration: 0:00:04
