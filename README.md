# 100day-code
udemy - the complete Python pro bootcamp


```sh
mkdir day + project name
cd   Navigate into the project directory.
python -m venv env	Create the virtual environment named env.
source env/bin/activate	Activate the environment (Linux).

pip freeze > requirements.txt Create a requirements.txt
pip install -r requirements.txt 	Install packages within the virtual environment.
deactivate	Deactivate the environment.
```

### Day 29
The error you're encountering is due to the fact that Tkinter is not available as a standalone package on PyPI (the Python Package Index). Instead, it is bundled with the Python installation itself.

```sh
sudo apt-get update
sudo apt-get install python3-tk
python3 -m tkinter
```

(env) @kamil-flow ➜ /workspaces/100day-code/day29_Generate_a_password (main) $ python3 -m tkinter
Traceback (most recent call last):
  File "<frozen runpy>", line 198, in _run_module_as_main
  File "<frozen runpy>", line 88, in _run_code
  File "/home/codespace/.python/current/lib/python3.12/tkinter/__main__.py", line 7, in <module>
    main()
  File "/home/codespace/.python/current/lib/python3.12/tkinter/__init__.py", line 4633, in _test
    root = Tk()
           ^^^^
  File "/home/codespace/.python/current/lib/python3.12/tkinter/__init__.py", line 2340, in __init__
    self.tk = _tkinter.create(screenName, baseName, className, interactive, wantobjects, useTk, sync, use)
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_tkinter.TclError: no display name and no $DISPLAY environment variable

The error message indicates that Tkinter is trying to create a graphical user interface (GUI) but cannot find a display server. This is common in headless environments, like some Docker containers or cloud IDEs.

```sh
sudo apt-get install xvfb
xvfb-run python3 your_script.py
```
when using Xvfb, the application doesn't open a visible window

Summary of Your Workflow
Create a new folder for each project.
Set up a virtual environment.
Install required libraries using pip.
Create a requirements.txt and use a .gitignore to exclude the virtual environment.
Commit only your source code and configuration files.