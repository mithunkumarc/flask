#### enable vm

          C:\Users\Downloads\flproject\myproject>py -3 -m venv venv
          C:\Users\Downloads\flproject\myproject>venv\Scripts\activate

#### running app

          (venv) C:\Users\Downloads\flproject\myproject>set FLASK_APP=serve.py
          (venv) C:\Users\Downloads\flproject\myproject>python -m flask run

#### browser cache problem

          Ultimately this is a frustrating browser cache issue, which can be solved by forcing the browser to do a "hard refresh", 
          which is going to be a browser/OS dependent keystroke, but generally this works:

          Windows: Ctrl+F5
          Mac: Cmd+Shift+R
          Linux: Ctrl+Shift+R

#### restart server if any change made in source files (see : running app)
