#### Unique URLs / Redirection Behavior

        The following two rules differ in their use of a trailing slash.
        The canonical URL for the projects endpoint has a trailing slash(/projects/). 
        It’s similar to a folder in a file system. If you access the URL without a trailing slash(/projects), 
        Flask redirects you to the canonical URL with the trailing slash(/projects/).

        The canonical URL for the about endpoint does not have a trailing slash(/about). 
        It’s similar to the pathname of a file. Accessing the URL with a trailing slash(/about/) produces a 404 “Not Found” error. 
        This helps keep URLs unique for these resources, which helps search engines avoid indexing the same page twice.



        from markupsafe import escape
        from flask import Flask

        app = Flask(__name__)

        @app.route('/projects/')
        def projects():
            return 'The project page'

        @app.route('/about')
        def about():
            return 'The about page'
    
    
        (venv) C:\Users\Downloads\flproject\myproject>set FLASK_APP=url_redirection.py

        (venv) C:\Users\Downloads\flproject\myproject>python -m flask run    
        
        # with trailing slash
        localhost:5000/projects/ output : project page
        # without trailing slash
        localhost:5000/projects output: redirect to project page
        
        # without trailing slash
        http://localhost:5000/about   output : about page
        # with trailing slash
        http://localhost:5000/about/   output : 404
        
