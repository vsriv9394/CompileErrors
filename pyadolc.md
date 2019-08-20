In conda the C++ flag of `-std=c++11` and `-ftemplate-depth=100` (notice the = sign) might not work in the setup.py file.
Thus use the following externally,

    `CFLAGS="-std=c++11 -ftemplate-depth=100" python setup.py build_ext --inplace`

Also, make sure that you are in the conda environment and that the boost libraries are installed from

    `conda install -c anaconda boost`

before running `./bootstrap.sh` and the above `setup.py` script subsequently
