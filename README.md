# PARSEC 2.1 & 3.0 Run Scripts README

## Overview

This folder contains shell scripts used to run PARSEC 2.1 & 3.0 benchmarks inside gem5 Full-System simulations.

Each script launches a specific benchmark workload and collects simulation statistics.

---

# Files

.

Example:

```bash
./build/X86/gem5.opt configs/example/fs.py \
--script=run_bodytrack.rcS
```

Example for PARSEC3.0:

```bash
cd /home/gem5/parsec-benchmark
source env.sh
parsecmgmt -a run -p blackscholes -c gcc-hooks -i simlarge -n
sleep 5
m5 exit
```

Example for PARSEC2.1:

```bash
cd /parsec/install/bin
/sbin/m5 switchcpu
/sbin/m5 dumpstats
/sbin/m5 resetstats
./blackscholes 16 /parsec/install/inputs/blackscholes/in_16.txt /parsec/install/inputs/blackscholes/prices.txt
echo "Done :D"
/sbin/m5 exit
/sbin/m5 exit
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
