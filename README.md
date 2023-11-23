# explore_submodule_import

This repo aims to explore techniques to import from submodules in Python when there are potential clashes in implementation (same class, same name, across different submodules)
Otherwise site.addsitedir or appending paths in the submodule __init__.py might suffice.

Commands to replicate:
- python -m venv venv
- source venv/bin/activate
- python -m pip install -e subapplications/subapp1
- python -m pip install -e subapplications/subapp2
- python main_application/main.py

You should see the statements being printed during the importing as such: <br>

dependency1 <br>
same same but different 1 <br>
dependency2 <br>
same same but different 2 <br>

This means that the classes SameSame were called with similar paths internally within subapp1 and subapp2 but they were imported independently