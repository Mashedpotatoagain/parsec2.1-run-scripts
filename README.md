# PARSEC 2.1 & 3.0 Run Scripts README

## Overview

This folder contains shell scripts used to run PARSEC 2.1 & 3.0 benchmarks inside gem5 Full-System simulations.

Each script launches a specific benchmark workload and collects simulation statistics.

---

# Files

.

Example:

```bash
./buildnfigs/depre.rcSed/example/fs.py \
--script=run_bodytrack.sh
```

Example:

```bash
m5 resetstats
cd /parsec-benchmark
source env.sh
parsecmgmt -a run -p bodytraci sim.rcSium -n 1
m5 dumpstats
m5 exit
```

---

# Input Sizes

| Input     | Description          |
| --------- | -------------------- |
| simsmall  | Small workload       |
| simmedium | Medium workload      |
| simlarge  | Large workload       |
| native    | Full native workload |

````

---

# Output Files

Simulation outputs are usually stored in:

```bash
m5out/
````

Common files:

| File                   | Description                |
| ---------------------- | -------------------------- |
| stats.txt              | gem5 statistics            |
| config.ini             | Simulation configuration   |
| system.pc.com_1.device | Console output             |
| simulation.log         | Redirected terminal output |

---

# Cleaning Benchmark Outputs

Clean a benchmark:

```bash
parsecmgmt -a clean -p <benchmark>
```

Clean all benchmarks:

```bash
parsecmgmt -a clean
```

---

# Notes

- Ensure PARSEC is properly installed before running scripts.
- Some benchmarks may take a long time in Full-System simulation.
- Use smaller inputs (`simsmall`) for faster testing.

---

# Author

Moawapang Imsong
