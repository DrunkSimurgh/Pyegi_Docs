# The Script Info File (PyProject)

In the `pyproject.toml` file, aside from the used libraries' info and Python version (which are automatically added to this file when you develop your script in a virtual environment with proper installation process), you may only include the standard info for your script or you could add a Pyegi section to include more info. The info which may currently be included are as follows:

* `describer-version = "0.1.0"` (Pyegi checks this value to know what info it should expect. In the future releases we plan to include more fields for this section)
* `name` (The name of your script)
* `description` (Your script's description)
* `version` (Your script's version)
* `version-description` (An optional title that your script's version has; like v0.2.3 Legacy)
* `authors` (The names of the authors of the script included in a list. Their email may be added in front of the name like `Dave <dave@a.b>`)
* `known-feeds` (You may include other scripts' links here so that when the Pyegi feed is updating, it automatically check those links as well. However, if none of your scripts' link are added directly to the respective file in Pyegi repo, you have the limitation of adding 7 scripts from your account)
