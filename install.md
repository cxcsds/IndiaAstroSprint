# Install the software needed for the X-ray tutorial
For the X-ray tutorial on Sunday, we will use Chandra data. 
That means that every participant needs to install the Chandra data reduction software package (called "CIAO")
before we do so. Because the package can be pretty big (several GB, see below), downloading it can take some time.
**Thus, you need to download and install CIAO before Sunday morning - we won't have enough time to wait for everyone to download it.**

CIAO runs on linux and MacOS, but not windows (Linux subsystem for windows might work, but I do't have personal experience with that and can't help.)

## General instructions
See official documentation here https://cxc.cfa.harvard.edu/ciao/download/

## The easy way (for people who don't want to read the full instructions)

The easiest way to install is through [conda](https://docs.conda.io/en/latest/miniconda.html),
the same package manager that is popular to install Python packages.
See the link above for details. 
For most of you pasting a single command into your terminal should be enough:
```
>>> conda create -n ciao-4.14 \
  -c https://cxc.cfa.harvard.edu/conda/ciao \
  -c conda-forge \
  ciao sherpa ds9 ciao-contrib caldb_main marx \
  jupyter
```
  
## If you want other packages in the same environment

just add them to the conda command, e.g. I always add astropy because it's so useful
```
>>> conda create -n ciao-4.14 \
  -c https://cxc.cfa.harvard.edu/conda/ciao \
  -c conda-forge \
  ciao sherpa ds9 ciao-contrib caldb_main marx \
  jupyter astropy
```
or install them separately after:
```
>>> activate ciao-4.14
>>> pip install astropy
```
## If you use a new Mac with M1 chip

put `CONDA_SUBDIR=osx-64` before the command, like so:
```
>>> CONDA_SUBDIR=osx-64 conda create -n ciao-4.14 \
  -c https://cxc.cfa.harvard.edu/conda/ciao \
  -c conda-forge \
  ciao sherpa ds9 ciao-contrib caldb_main marx \
  jupyter
```  

## If download volume or disk space is a concern

The full download is > 2 GB and needs several GB of space unpacked. If that's a problem (slow internet, not enough disk space), do not install the calibration data pacakge (called "caldb_main"):
```
>>> conda create -n ciao-4.14 \
  -c https://cxc.cfa.harvard.edu/conda/ciao \
  -c conda-forge \
  ciao sherpa ds9 ciao-contrib caldb_main marx \
  jupyter
```
You will need two extra steps to get just the calibration data you need later, but that's a much smaller download (< 0.5 GB).

## Any problems?

I'll talk about this on Friday evening. If you run into problems,
check https://cxc.cfa.harvard.edu/ciao/download/ or email me (hgunther@mit.edu) and cxchelp@head.cfa.harvard.edu

Yours,

Moritz
