#### HTTP Methods

        Web applications use different HTTP methods when accessing URLs. 
        You should familiarize yourself with the HTTP methods as you work with Flask. 
        By default, a route only answers to GET requests. 
        You can use the methods argument of the route() decorator to handle different HTTP methods
        


#### http_methods.py

        from flask import Flask, request

        app = Flask(__name__)

        @app.route('/login', methods=['GET', 'POST'])
        def login():
            if request.method == 'POST':
                return do_the_login()
            else:
                return show_the_login_form()


        def do_the_login():
          return "do the login"


        def show_the_login_form():
          return "show the login form"
          
 #### execute : use postman for post request     

        (venv) C:\Users\Downloads\flproject\myproject>set FLASK_APP=http_methods.py
        (venv) C:\Users\Downloads\flproject\myproject>python -m flask run          
