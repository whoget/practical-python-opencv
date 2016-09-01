# Practical Python and OpenCV

## OpenCV Installation with Anaconda Python

Create an environment for OpenCV:

``` bash
conda create --name opencv numpy scipy matplotlib jupyter
```

This will install required packages and their dependencies. Mahotas is not
available via the `conda` command, so we have to install it via Anaconda
Cloud:

``` bash
source activate opencv
conda install -c http://conda.anaconda.org/luispedro mahotas
```

OpenCV is available via `conda install`, but apparently that version is
compiled without GTK+ 2.x support. If you install this version you'll get
the following error when runnning the first example from Chapter 3:

```
OpenCV Error: Unspecified error (The function is not implemented. Rebuild
the library with Windows, GTK+ 2.x or Carbon support. If you are on Ubuntu
or Debian, install libgtk2.0-dev and pkg-config, then re-run cmake or
configure script) in cvShowImages file ...
```

This error will occur even if you already have both `libgtk2.0-dev` and 
`pkg-config` installed. Installing OpenCV 3 from Anaconda Cloud solved the
problem.

``` bash
conda install -c http://conda.anaconda.org/menpo opencv3
```

