# API

In this section some of Pyegi functions are detailed.

## GetParameters

`Pyegi.GetParameters()` function returns a table similar to the `settings.json` with parameters that user has set.

## CreateOutputFile

`Pyegi.CreateOutputFile()` function accepts two inputs:

* `original` default value is "C". This input defines what happens to the original lines in the subtitle file:
  * 'C': the original lines in the subtitle file will be Commented
  * 'D': the original lines in the subtitle file will be Deleted
  * 'U': the original lines in the subtitle file won't be modified
* `placement` default value is "O". This option defines where the produced lines will be placed in the subtitle file:
  * 'O': produced line(s) will be placed below the corresponding Original line
  * 'E': produced line(s) will be placed at the end of subtitle file
  * 'S': produced line(s) will be placed at the start of subtitle file
