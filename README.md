# PARSEC 2.1 Run Scripts README

## Overview

This folder contains shell scripts used to run PARSEC 2.1 benchmarks inside gem5 Full-System simulations.

Each script launches a specific benchmark workload and collects simulation statistics.

---

# Files

```bash
S
run_blacksc.rcSes.
run_dedup.rcS.rcSn_facerret.r.rcSrun_fluS
r.rcSfreqmine.lus.rcS.run_swapti.rcSrun_x.sh
```

Exe.rcSable

Before .rcS, make it executa+.rcSun_bodyripts e.rcSut

--enc.rcSrk Script.rcS`bash
./run_bodytrack.sh

````

These scripts arypically passed to gem5 u` option.

Example:

```bash
./buildnfigs/depre.rcSed/example/fs.py \
--script=run_bodytrack.sh
````

---

# .rcSical Scriplow

Most scripts perform the followistatistics 2. Enter PARSEC .rcSectory 3. Load PARSEC environmmark 5. Dump statistics 6. Exit simulation

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

Example:

```bash
parsecmgmt -a run -p blackscholes -i sim.rcSium -n 1
```

---

# Output Files

Simulation outputs are usually stored in:

```bash
m5out/
```

Common files:

| File                   | Description                |
| ---------------------- | -------------------------- |
| stats.txt              | gem5 statistics            |
| config.ini             | Simulation configuration   |
| system.pc.com_1.device | Console output             |
| simulation.log         | Redirected terminal output |

---

# Saving Logs

To save simulator output:

```bash
./build/X86/gem5.opt configs/... > simulation.log 2>&1
```

---

# Cleaning Benchmark Outputs

Clean a benchmark:

```bash
parsecmgmt -a clean -p bodytrack
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

