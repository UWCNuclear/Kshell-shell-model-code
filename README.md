# Kshell-shell-model-code

Check if you have the following softwares

(1) gfortran. If you don't have it already insatalled you can install it as follows: sudo apt-get install gfortran
(2) BlAS, LAPACK library. If you don't have it already insatalled you can install it as follows: sudo apt-get install libblas-dev liblapack-dev
(3) Python 2.4 or later. If you don't have it already insatalled you can follow the instructions in the link: https://www.how2shout.com/linux/install-python-3-9-or-3-8-on-ubuntu-22-04-lts-jammy-jellyfish/

 Installation procedure
 1) $ unzip KSHELL-master.zip
 2) $ cd KSHELL-master/src/
 3) $ edit Makefile for compiler (the default is intel Fortran, change this to gfortan)
 4) run the make command on the terminal i.e., $ make
 5) The insatllation is now complete. You can now run kshell using GUI in bin directory. $ ./kshell_ui.py 
 6) if the GUI fails to run. Check if it is able to access the interaction (.snt) files.
 7) on ubuntu do the following:  
    a) replace line 13 with:  bindir = "" #os.path.dirname( __file__ )
    b) replace "/../snt/" with actual path to snt directory for example: "/home/username/Pictures/KSHELL-master/snt/"

 Advice: instead of working in the bin directory you may choose to copy the files in the bin to new directory called say: KSHELL-master/my_work.
