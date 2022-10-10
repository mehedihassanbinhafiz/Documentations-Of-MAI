## installing jupyter notebook on Ubuntu
1.	sudo apt update
2.	sudo apt install python3-pip
3.	pip3 –version
4.	pip3 install notebook
5.	Running Notebook
jupyter notebook
Or jupyter-notebook

## pycharm installation 
1.	Go to Ubuntu software.
2.	Search pycharm 
3.	Install community version
4.	After installation run it
## Ubuntu full screen
1.	Remove guest addition iso form storage.
2.	Open terminal form Ubuntu
3.	sudo apt update
4.	sudo apt install -y build-essential linux-headers-$(uname -r)
5.	go to virtual box 
6.	click devices 
7.	click insert guest addition cd image
8.	a cd will appear in menu click it
9.	right click speech and click open in terminal
10.	ls to see this
11.	type     ./autorun.sh   and press enter
12.	give authentication pass
13.	press retun to claose this winder -> press enter just
14.	close everything and restart the Ubuntu
15.	enter password then click maximize button. 
16.	Enjoy full screen

## creating virtualenv in ubuntu
1. sudo pip3 install virtualenv 
2. virtualenv venv_name
3. source venv_name/bin/activate

## accessign hosting folders
1. go to setting
2. click shared folders
3. click add share button
4. click dropdown box of file path
5. select others 
6. then select the host pc folder
7. check auto-mount
8. click ok
9. start the linux os
10. open terminal
11. type whoami
12. copy user name
13. type sudo adduser username vboxsf
14. restart the ubuntu

## Register and setting up virtualenv 

1. python -m ipykernel install
2. ipython kernel install --name venv_name --user

## uninstall jupyter kernel
1. jupyter-kernelspec uninstall venv_name