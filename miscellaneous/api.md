# API

In this section some of Pyegi functions are detailed.

## create\_output\_file

`Pyegi.create_output_file()` function accepts two inputs:

* `transform_original` default value is `Transform.COMMENTED`. This input defines what happens to the original lines in the subtitle file:
  * `Transform.COMMENTED`: the original lines in the subtitle file will be Commented
  * `Transform.DELETED`: the original lines in the subtitle file will be Deleted
  * `Transform.UNCHANGED`: the original lines in the subtitle file won't be modified
* `insert_new` default value is `Location.BELOW`. This option defines where the produced lines will be placed in the subtitle file:
  * `Location.BELOW`: produced line(s) will be placed below the corresponding Original line
  * `Location.END`: produced line(s) will be placed at the end of subtitle file
  * `Location.START`: produced line(s) will be placed at the start of subtitle file

## get\_parameters

`Pyegi.get_parameters()` function returns a table similar to the `settings.json` with parameters that user has set.

## get\_project\_properties

`Pyegi.get_project_properties()` function loads the contents of the file containing the properties of the working subtitle (like video\_position, active\_row, etc) to an object.

## send\_line

`Pyegi.send_line()` function converts the subtitle line to a string with a certain formatting and appends it to a list containing the previously created strings of this sort.
