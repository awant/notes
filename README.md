# notes
Through years I collected several useful commands and make notes. I believe it can be helpful to someone also.
It is faster to check these notes to refresh memory.

### Git
Take all submodules with first repo init:
git submodule update --init --recursive
git clone --recurse-submodules path/to/git/repo

### PERL ONE LINERS
Strip trailing whitespaces from a file: perl -lpe 's/\s*$//'


### VIM
Run script in vim: (Not convenient, because we can't change code in the same tab)
There is a make command. It runs the command set in the makeprg option. Use % as a placeholder for the current file name. For example, if you are editing a python script:
:set makeprg=python\ %
After this you can simply run:
:make
If you wish, you can set the autowrite option and it will save file automatically before running the makeprg:
:set autowrite

Commands:
x - to delete current symbol
A - starting to insert chars at the end of the line
dw - remove current word (w/e/$)
0 - to start of the line
rx - replace symbol with x (R - enter into replace mode)
ce - remove word and insert into edit mode
(c) - change mode
(CTRL + G) - show file location and status
(CTRL + O) - to go back
:s/old/new/g - substitute new for old
More: https://www.reddit.com/r/vim/comments/1ztmqz/vim_best_practices/

### BASH
Show free space: df -h /data/
Make visible 6th GPU for a script: CUDA_VISIBLE_DEVICES=6 ./script.sh
Count number of occurrences in a file: grep -o 'needle' file | wc -l
Show owner of a process with pid: ps -o user= -p <pid>
Show absolute filepath of file: realpath filename
Show size of file in Mb: ls -l --block-size=M
Prettify json: python -m json.tool <filename.json> | less
Low register: tr A-Z a-z < input > output
Print into stdout and a file: ls -a | tee output.file

### VENV
virtualenv -p python3 venv
activate env: source venv/bin/activate
deactivate: deactivate

### TMUX
https://habrahabr.ru/post/126996/
https://habrahabr.ru/post/327630/
scrolling: Ctrl+b, [

Boost: Running specific test units selected by their name:
example --run_test=testA
example --run_test=testA,testB
example --run_test=s2/in/test

### ITERM
http://teohm.com/blog/working-effectively-with-iterm2/
cmd+d - splits the window horizontally (pane)
cmd+shift+D splits the window vertically (pane)
cmd+] - next pane
cmd+[ - prev pane

### WIN CMD
Build project: cmake .. -G "Visual Studio 15 2017 Win64" -DCMAKE_BUILD_TYPE=Debug
cmake -DBUILD_BOOST=ON -DBUILD_FBS=ON -DBUILD_OPENSSL=ON -DBUILD_LIBSSH2=ON ../ -G "Visual Studio 14 2015 Win64"

### PYTHON
Call unittests example: python -m unittest am_composite_policy_manager/tests/test_tppm.py

### Jupyter Notebook
Ctrl+M,L - show numbers
Connect Jupyter notebook remotely on ip: X.X.X.X
	on server: jupyter notebook --no-browser --port xxxx --ip 0.0.0.0  # change xxxx (1234 for example)
	locally: ssh -N -f -L xxxx:localhost:xxxx username@X.X.X.X  # xxxx -> 1234. should be the same

### DOCKER
Run docker image and enter into bash: docker run -it <image> /bin/bash
Detach from container: Ctrl+P; Ctrl+Q / exit
Stop container: docker stop <container_id>
Save changes in container: docker commit <container_id>
