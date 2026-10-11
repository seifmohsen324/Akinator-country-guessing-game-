# Country Guessing Game

A console-based C game that guesses a country by traversing a binary question tree. When the current answer is wrong, the player can provide the correct country and a distinguishing yes/no question; the updated tree is serialized to `Akinator-main/countries.txt`.

## Project files

```text
.
└── Akinator-main/
    ├── main.c
    ├── play.h
    ├── learn.h
    ├── countries.txt
    └── CMakeLists.txt
```

## Build and run

Use a C compiler with GNU/POSIX `strdup` support:

```bash
cd Akinator-main
gcc -std=gnu11 main.c -o akinator
./akinator
```

Run the executable from this directory because the game opens `countries.txt` using a relative path. The source uses a text serialization of a binary tree; avoid commas in country names and questions because commas delimit serialized values.

## Implementation notes

- `play.h` defines the tree node, file deserialization, yes/no traversal, and cleanup.
- `learn.h` inserts a question and country after an incorrect guess and writes the tree back to disk.
- Interactive text input is limited to the fixed 100-byte buffers.

This is a small educational console project, not a natural-language or probabilistic guessing system.
