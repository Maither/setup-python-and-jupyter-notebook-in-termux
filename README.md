# setup-python-and-jupyter-notebook-in-termux
```
pkg update
pkg install python3
mkdir 220815myNewProject
python3 -m venv 220815myNewProject
cd 220815myNewProject
source bin/activate
pip install jupyterlab
```
solve libxml issue :
https://www.reddit.com/r/termux/comments/c4ot4q/cant_find_solution_to_this_problem/

```
pkg install libxslt
pip install notebook
jupyter notebook
```
Copy paste the link from the console in a navigator
