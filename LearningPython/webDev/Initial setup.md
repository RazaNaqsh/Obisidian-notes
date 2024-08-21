- open up the flask documentation
- From there youll need to setup the venv (virtual environment) in your directory.

```
> mkdir myproject
> cd myproject
> py -3 -m venv .venv #(this second arg is the folder name where the venv will be created)
> 
```

- Activate the environment

```
 .venv\Scripts\activate
```

- Install Flask
```
pip install Flask
```

- Then create a server.py

```
from flask import Flask,render_template

app = Flask(__name__)


@app.route('/')

def hello_world():

    return render_template("index.html")

  

@app.route('/about')

def about():

    return render_template('about.html')
```
Youll have to create a template folder and place the html files there for the flask to detect it

then set the file to be run
```
$env:FLASK_APP = "server.py"
```


Then to run the flask server
```
flask run --debug
```



And for the CSS and js script file to load and run
create a static folder, move both files there
change the location inside index.html

```
    <link rel="stylesheet" href="static/style.css" />
  <script src="static/script.js"></script>
```