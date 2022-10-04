

# linux-install

Brief guide to installing softwares on linux distributions

<br>

### 1. Extract Files

Installation files are normally archived and need to be extracted.

**.rar files:**

*Install unrar:*
	
	sudo apt-get install unrar
or

	sudo apt install unrar

<br>

*Extract without archived path (flat) in current directory:*

	unrar e file.rar

<br>

*Extract without archived path (flat) in an arbitrary directory:*

	unrar e file.rar /home/user/Desktop
	
<br>

*Extract with full path (e.g. files have nested directories):*

	unrar x file.rar

- In order to extract all parts, extract the first part, but other parts need to be in the same directory.

<br>

**.tar.gz files:**

*Extract in current directory:*

	tar -xvzf file.tar.gz

<br>

*Extract in an arbitrary directory:*

	tar -xvzf file.tar.gz -C /home/user/Desktop
	
<br>

- -x --extract : extract files from archive
- -v --verbose: verbosely list files processed
- -z --gzip: decompress archive using gzip
- -f --file: specifies the file
- -C --directory: change to arbitarary directory

<br>

### 2. Mount .iso file

the outcome of extraction is normally a .iso file which needs to be mounted as a drive.

*Create arbitrary directory in /media*
	
	sudo mkdir /media/software

- default mountpoint is /media, however you can use other directories like /mnt or /home.

<br>

*Mount .iso file in the arbitrary directory*

	sudo mount file.iso /media/software

- current directory must be the path in which contains file.iso.

<br>

### 3. Install

run install and follow the steps according to README.txt file.

*run install*
	
	sudo /media/software/install

- opening installation window may takes several minutes.

<br>

*Add root to access runing X server*
	
	xhost +SI:localuser:root

- This appears to be an issue with MATLAB R2021b under root not being able to access the X Server.
	- https://www.mathworks.com/matlabcentral/answers/1461039-on-ubuntu-sudo-won-t-run-the-install-file
