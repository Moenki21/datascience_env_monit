# Environmental Monitoring and Data Analysis
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

## Licence

See [LICENSE](LICENSE). The FLUXNET data in `flux4student/` has its own licence and citation requirements, described in `flux4student/README.md`.
