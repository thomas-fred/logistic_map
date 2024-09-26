## Using the cluster -- logistic function

Use the logistic function as an example for using the cluster.

env.yml: Specifies conda environment to run in.
    To create environment with micromamba:
    $ micromamba create -f env.yml -y
    To run python scripts in this environment, first run:
    $ micromamba activate logistic
create_params.py: Creates parameter set to run subsequent scripts with.
    Run first to create params.txt
    $ python create_params.py
array_job.sh: Runs plotting jobs in parallel.
    Log in to cluster head node and submit with sbatch:
    $ sbatch array_job.sh
    This will run logistic_map_zoom.py on each one of the parameter sets
logistic_map_zoom.py: Plots a frame using parameters from params.txt lookup.
    Receives these as command line arguments, e.g. to run 3rd set of params, run
    $ python logistic_map_zoom.py 2

For background only:
logistic_map.py: Plot logistic function over some r-space. Standalone.
notebook.ipynb: Playing with the underlying functions. Requires notebook server.
