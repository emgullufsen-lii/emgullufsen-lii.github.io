# Guides

## Installing pyre2 on Apple ARM M1 (aarch64) Machine

1. Clone the fork of pyre2 from [emgullufsen-lii/pyre2](https://github.com/emgullufsen-lii/pyre2).

        git clone git@github.com:emgullufsen-lii/pyre2.git

2. Change directory (cd) into pyre2

        cd pyre2

3. Use homebrew to install dependencies (Cython among them), and determine the path to the installed cython binary

        brew install cmake ninja pybind11 Cython re2
        sudo find / -name cython
*We will use the path to cython found via 'find' below - you can double-check this is the actual cython binary by invoking it with the '--version' argument.

        <path>/cython --version

4. Edit src/CMakeLists.txt, substituting the location of your cython executable on line 5 (this is currently set to /opt/homebrew/bin/cython)

        set(CYTHON_EXECUTABLE <your path here>)

5. Run 'make install' to install

        make install
