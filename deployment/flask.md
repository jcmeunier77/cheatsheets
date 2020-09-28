# Flask Quickstart

## Basic app
Quick start a Flask app. To write in `main.py`:

```Python
from flask import Flask
app = Flask(__name__)


@app.route('/')
def home():
    return 'Hello World'

if __name__ == '__main__':
    app.run("127.0.0.1", port=5000, debug=True)
```

## Variable rules
Flask can define types and will convert any given input to these types

```Python
from markupsafe import escape

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
```

#### Converter types:
| Types |   |
|---|---|
| `string` | (default) accepts any text without a slash |
| `int` | accepts positive integers |
| `float` | accepts positive floating point values |
| `path` | like `string` but also accepts slashes |
| `uuid` | accepts [UUID](https://www.uuidgenerator.net/) strings |

#### What is markupsafe ?
*MarkupSafe escapes characters so text is safe to use in HTML and XML. Characters that have special meanings are replaced so that they display as the actual characters. This mitigates injection attacks, meaning untrusted user input can safely be displayed on a page.*
