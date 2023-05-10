### FLPP
FLPP is a simple lua-python data structures parser for Blacmagicdesign Fusion files, such as prefs files, macros and comp files.

Check `tests` package for `tests.py` file to run some test cases specific to Fusion, such as named table values, bracketed string keys and others.
Use `python -m unittest` to run tests.

Run `parse_fusion_files.py` to convert sample Fusion comp. This scriptt will produce `Fusion_modified.comp` and intermediate `Fusion_modified.json` files. Feel free to test your comp's conversion with the script too.

File `fusion_registry_list.json` contains Fusion registry entries for correct comp parsing. This list was generated on my machine and it would be enough to parse most of the comps. However, it is recommended to rebuild this list locally, so all the tools and fuses, specific to your local machine, would be parsed correctly. To build this list, run the `fusion_registry_build.py` script from `utils` folder with your python interpreter. This script will work only with Fusion Studio version. It checks if `fusionscript` module is present in the `sys.modules`. If the script is not working for you, add the `fusionscript` scripting module path to the `PYTHONPATH` environment variable. Here's some ways to do that (using macos example):

```bash
export RESOLVE_SCRIPT_API='/Library/Application Support/Blackmagic Design/DaVinci Resolve/Developer/Scripting/'
export RESOLVE_SCRIPT_LIB='/Applications/DaVinci Resolve/DaVinci Resolve.app/Contents/Libraries/Fusion/fusionscript.so'
export PYTHONPATH="$RESOLVE_SCRIPT_API/Modules"
export PYTHONPATH="$PYTHONPATH:/Applications/Blackmagic Fusion 18/Fusion.app/Contents/MacOS/"
```