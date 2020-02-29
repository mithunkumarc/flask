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
