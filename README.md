# ANSI_EscapeSequences
Library written in C for using ANSI escape sequences to manage viewport, change colors etc. in terminal.

## Macros:
Can be found in *ANSIMacros.h*
### Style
- DEFAULT_STYLE
- BOLD/NOBOLD
- UNDERLINE/NOUNDERLINE
- NEGATIVE/POSITIVE

### Prefix
- FOREGROUND
- BACKGROUND
- BRIGHT_FOREGROUND
- BRIGHT_BACKGROUND

### Color
- BLACK
- RED
- GREEN
- YELLOW
- BLUE
- MAGENTA
- CYAN
- WHITE
- DEFAULT_COLOR

### Shape
- DEFAULT_SHAPE
- BLOCK
- UNDERLINE
- BAR

### Delete mode
- START_TO_CURSOR
- CURSOR_TO_END
- ALL


## Functions:
Can be found in *ANSI.h*
### Setting up a terminal
- `setupConsole(columns, rows);`
- `restoreConsole();`
- `setWindowTitle("ConsoleTitle");`

### Changing style & colors
- `setColor(prefix, color);`
- `setStyle(count, {comma separated list of styles});`

### Cursor settings
- `relativeCursorPosition(columns, rows);`
- `absoluteCursorPosition(columns, rows);`[^1]
- `saveCursorPosisiton();`
- `restoreCursorPosition();`
- `blinkCursor(boolBlink);`
- `hideCursor(boolHide);`
- `shapeCursor(shape);`
[^1]: if the value is set to 0 than parameter is ignored

### Viewport settings
- `scrollUp(rows);`
- `scrollDown(rows);`
- `eraseViewport(delMode);`
- `scrollMargins(top, bottom);`
- `alternateBuffer(boolAlternate);`

### Text
- `insertCharacter(count);`
- `deleteCharacter(count);`
- `insertLine(count);`
- `deleteLine(count);`
- `eraseLine(delMode);`
