[Jupyter notebooks](http://jupyter.org/) are awesome. We should use them. Here are instructions for how to install in your local home directory on the UC Davis farm cluster.

Jupyter is a program written in Python. [Anaconda](https://docs.continuum.io/anaconda/index) is a package manager for Python. It’s straightforward to install and saves a lot of time. 

Download it:

    cd
    curl -OL https://3230d63b5fc54e62148e-c95ac804525aac4b6dba79b00b39d1d3.ssl.cf1.rackcdn.com/Anaconda2-2.4.0-Linux-x86_64.sh

This will download a shell script which you can run to install Anaconda:

    bash Anaconda2-2.4.0-Linux-x86_64.sh

(Select yes when prompted on adding it to your .bashrc).

Then source and install Jupyter notebook:

    source ~/.bashrc
    conda install jupyter

Then install R kernel for Jupyter:

    conda install -c r r-essentials

Source your ~/.bashrc

    source ~/.bashrc

Start a notebook (change the port number to arbitrary 4 numbers, but remember it!):

    jupyter notebook --port 8756

This will open a port 8756. Might take a little while depending on node traffic. Please be patient. 

(Side Note: If you are logged on to another node, this will not work. Jupyter notebooks will need to access your home directory because OSError: [Errno 13] Permission denied: '/run/user/1126017'

Once it starts, you will see a screen , just type 'q' to quit out. It will give you this:

    ljcohen@farm:~$ jupyter notebook --port 8756
    [I 16:06:14.988 NotebookApp] Serving notebooks from local directory: /home/ljcohen
    [I 16:06:14.989 NotebookApp] 0 active kernels 
    [I 16:06:14.989 NotebookApp] The Jupyter Notebook is running at: http://localhost:8888/
    [I 16:06:14.990 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
    [I 16:08:09.444 NotebookApp] Creating new notebook in /msu_assemblies_finished/A_xenica
    [I 16:08:26.245 NotebookApp] Kernel started: 1ef9327c-6cf6-4d30-a4cd-f0b1a987819a
    [W 16:08:37.154 NotebookApp] Timeout waiting for kernel_info reply from 1ef9327c-6cf6-4d30-a4cd-f0b1a987819a
    [1] "Got unhandled msg_type:" "comm_open"              
    [I 16:10:18.136 NotebookApp] Saving file at /msu_assemblies_finished/A_xenica/Untitled1.ipynb
    [I 16:20:17.660 NotebookApp] Saving file at /msu_asse

On your local terminal, open another ssh connection to farm:

    ssh -L 8888:localhost:8756 ljcohen@farm.cse.ucdavis.edu


Now, you should be able to open a browser and type: 

    http://localhost:8888/tree/

This should give you a screen with your home directory on the farm cluster!

Now, you can make notebooks like this: https://github.com/ljcohen/MMETSP/blob/master/MMETSP_reverse_transrate.ipynb

Useful Links:

* https://github.com/ipython/ipython/wiki/A-gallery-of-interesting-IPython-Notebooks
* http://www.camillescott.org/dammit/installing.html
* https://github.com/dib-lab/ged-docs/wiki/IPython-on-HPCC#configuring-notebook-server
* https://www.continuum.io/blog/developer/jupyter-and-conda-r



