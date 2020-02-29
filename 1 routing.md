#### Use the route() decorator to bind a function to a URL.

    hello.py

    from flask import Flask
    app = Flask(__name__)

    @app.route('/')
    def index():
      return 'Index page'

    @app.route('/hello')
    def hello_world():
        return 'Hello, World!'
    
(venv) C:\Users\flproject\myproject>set FLASK_APP=hello.py

(venv) C:\Users\flproject\myproject>python -m flask run    
