# Setting up a Python development environment

```
wget https://repo.anaconda.com/archive/Anaconda3-2019.03-Linux-x86_64.sh
sh Anaconda3-2019.03-Linux-x86_64.sh
bash
conda create -n py36 python=3.6 anaconda
```

# Building libraries

```
./build.sh
```

# Running a simulation
```
source activate py36
```
```
python read_MLFMA_mesh_part1.py
python mesh_functions_seb.py
python setup_MLFMA_mesh.py
python read_MLFMA_mesh_part2.py
python setup_MLFMA_poles.py
python makeFFmat.py
```
```
OMP_NUM_THREADS=4 python solveFFmat.py
```

Open .pos files with `gmsh`. You will see the surface current distribution as shown:

<img src="imgs/surface1.norm_J_centroids_triangles.png" width="600px">

The near-field distributions can be computed and drawn by running the following command:

```
python computeEobs.py
```

Check image files in result/.

![](imgs/E_obs_d.png)

# Where is the configuration file?

See:
* [inputParams/simulation_parameters.py](inputParams/simulation_parameters.py)