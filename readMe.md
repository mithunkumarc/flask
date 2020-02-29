#### quick start

	# creating project
	C:\Users\Downloads\flproject>mkdir myproject
	
	C:\Users\Downloads\flproject>cd myproject

	# creating virtual environment	
	C:\Users\Downloads\flproject\myproject>py -3 -m venv venv

	C:\Users\Downloads\flproject\myproject>venv\Scripts\activate

	# installing flask
	(venv) C:\Users\Downloads\flproject\myproject>pip install Flask

	# hello world 
	C:\Users\Downloads\flproject\myproject\hello.py

				from flask import Flask
				app = Flask(__name__)

				@app.route('/')
				def hello_world():
					return 'Hello, World!'

	# executing 
	(venv) C:\Users\Downloads\flproject\myproject>export FLASK_APP=hello.py

	(venv) C:\Users\Downloads\flproject\myproject>set FLASK_APP=hello.py

	(venv) C:\Users\Downloads\flproject\myproject>python -m flask run
	 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
