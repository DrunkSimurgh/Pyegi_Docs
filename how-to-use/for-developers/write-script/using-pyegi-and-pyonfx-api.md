# Using Pyegi and PyonFX API

Currently, in order to write a python script for subtitle editing, you need to import the Pyegi library:

```python
import Pyegi
```

We currently support [PyonFX](https://github.com/CoffeeStraw/PyonFX) library which helps with subtitle editing. In order to receive the lines from Aegisub, you need to include this code:

```python
from pyonfx import *

io = Ass(Pyegi.get_input_file_path(), extended=True)
meta, styles, lines = io.get_data()
```

Notice that if you don't need full line specs (specially when you want to apply some simple function on many lines, you are better off setting `extended=False` in the parameters of your `Ass` function.

The `meta, styles, lines` are the subtitle meta info, the details of styles defined in subtitle file, and the subtitle lines received from Aegisub correspondingly. For more details on this, you may refer to [PyonFX documentation](https://pyonfx.readthedocs.io/en/latest/reference/ass%20core.html).

Also, when you want to prepare a line to be sent back to Aegisub, you need to use the following code:

```python
Pyegi.send_line(l)
```

Here, `l` is considered to be the line object based on PyonFX library.

Finally, you need to send all the prepared lines back to Aegisub with the following command:

```python
Pyegi.create_output_file()
```

Here, you may include the optional arguments `transform_``original` and `insert_new`; e.g:

```
Pyegi.create_output_file(transform_original=Transform.COMMENTED, insert_new=Location.BELOW)
```

where `transform_original` deals with the state of the original lines which the script is being applied to; `Transform.COMMENTED` is for commenting the original lines, `Transform.DELETED` is for deleting the original lines, and `Transform.UNCHANGED` is for keeping them unchanged. The `insert_new` argument, on the other hand, deals with the position of the generated lines; `Location.BELOW` is for placing the generated lines below their corresponding original lines, `Location.END` is for placing them at the end of the subtitle file, and `Location.START` is for placing them at the start of the subtitle file.

There is also a function for accessing the state of your \[automatically generated] GUI:

```
Pyegi.get_parameters()
```

This function loads the contents of the file containing the current states of the script GUI variables to an object. For example, if you have a color-picking object in your GUI, when you choose a color and go to the next window or apply the script, the color you chose will be saved in a file and the contents of this file can be accessed using the `get_parameters` function.

Finally, there's a function to access the properties of the project you have open in your Aegisub:

```
Pyegi.get_project_properties()
```

This function loads the Aegisub project properties namely `timecodes_file`, `keyframes_file`, `automation_scripts`, `export_filters`, `export_encoding`, `style_storage`, `video_zoom`, `ar_value`, `scroll_position`, `active_row`, `ar_mode`, `video_position`, `audio_file`, and `video_file` to an object.
