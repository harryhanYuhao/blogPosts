# Python development and deploy environment

To avoid possible dependency conflicts, python has `virtualenv` module. 

```
python -m virtualenv .venv # set up virual environment in \.venv directory
source .venv/bin/activate # enter venv
deactive # leave venv
```

In venv you can use pip to install whatever dependency for your project without worrying it will temper with the rest of your system.

```
pip freeze > requirement.txt # store current dependency into requirement.txt
pip install -r requirment.txt # install dependencies
```
