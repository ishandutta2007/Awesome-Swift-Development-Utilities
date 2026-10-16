# Awesome-Swift-Development-Utilities

# Top System Monitoring & CLI Tools Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Disk Usage Analysis, Storage Visualization & Terminal-Based Monitoring*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **System Monitoring & CLI Tools**. These tools help you find what's eating your disk space — scanning filesystems, visualizing directory sizes, and identifying large or duplicated files from either a graphical interface or the terminal.

**Examples** include TreeSize Professional, WinDirStat, WizTree, SpaceMonger, DaisyDisk, GrandPerspective, Disk Inventory X, HDGraph, JDiskReport, and Folder Size Pro (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, terminal-based analysis, and transparent disk usage reporting — ideal for sysadmins, developers, and anyone managing storage on servers or workstations.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[TreeSize Professional](https://www.jam-software.com/treesize/)**  
  Commercial disk space manager for Windows with treemap visualization, duplicate finder, and export reports. **Known for slow scanning speed** compared to WizTree or Everything — robust feature set but not the fastest . Paid license per user with volume discounts.

- **[WizTree](https://diskanalyzer.com/)**  
  **The fastest disk space analyzer on Windows** — reads the Master File Table (MFT) directly, scanning entire drives in seconds rather than minutes . Treemap visualization with file type breakdown. Free for personal use; **Commercial license $29.95/user** . **Windows-only** — no macOS or Linux version .

- **[SpaceMonger](https://www.spacemonger.com/)**  
  Commercial disk space analyzer for Windows with treemap visualization and duplicate file detection.

- **[DaisyDisk](https://daisydiskapp.com/)**  
  macOS disk analyzer with a distinctive radial visualization interface. Drag segments to delete. Paid license with free trial.

- **[GrandPerspective](https://grandperspectiv.sourceforge.net/)**  
  Open-source macOS disk usage visualizer using treemaps. Free but **interface feels dated** compared to modern alternatives .

- **[Disk Inventory X](https://www.derlien.com/)**  
  Classic macOS disk usage tool with treemap visualization. Open-source but **not actively maintained** — newer macOS versions may have issues .

- **[HDGraph](https://www.hdgraph.com/)**  
  Windows disk space analyzer with graphical treemap display.

- **[JDiskReport](https://www.jgoodies.com/freeware/jdiskreport/)**  
  Cross-platform Java-based disk usage analyzer. Works on Windows, macOS, and Linux but **requires Java runtime** .

- **[Folder Size Pro](https://www.mindgems.com/products/Folder-Size/Folder-Size.html)**  
  Commercial Windows tool for analyzing folder sizes and disk usage.

## Open-Source GitHub Projects

- **[ncdu](https://github.com/rofl0r/ncdu)**  
  **The standard terminal-based disk usage analyzer for Linux and Unix systems.** NCurses interface with keyboard navigation, sorting by size, and the ability to delete files directly from the interface. Fast C implementation with no dependencies. **ncdu 2.x** uses a new file format and supports **export/import of scan data** for analyzing one machine's disk on another. **The default recommendation for any SSH session or server without a GUI** .

- **[duf](https://github.com/muesli/duf)**  
  **Disk Usage/Free Utility** — a modern replacement for `df` with a friendly colorized table showing mountpoints, filesystem types, sizes, used/free space, and usage percentage . **Sorted by filesystem, mountpoint, or usage** with `--sort` flag. **Group and filter** with `--only`, `--hide`, and `--hide-fs` . Color-coded usage bars make it immediately obvious which volumes are nearly full . Cross-platform (Linux, macOS, Windows, BSD). Install via `apt`, `brew`, `scoop`, or Go. **Replaces `df -h` in every workflow** .

- **[dust](https://github.com/bootandy/dust)**  
  **A more intuitive version of `du` in Rust.** Shows directory sizes as a **tree with ASCII bar charts** — you see both the hierarchy and relative sizes at a glance . Handles **`--depth`**, **`--only-dir`**, and **`-X` to stay on one filesystem** . **Aggregates hard links correctly** with `--count-links` or ignores them by default . **Fast** — parallel scanning across CPU cores. Install via `cargo install du-dust`, `brew`, or distribution packages. **Best for "what's big and where?" in a single command** .

- **[gdu](https://github.com/dundee/gdu)**  
  **Interactive disk usage analyzer in Go** — similar interface to ncdu but faster and with **parallel scanning** . **gdu 5.x** adds **sparse file handling**, **`--top` for largest files only**, and **`--output-file` for CI integration** . Cross-platform with prebuilt binaries for Linux, macOS, and Windows. **The speed advantage over ncdu matters on large filesystems** — parallel scanning uses all CPU cores . Install via `brew`, `snap`, or direct binary .

- **[duc](https://github.com/zevv/duc)**  
  **A collection of tools for indexing, inspecting, and visualizing disk usage.** Scalable to **hundreds of millions of files** across multiple filesystems . Stores the filesystem tree in an **optimized database** for fast querying after the initial scan. **`duc ls`** for terminal listing, **`duc gui`** for X11 visualization, and **`duc ui`** for ncurses interface . **Sunburst visualization** in the GUI shows the whole filesystem in one view . **Best when you need to rescan repeatedly** — the database avoids rescanning the entire disk each time .

- **[diskonaut](https://github.com/imsnif/diskonaut)**  
  **Terminal disk space navigator** written in Rust — shows a **treemap of disk usage** in the terminal and lets you navigate directories with arrow keys . **Files and directories are proportional rectangles** — bigger files are bigger blocks . Press Enter to descend, Backspace to go up, and `d` to delete with confirmation . **Best for quickly finding large files in a terminal** with a visual treemap rather than a scrolling list .

- **[dua-cli](https://github.com/Byron/dua-cli)**  
  **Disk Usage Analyzer CLI in Rust** with both a **terminal UI mode** (`dua` interactive) and **non-interactive mode** for scripting . **Parallel traversal** for speed. **`dua i`** launches the interactive interface with directory navigation and deletion. **Aggregates hard links** and can **mark files for deletion in a queue** before committing . **Best for a modern ncdu alternative** with parallel scanning and Rust performance.

- **[dirstat-rs](https://github.com/scullionw/dirstat-rs)**  
  **Fast, cross-platform disk usage CLI in Rust** — works on Windows, Linux, and macOS . **Parallel scanning** using `rayon` . **`-t` for threshold filtering** — only show entries above a size . **`-d` for depth control** . **JSON output** for scripting and CI pipelines . **Best for cross-platform disk usage analysis** with scriptable output.

- **[godu](https://github.com/viktomas/godu)**  
  **Simple golang utility helping to discover large files and folders** — 551 GitHub stars . **Interactive terminal interface** with directory navigation and size sorting. **Fast** — Go binary with no dependencies. **Best for a minimal, fast alternative to ncdu** when you don't need the full feature set.

- **[tin-summer](https://github.com/vmchale/tin-summer)**  
  **Shell utility for finding and visualizing disk usage** — written in Haskell . **`sn` command** provides `sn f` for finding large files, `sn ar` for archiving, and `sn d` for disk usage report . **Color-coded output** with size thresholds. **Best for a functional-programming approach to disk usage** with a distinctive syntax .

- **[nat](https://github.com/willdoescode/nat)**  
  **The `nat ls` replacement with color and file icons** — 200+ GitHub stars . Shows directory listings with **Nerd Font icons**, color-coded by file type, and **human-readable file sizes** . **`nat ls -T`** adds a tree view . **Best for replacing `ls`** with something more informative and visually scannable .

### Additional Strong Open-Source Options

- **Baobab (GNOME Disk Usage Analyzer)** — Graphical disk usage analyzer for GNOME with treemap and ring chart visualizations. Part of the GNOME desktop.
- **Filelight** — KDE's disk usage visualizer with concentric ring charts. Integrated with Dolphin file manager.
- **QDirStat** — Qt-based directory statistics tool derived from KDirStat. Cross-platform with treemap visualization.
- **WinDirStat** — Open-source Windows disk usage analyzer with treemap visualization. Slower than WizTree but free and well-known.
- **duc** — Collection of tools for indexing and visualizing disk usage at scale.

**Frameworks for building custom systems**: Combine **ncdu** or **gdu** for interactive terminal exploration, **dust** for quick "what's big" queries in scripts and pipelines, **duf** for replacing `df -h` with colorized mountpoint summaries, **duc** for indexed rescanning across massive filesystems, and **diskonaut** for visual treemap navigation in the terminal — to build a complete disk usage analysis toolkit that works on servers, workstations, and CI pipelines.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Disk usage tools differ significantly in scanning speed, visualization approach, and platform support. **WizTree reads the NTFS Master File Table directly** — orders of magnitude faster than tools that traverse directories . **ncdu's database format is not interchangeable between versions** — 1.x and 2.x are incompatible . **Deleting files from disk usage tools is permanent** — always confirm the path before committing deletion, especially on system directories. **WizTree's speed advantage is Windows-only** — Linux and macOS tools rely on filesystem traversal and benefit from parallel scanning .
- Self-hosted open-source solutions require proper permissions, careful path selection when deleting, and awareness that scanning large filesystems consumes I/O and CPU.

---

**Made for system administrators, developers, and anyone trying to find what's filling their disk.**  
Let's make disk usage analysis more open, fast, and terminal-friendly.
