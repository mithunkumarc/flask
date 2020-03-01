#### URL Building

        To build a URL to a specific function, use the url_for() function. 
        It accepts the name of the function as its first argument and any number of keyword arguments, 
        each corresponding to a variable part of the URL rule. 
        Unknown variable parts are appended to the URL as query parameters.


#### url_building.py
        from markupsafe import escape
        from flask import Flask, url_for

        app = Flask(__name__)

        @app.route('/')
        def index():
            return 'index'

        @app.route('/login')
        def login():
            return 'login'

        @app.route('/user/<username>')
        def profile(username):
            return '{}\'s profile'.format(escape(username))

        with app.test_request_context():
            print(url_for('index')) # index : function name
            print(url_for('login')) # login : function name
            print(url_for('login', next='/'))
            print(url_for('profile', username='John Doe'))
    
#### output :

        /
        /login
        /login?next=%2F
        /user/John%20Doe

    
