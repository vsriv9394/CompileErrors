Make sure that you are in the conda environment and that the boost libraries are installed from

    conda install -c anaconda boost

before running `./bootstrap.sh`.

Further, edit the `BOOST_DIR` variable in the `setup.py` file such that the default points to the anaconda environment folder. As an
example, it should read,

    BOOST_DIR   = os.environ.get('BOOST_DIR', '/<path-to-anaconda-or-miniconda>/envs/<env-name-with-boost-installed-used-to-run-bootstrap.sh>')

In conda, the C++ flags from `-std=c++11` and `-ftemplate-depth=100` (notice the = sign) might not work in the `setup.py` file.
Thus use these flags externally.

    CFLAGS="-std=c++11 -ftemplate-depth=100" python setup.py build_ext --inplace    
