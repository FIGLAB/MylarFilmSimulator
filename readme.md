## Mylar Simulator
C++-based simulator for Mylar film, with electrostatic energy, 
edge length energy, bending energy, boosted with openMP.


### 1. Dependency
```bash
# install homebrew if not installed
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

```bash
# Install openMP
brew install llvm
brew install libomp
brew upgrade libomp
```

```bash
# Install python dependencies (for svg preprocessing)
# use pip3 if your pip is binded to python2
pip install -r requirements.txt
```

### 2. Build

```bash
mkdir build
cd build
cmake ..
make
cd ..
```

### 3. Run
```bash
sh ./run.sh [svg_dir] [resolution] [seam_width]
```
- Replace "[svg_dir]" with directory to the svg file. 
- Replace "[resolution]" with the ideal length of triangle edge (default 2).
- Replace "[seam_width]" with the ideal seam width (default 1).

#### Example:
```bash
sh run.sh ./data/svg/rose.svg 8 0.1
```
The above script will load a rose pattern, with 8 as triangle edge length and 0.1 as the width of the seams(non-closed curve) on the rose.

The svg can be editted at real-time, the change will be automatically detected and the triangle mesh will be remeshed.

