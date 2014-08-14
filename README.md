FUSE4MIC
========

Modified FUSE for Xeon Phi.

Introdution
--------
Though there is an FUSE kernel module provided by MPSS, but the fusermount and
some other binarys are missing on Xeon Phi. After some trials, I realized that
the missing components can be compiled from source code of FUSE, this project
contains a configured Makefile to make it easy to compile the components.

Compilation and Usage
------

If you decided to use a SNAPSHOT, this version is available for download [here](https://github.com/sdu-hpcl/FUSE4MIC/releases/download/0.0/fuse4mic.zip), and go to the uploading step after unzipping.

* Configure


        cd FUSE4MIC
        ./mic-configure.sh

* Compling


        make

* Packaging


        mkdir /PATH-WHATEVER/fuse-mic
        make install prefix=/PATH-WHATEVER/fuse-mic
    
* Uploading
 

        cd /PATH-WHATEVER/fuse-mic
        sudo scp lib/* micX:/lib64
        sudo scp bin/* micX:/bin

* Running


        scp example/hello micX:
        ssh micX
        mkdir hello
        ./hello hello

Contact
-----

Any questions or suggestions, contact me at dxhisboy@126.com.

