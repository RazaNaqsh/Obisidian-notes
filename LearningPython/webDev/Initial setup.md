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


then set the file to be run
```
$env:FLASK_APP = "server.py"
```


Then to run the flask server
```
flask run --debug
```

