# Environmental Monitoring and Data Analysis

Course material for the Master's course *Environmental Monitoring and Data Analysis*
(1st semester, environmental science), Chair of Sensor-based Geoinformatics,
University of Freiburg. Lab website: <https://uni-freiburg.de/enr-geosense>

The course runs weekly on Fridays. In each block there is about two hours of teaching and
about two hours of assignment work. Everything you need for the assignments is in this repository.

## Assignments

| Block | Topic | Assignment |
| --- | --- | --- |
| 2 | Git and GitHub, your first job on bwUniCluster | [Block 2 assignment](assignments/block-2-git-github-cluster.md) |

More assignments are added here as the course goes on.

## What is in this repository

| Folder | Content |
| --- | --- |
| `assignments/` | The assignment sheets, one per block |
| `scripts/` | Small example scripts in R and Python |
| `jobs/` | Slurm job scripts for bwUniCluster |
| `docs/` | Notes and templates, for example `STORAGE_TEMPLATE.md` |
| `ssh-connection/` | Guide to connect to bwUniCluster with SSH ([read it online](https://negin-katal.github.io/datascience_env_monit/ssh-connection/)) |
| `flux4student/` | FLUXNET site explorer and the weekly data used in the course ([open it online](https://negin-katal.github.io/datascience_env_monit/flux4student/)) |

## How to use this repository

1. **Fork** it on GitHub (button at the top right). The fork is your own copy.
2. **Clone** your fork to your laptop and work there.
3. Follow the assignment sheet. Commit small, write messages that say why, and push to your fork.
4. Hand in what the assignment asks for on ILIAS.

Do not push to this repository. You work in your fork, so your changes never touch the course material.

## Reproducing the five-tower report

The report source is [`scripts/view_tower_data.ipynb`](scripts/view_tower_data.ipynb). To render it, install
[Quarto](https://quarto.org/docs/get-started/) and Python 3, then clone your fork and install the
Python packages in a virtual environment:

```bash
git clone https://github.com/Moenki21/datascience_env_monit.git
cd datascience_env_monit
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install jupyter ipykernel pandas numpy matplotlib seaborn plotly
```

The five half-hourly FLUXNET ZIP files are not included in Git. Obtain them through the FLUXNET
Shuttle or the course-provided download instructions, and place them in `data/raw/`:

- `AMF_CA-Ca2_FLUXNET_2000-2010_v1.3_r1.zip`
- `AMF_US-Bi1_FLUXNET_2016-2024_v1.3_r1.zip`
- `ICOS_FR-Hes_FLUXNET_1997-2026_v1.3_r1.zip`
- `JPF_CN-HaM_FLUXNET_2001-2014_v1.3_r1.zip`
- `TERN_AU-Dry_FLUXNET_2009-2025_v1.3_r1.zip`

With the virtual environment active and all five ZIP files in place, run this from the repository
root:

```bash
quarto render scripts/view_tower_data.ipynb
```

The rendered report is `scripts/view_tower_data.html`. On Windows PowerShell, activate the virtual
environment with `.venv\Scripts\Activate.ps1` instead of the `source` command above.

## Before you start

- Git installed, with your name and email set (`git config --global user.name`, `user.email`).
- A GitHub account.
- An approved bwUniCluster account for the cluster parts. If yours is not ready yet, the assignment has a laptop fallback.
- R with Positron, or Python with VS Code (see the Block 1 material).

## Help

Stuck for more than 10 minutes? Post the exact command and the last lines of the error on ILIAS, or raise your hand in class.
Each assignment sheet ends with a troubleshooting table.

## Licence

See [LICENSE](LICENSE). The FLUXNET data in `flux4student/` has its own licence and citation requirements, described in `flux4student/README.md`.
