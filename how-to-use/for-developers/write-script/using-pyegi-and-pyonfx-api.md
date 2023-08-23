# Using Pyegi and PyonFX API

Currently, in order to write a python script for subtitle editing, you need to import the Pyegi library:

```python
import Pyegi
```

We currently support [PyonFX](https://github.com/CoffeeStraw/PyonFX) library which helps with subtitle editing. In order to receive the lines from Aegisub, you need to include this code:

```python
from pyonfx import *

io = Ass(Pyegi.GetInputFilePath(), extended=True)
meta, styles, lines = io.get_data()
```

Notice that if you don't need full line specs (specially when you want to apply some simple function on many lines, you are better off setting `extended=False` in the parameters of your `Ass` function.

The `meta, styles, lines` are the subtitle meta info, the details of styles defined in subtitle file, and the subtitle lines received from Aegisub correspondingly. For more details on this, you may refer to [PyonFX documentation](https://pyonfx.readthedocs.io/en/latest/reference/ass%20core.html).

Also, when you want to prepare a line to be sent back to Aegisub, you need to use the following code:

```python
Pyegi.SendLine(l)
```

Here, `l` is considered to be the line object based on PyonFX library.

Finally, you need to send all the prepared lines back to Aegisub with the following command:

```python
Pyegi.CreateOutputFile()
```

Here, you may include the optional arguments `original` and `placement`; e.g:

```
Pyegi.CreateOutputFile(original="C", placement="O")
```

where `original` deals with the state of the original lines which the script is being applied to; `"C"` is for commenting the original lines, `"D"` is for deleting the original lines, and `"U"` is for keeping them unchanged. The `placement` argument, on the other hand, deals with the position of the generated lines; `"O"` is for placing the generated lines below their corresponding original lines,  `"E"` is for placing them at the end of the subtitle file, and `"S"` is for placing them at the start of the subtitle file.
