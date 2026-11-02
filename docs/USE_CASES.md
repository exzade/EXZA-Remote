# Practical EXZA Remote workflows

These examples explain what the platform is intended to help with. They are **examples, not guaranteed behavior on every platform**. Each task depends on device permissions and supported tools.

## 1. Check a connected machine

> Check my paired computer's connection status and tell me its OS. Read only; do not change anything.

**Why:** Verify that pairing, the client, and the AI authorization are functioning before using more advanced tools.

## 2. Review a development project

> List the files in the project folder I have explicitly allowed and summarize the top-level structure. Do not open secrets or modify files.

**Why:** Obtain a project overview without uploading an entire archive to a chat.

## 3. Run a controlled test

> Suggest the exact, harmless test command first. Explain what it does. Only after I review and approve it, run the test and summarize the exit status.

**Why:** Keep changes intentional and make command execution auditable.

## 4. Diagnose a local process

> Show the supported running-process summary and identify processes related to my app. No process termination or configuration changes.

**Why:** Understand the current environment before taking action.

## 5. Organize a selected folder

> List the contents of my allowed test folder. Suggest a safe organization plan. Do not move, overwrite, or delete anything until I authorize individual changes.

**Why:** AI assistance should not imply automatic file modification.

## 6. Work with desktop applications

> If this operating system supports the action, identify the application window and describe the steps. Ask before typing or triggering shortcuts.

**Why:** Desktop automation should be deliberate, platform-aware, and reviewable.

## Explore more workflows

The official [EXZA Prompt Library](https://remote.exza.de/prompts/) contains additional ready-to-adapt ideas. Check the requested action, files, and permission boundaries before using any prompt.
