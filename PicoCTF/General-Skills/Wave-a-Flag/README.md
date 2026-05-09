# Wave a Flag

Goal: Use Linux command-line techniques to retrieve the hidden flag from the provided executable.

Category: General Skills  
Difficulty: Easy

## What I noticed

- The challenge description mentioned “help flags.”
- A file named `warm` was provided.
- Using `cat` on the file produced mostly unreadable characters with some English text mixed in.
- The text mentioned `-h` which seemed like a clue.

## What I tried

- Downloaded the file and navigated to the challenge folder.
- Used: `ls` to confirm the file existed.
- Tried: `cat warm` to inspect the file contents.
- Tried: `-h` which failed.
- Tried: `warm -h` which also failed.
- Tried: `./warm -h` after learning that executables in the current directory are run using `./`.

## What failed

- Running: `-h` returned: “command not found” because `-h` is not a standalone command.
- Running: `warm -h` returned: “command not found” because the terminal did not automatically search the current directory.
- Running: `./warm -h` returned: “permission denied” because the file was not executable.
- After adding execute permissions, running the program on macOS returned: “exec format error” because the binary was compiled for Linux and not compatible with my Mac environment.

## What worked

- Used: `chmod +x warm` to add execute permissions.
- Switched to GitHub Codespaces/Linux environment.
- Uploaded the `warm` file into the Linux environment.
- Ran: `./warm -h`
- The program displayed the flag successfully.

## Commands used

- `ls`
- `cat`
- `chmod +x`
- `./`
- `cd`

## What I learned

- Binary files behave differently from normal text files.
- Help flags like `-h` are arguments passed to programs.
- `./` is used to run executables from the current directory.
- Linux permissions control whether a file can execute.
- `chmod +x` adds execute permissions.
- Architecture and operating system compatibility matter when running binaries.
- GitHub Codespaces can provide a Linux environment for running Linux executables.