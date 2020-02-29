#### Variable Rules

          You can add variable sections to a URL by marking sections with <variable_name>. 
          Your function then receives the <variable_name> as a keyword argument. 
          Optionally, you can use a converter to specify the type of the argument like <converter:variable_name>.

          string : (default) accepts any text without a slash
          int : accepts positive integers
          float : accepts positive floating point values
          path : like string but also accepts slashes
          uuid : accepts UUID strings


#### variable.py

          from markupsafe import escape
          from flask import Flask

          app = Flask(__name__)

          @app.route('/user/<username>')
          def show_user_profile(username):
              # show the user profile for that user
              return 'User %s' % escape(username)

          @app.route('/post/<int:post_id>')
          def show_post(post_id):
              # show the post with the given id, the id is an integer
              return 'Post %d' % post_id

          @app.route('/path/<path:subpath>')
          def show_subpath(subpath):
              # show the subpath after /path/
              return 'Subpath %s' % escape(subpath)

#### output 

        (venv) C:\Users\Downloads\flproject\myproject>set FLASK_APP=variable.py
        (venv) C:\Users\Downloads\flproject\myproject>python -m flask run


        http://localhost:5000/user/rajat
        output : User rajat

        http://localhost:5000/user/38
        output : User 38

        http://localhost:5000/path/documents/images
        output : Subpath documents/images
