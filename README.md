# setup-python-jupyter-notebook-in-termux
```
pkg update
pkg install python3
mkdir 220815myNProject
python3 -m venv 220815myNProject
cd 220815myNProject
source bin/activate
pip install jupyterlab
```
//solve libxml issue :
//https://www.reddit.com/r/termux/comments/c4ot4q/cant_find_solution_to_this_problem/
pkg install libxslt
//solve libzmq issue :
//https://stackoverflow.com/questions/49805480/could-not-install-pyzmq-using-apt-pip-pip3-easy-install-etc-any-command
pip install notebook
//solve numpy issue :
//https://github.com/termux/termux-packages/issues/10808
MATHLIB="m" pip install numpy

//lve pillow issue : pillow fix but matplotlib fail below
//https://stackoverflow.com/questions/62956054/how-to-install-pillow-on-termux
pip install wheel
pkg install libjpeg-turbo
LDFLAGS="-L/system/lib64/" CFLAGS="-I/data/data/com.termux/files/usr/include/" pip install Pillow

pip install matplotlib //fail

pkg install matplotlib //ok but not pip

pip install matplotlib //fail

//from :
//https://stackoverflow.com/questions/65184413/pip-install-matplotlib-does-not-work-under-termux-android

pkg in build-essential -y 
git clone https://github.com/matplotlib/matplotlib
cd matplotlib
sed 's@#enable_lto = True@enable_lto = False@g' setup.cfg.template > setup.cfg
pip install . //fail

sed 's/#enable_lto = True/enable_lto = False/g' mplsetup.cfg.template > mplsetup.cfg
pip install .
//nope fail

//
//https://github.com/termux/termux-packages/issues/8183
pkg install binutils
pip install .
//nice  M. Grimler91 save the day

jupyter notebook
//copie paste link in brother



//
//https://gist.github.com/NateScarlet/cfb27038e67ed817914c5a2186916ded
