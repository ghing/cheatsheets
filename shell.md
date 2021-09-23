# Shell

## Count files in a directory structure

Use `find` together with `wc`:

```
find $DIRECTOR_TO_SEARCH -type f | wc -l
```

Be aware that this will count all files, so you can tweak the parameters to the `find` command to only match certain filename extensions or exclude files like `.DS_Store`.

This is useful if you want to make sure a web-based upload process uploaded all the files in a directory structure.
