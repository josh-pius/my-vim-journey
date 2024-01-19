### Basic Navigation
1. **Basic Movements**:
    - `h`: Move left.
    - `j`: Move down.
    - `k`: Move up.
    - `l`: Move right.
2. **Word Movements**:
    - `w`: Move to the start of the next word.
    - `b`: Move to the start of the previous word.
    - `e`: Move to the end of the current/next word.
    - `ge`: Move to the end of the previous word.
3. **Line Movements**:
    - `0`: Move to the beginning of the line.
    - `^`: Move to the first non-blank character of the line.
    - `$`: Move to the end of the line.
    - `+`: Move to the first non-blank character of the next line.
    - `-`: Move to the first non-blank character of the previous line.
    - `g_`: Move to the last non-blank character of the line.
4. **Screen Movements**:
    - `H`: Move to the top of the screen.
    - `M`: Move to the middle of the screen.
    - `L`: Move to the bottom of the screen.
5. **Page Movements**:
    - `Ctrl-f`: Move forward one full screen.
    - `Ctrl-b`: Move back one full screen.
    - `Ctrl-d`: Move forward half a screen.
    - `Ctrl-u`: Move back half a screen.
6. **Paragraph/Section Movements**:
    - `}`: Move to the next paragraph or block of text.
    - `{`: Move to the previous paragraph or block of text.
    - `]]`: Move to the next section.
    - `[[`: Move to the previous section.
7. **Matching Brackets**:
    - `%`: Move to the matching bracket ((), [], {}).
8. **Line Number**:
    - `G`: Move to the end of the file.
    - `gg`: Move to the beginning of the file.
    - `[number]G`: Move to the specified line number.
9. **Miscellaneous**:
    - `*`: Move to the next occurrence of the current word.
    - `#`: Move to the previous occurrence of the current word.
    - `f[char]`: Move to the next occurrence of [char] on the current line.
    - `F[char]`: Move to the previous occurrence of [char] on the current line.
    - `t[char]`: Move right before the next occurrence of [char] on the current line.
    - `T[char]`: Move right before the previous occurrence of [char] on the current line.
    - `;`: Repeat the last `f`, `F`, `t`, or `T` command.
    - `,`: Repeat the last `f`, `F`, `t`, or `T` command in the opposite direction.
