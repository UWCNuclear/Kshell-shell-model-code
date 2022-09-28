#  Shell-model-code: Kshell

Check if you have the following softwares

(1) gfortran. If you don't have it already insatalled you can install it as follows: sudo apt-get install gfortran
(2) BlAS, LAPACK library. If you don't have it already insatalled you can install it as follows: sudo apt-get install libblas-dev liblapack-dev
(3) Python 2.4 or later. If you don't have it already insatalled you can follow the instructions in the link: https://www.how2shout.com/linux/install-python-3-9-or-3-8-on-ubuntu-22-04-lts-jammy-jellyfish/

 Installing Kshell on ubuntu and running it with user interface
 1) $ unzip KSHELL-master.zip
 2) $ cd KSHELL-master/src/
 3) $ edit Makefile for compiler (the default is intel Fortran, change this to gfortan)
 4) run the make command on the terminal i.e., $ make
 5) The insatllation is now complete. You can now run kshell using GUI in bin directory. $ ./kshell_ui.py 
 
 6) If the GUI fails to run. Check if it is able to access the interaction (.snt) files.
 7) on ubuntu do the following:  
    a) replace line 13 with:  bindir = "" #os.path.dirname( __file__ )
    b) replace "/../snt/" with actual path to snt directory for example: "/home/username/Pictures/KSHELL-master/snt/"

 Advice: instead of working in the bin directory you may choose to copy the files in the bin to new directory called say: KSHELL-master/my_work.
 
 Once you are in my_work directory: run the script for user interface $ ./kshell_ui.py
 
 You will get the following:
 
 -----------------------------
KSHELL user interface to generate job script.\
-----------------------------
MPI parallel?\
Y/N (default:\
No) :\
n\
y for MPI parallel
... generate shell script for a single node.
model space and interaction file name (.snt)
(e.g.
w or w.snt, TAB key to complete) :
w.snt

After choosing the interaction of choice. Press enter

*************** specify a nuclide ********************
number of valence protons and neutrons
(ex.
2, 3 <CR>) <CR> to quit :
4,4
Numbers of active protons and neutrons
name for script file (default: Mg24_w ):
J, parity, number of lowest states
(ex. 10
for 10 +parity, 10 -parity states w/o J-proj. (default)
-5
for lowest five -parity states,
0+3, 2+1
for lowest three 0+ states and one 2+ states,
1.5-, 3.5+3 for lowest one 3/2- states and three 7/2+ states) :
+10
Compute 10 low-lying positive-parity states

Press enter. 

truncation for "+" parity state in Mg24_w_p.ptn
truncation scheme ?
(0): No truncation (default)
(1): particle-hole truncation for orbit(s)
(2): hw truncation
(3): Both (1) and (2)
0 for no truncation.
: 0
generating partition file ............ done.

You will then see the input parameter. E.g

eff_charge = 1.5, 0.5,
fn_int = "w.snt"
gl = 1.0, 0.0,
gs = 3.91, -2.678,
hw_type = 2
max_lanc_vec = 200
maxiter = 300
mode_lv_hdd = 0
n_block = 0
n_restart_vec = 10

You will be asked if you want to modify any parameters.

modify parameter?
(e.g. maxiter = 300 for parameter change
<CR>
for no more modification ) :

The next step if to decide whether to compute the transition probabilities or not.

compute transition probabilities (E2/M1/E1) for
Mg24_w ? Y/N (default: No) :
y
“y” for computing transition probabilities. “n” if unnecessary.

We are done generating the bash script for Kshell to run it using the terminal do the following:

$./Mg24_w.sh

The observables: binding energies,excited states energies and transition probabilities (E2/M1/E1) will be in summary_* file.
The wavefunctions are found in density_*  file.
