---
title: "Install/Manage Anaconda on My Macbook"
excerpt: "This page is for managing anaconda on my Macbook Pro"

categories:
  - Dev
tags:
  - Dev
last_modified_at: 2021-04-10T16:00:00-05:00
---

This page is for recording/managing installation process of Anaconda on my MacBook Pro. 



## Installing Anaconda on Macbook



### 1. Checking Pre-installed Anaconda 

- I have no idea whether I installed Anaconda on my Macbook. This can be checked by

```
$ conda --version
-bash: conda: command not found
```



### 2. Installing Anaconda on macOS

- Maybe, the easiest way is downloading **.pkg** file on the [Anaconda download page](https://www.anaconda.com/products/individual) (Python 3.8 version) and installing it.

- If you can find **Anaconda Navigator** on your LaunchPad, then the installation is successful.
- Open a new terminal, then the terminal may shows **(base)**
- Try

```
(base)... $ conda list

# packages in environment at /Users/yodacat/opt/anaconda3:
#
# Name                    Version                   Build  Channel
_ipyw_jlab_nb_ext_conf    0.1.0                    py38_0  
alabaster                 0.7.12                     py_0  
anaconda                  2020.11                  py38_0  
anaconda-client           1.7.2                    py38_0  
anaconda-navigator        1.10.0                   py38_0  
                                              ...
```





## Managing Anaconda On My MacBook Pro



### 1. Create a Virtual Environment

- Create an virtual environment `venv_0` with Python version = 3.8.5

```
(base)$ conda create -n venv_0 pip python=3.8.5

Collecting package metadata (current_repodata.json): done
Solving environment: done


==> WARNING: A newer version of conda exists. <==
  current version: 4.9.2
  latest version: 4.10.0
...
Verifying transaction: done
Executing transaction: done
#
# To activate this environment, use
#
#     $ conda activate venv_0
#
# To deactivate an active environment, use
#
#     $ conda deactivate
```

- venv_0 can be activated

```
(base)$ conda activate venv_0 
```



### 2. Installing Python Module within the Virtual Environment (<u>venv_0</u>)

- Within the virtual environment, install other Python modules

**PyQT5**

`conda install -c anaconda pyqt`



**Matplotlib**

`conda install -c conda-forge matplotlib`



**Jupyter Notebook**

`conda install -c conda-forge jupyterlab`



**Pandas**

`conda install -c anaconda pandas`



**Scipy**

`conda install -c anaconda scipy`



**Gpxpy**

`conda install -c conda-forge gpxpy`



**utm**

`conda install -c conda-forge utm`



**gmplot**

`conda install -c mlgill gmplot`

or `pip install gmplot` on the terminal after activating a virtual env.



**basemap**

`conda install -c anaconda basemap`



**jsonlines**

`conda install -c conda-forge jsonlines`



**pynmea2**

`conda install -c conda-forge pynmea2`



**pyserial**

`conda install -c anaconda pyserial`



**pytest**

`conda install -c anaconda pytest`



**LatLon23(1.07)** (Decimal <-> DMS)

`conda install -c conda-forge latlon23`



**Plotly**

`conda install -c plotly plotly`



**Echo the installed modules within the virtual environment**

`conda list -n venv_0` , where `venv_0` is name of the virtual environment.

```
# packages in environment at /Users/yodacat/opt/anaconda3/envs/venv_0:
#
# Name                    Version                   Build  Channel
ca-certificates           2021.1.19            hecd8cb5_1  
certifi                   2020.12.5        py38hecd8cb5_0  
libcxx                    10.0.0                        1  
libffi                    3.3                  hb1e8313_2  
ncurses                   6.2                  h0a44026_1  
openssl                   1.1.1k               h9ed2024_0  
pip                       21.0.1           py38hecd8cb5_0  
python                    3.8.5                h26836e1_1  
readline                  8.1                  h9ed2024_0  
setuptools                52.0.0           py38hecd8cb5_0  
sqlite                    3.35.4               hce871da_0  
tk                        8.6.10               hb0a8c7a_0  
wheel                     0.36.2             pyhd3eb1b0_0  
xz                        5.2.5                h1de35cc_0  
zlib                      1.2.11               h1de35cc_3  
```



### 3. Run a Virtual Env on VSCODE

https://mylogcenter.tistory.com/7



## References

-  [Anaconda commands (in Korean)](https://medium.com/@5eo1ab/conda-env-%ED%84%B0%EB%AF%B8%EB%84%90-%EB%AA%85%EB%A0%B9%EC%96%B4-adc8366f8a9d)

## Future plan

-  