# Followed this:

https://code.visualstudio.com/docs/python/tutorial-flask

# tl;dr

## Basic Steps

### Python

First install python with Homebrew via `brew install python`.

Pip is installed automatically by Homebrew on the install of Python, it is essentially the package manager.

_more on MacOs install here: https://www.digitalocean.com/community/tutorials/how-to-install-python-3-and-set-up-a-local-programming-environment-on-macos_

### Basics

Launch a Python console with `python`, `python2`, or `python3`.
Use `python --version` to see what you have installed.

For auto-formatting a default to use is autopep8, install with `pip install -U autopep8`.

### Flask & VirtualEnv

Flask is the most basic API interface for Python and we install it with
`pip install Flask`. It has add-ons like Flask-Admin, a templating engine Jinja2, and much more.

We also want to add `virtualenv` which is more or less environment versioning with
`pip install virtualenv`.

Then run `python3 -m venv .venv` and `source .venv/bin/activate`.

In VSC, press macro (⇧⌘P) and find "Python: Select Interpreter". Find the one that is probably starred, recommended, and starts with (.venv or ./venv).

In the root of the repo make a `.vscode` folder and create `launch.json` and paste in the following

```
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Python: Flask",
      "type": "python",
      "request": "launch",
      "module": "flask",
      "env": {
        "FLASK_APP": "app.webapp"
    },
      "args": [
        "run",
        "--no-debugger"
      ],
      "jinja": true,
      "justMyCode": true
    }
  ]
}
```

You should be able to just then write `pip install -r requirements.txt` to install dependencies, go to "/app" and launch the app with `python -m flask run`, then navigate to `localhost:5000`.
