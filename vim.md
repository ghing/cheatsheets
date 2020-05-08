# Vim cheatsheet

## Unwrapping text

This is useful if you copy and paste a paragraph and it breaks the text onto multiple lines but you want it to be one continuous paragraph.

```
vipJ
```

## Block comment or uncomment

To comment:

- Go to the virst line of the block
- `Ctrl V` to get into visual block mode
- Use arrow keys (or corresponding letter keys) to go down to select rows
- `Shift I` to go into insert mode
- Type comment character, e.g. `#`.
- `Esc` to add comment character to all lines.

To uncomment:

- Go to first line of commented block.
- `Ctrl V` to get into visual block mode.
- Use arrow keys (or corresponding letter keys) to go down to select rows.
- `x` to delete the comment character.

Source: [What's a quick way to comment/uncomment lines in Vim? - Stack Overflow](https://stackoverflow.com/questions/1676632/whats-a-quick-way-to-comment-uncomment-lines-in-vim)
