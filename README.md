# streaming-tools
Various code and utilities extending other live streaming programs for Windows and Linux.

## Advanced Scene Switcher

### - Sound Action -
Adds a new Macro action to [Advanced Scene Switcher](https://github.com/WarmUpTill/SceneSwitcher) that will play an audio file.

### Installation
**Dependency:** [Pydub](https://github.com/jiaaro/pydub)

```
pip install pydub
```


Download the Python script from this repository from the _SceneSwitcher_ directory to a location on your device.

![OBS menu bar with 'Tools' menu open and cursor hovering over it. This image edit has the Scripts menu item text with a blue underline.](/SceneSwitcher/adv-ss-soundaction-1.png "OBS Tools Menu")  
*Tools &#9656; Scripts &#9656; 'Add Scripts' + button &#9656; adv-ss-sound.py*

Click '**Scripts**' in the Tools
menu of OBS Studio's main window.  
In the window that opens, click the <img src=./assets/obs_button_add.webp alt="plus" width="28"/> button to add a script, then browse to the .py file you saved. OBS will load this file at startup.

![OBS window for the Advanced Scene Switcher plugin, with added Macro Action 'Sound' highlighted in blue by mouse cursor.](/SceneSwitcher/adv-ss-soundaction-2.png "Advanced Scene Switcher")  

Then just open Advanced Scene Switcher from the Tools menu from before. The new Macro action will show up as "Sound".

<br>

### Usage
#### File:
Specify a full path to the audio file, or use the _Browse_ button to open the file manager and locate your file of choice.

#### Type: 
**[mandatory]** This tells Pydub's _play_ command what filetype the file is. Usually this will match the file extension, so put that here. Failing to correctly provide this will generate an error.

<br>

### Using a Venv:
If you are using an externally-managed environment with Python, you may need to modify the code to include the path to your _Python_ modules.  
Add in the top section, before importing Pydub:

##### adv-ss-sound.py
```
import os
import sys

home = os.path.expanduser("~")
modules = os.path.join(home, ".venv/<my-env-here>/lib/<my-py-version>/site-packages")
if modules not in sys.path:
    sys.path.append(modules)

[...]
```

Then use `pip install pydub`. You can create a [venv](https://docs.python.org/3/library/venv.html) with `python -m venv /path/to/new/virtual/environment`.