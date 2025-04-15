# hpc-container-def
Some container definition files for HPC related

## Usage
1. `git clone https://github.com/ExplorerRay/hpc-container-def.git`

### OSU Micro Benchmarks
> This container uses openmpi from debian 12
2. `cd benchmark && singularity build -f osu.sif osu_benchmark.def`
3. `singularity run osu.sif <osu program>`, example:
   - `singularity run osu.sif startup/osu_hello`
   - `singularity run osu.sif one-sided/osu_get_latency`

With Slurm:
- `srun -N<node> --mpi=pmix singularity run osu.sif <osu program>`

You can run `singularity shell osu.sif` and `ls /opt/libexec/osu-micro-benchmarks/mpi` to see all available programs.
