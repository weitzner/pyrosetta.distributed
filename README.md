# PyRosetta Distributed
A notebook for generating a PSSM for a protein based on a PDB file.
This is a demo and is intended to run quickly.
Because of this, all calculations are performed with a fixed backbone.
In a real-world situation, it may be wiser to replace the fixed-backbone side-chain packing runs with a call to `FastRelax` in order to capture small backbone movements.

# Environment configuration instructions
This notebook relies on an addon to PyRosetta currently being developed by Alex Ford.
The `environment.yml` file specifies the packages that are required, including a `pip`-installable version of Alex's code.
To create the environment, `cd` to the `pyrosetta.distributed` directory and issue the following command:
```bash
conda env update -f environment.yml
```
__Note:__ if you are on the `digs` (_i.e._ you're in the Baker Lab), you will probably not have `conda` in your path by default.
Here's what you should do:
If it doesn't exist, create `~/bin` and change to it by issuing 
```bash
mkdir ~/bin && cd ~/bin
```
Then we will make a few symlinks to relevant anaconda executables by issuing
```bash
ln -s /software/miniconda3/bin/activate /software/miniconda3/bin/conda /software/miniconda3/bin/deactivate .
```
Finally, prepend `$HOME/bin` to your `$PATH` variable in your (probably) `.bashrc` file by adding the following line:
```bash
export PATH=$HOME/bin:$PATH
```

Once the environment is configured, you will have `conda: pyrosetta.distributed` as a kernel option in your jupyter server.
