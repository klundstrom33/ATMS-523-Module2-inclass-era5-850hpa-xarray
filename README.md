# ERA5 850 hPa Temperature — Xarray Teaching Template

A GitHub **template** repository with a Jupyter notebook introducing xarray using a **cloud-hosted ERA5** dataset on **Google Cloud Storage** (ARCO ERA5 Zarr v3). Students will open the dataset, subset in space/time, compute basic statistics (including area-weighted means), and produce simple maps.

## Dataset
- **ARCO ERA5** hourly at 0.25° resolution (Zarr v3) on GCS  
- Store: `gs://gcp-public-data-arco-era5/ar/full_37-1h-0p25deg-chunk-1.zarr-v3`
- Variable used: `t` (temperature, Kelvin) on pressure levels → select **850 hPa** and convert to °C

## Quick start

### Conda/Mamba (recommended)
```bash
mamba env create -f environment.yml
mamba activate era5-850
jupyter lab
```

### Pip (fallback)
```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

Open `notebooks/01_era5_850hpa_intro.ipynb` and follow the prompts.

## Codespaces
This repo includes a `.devcontainer/` config for **GitHub Codespaces**. Open in Codespaces and the environment will be prepared automatically.

## Learning goals
- Open **Zarr v3** data directly from **GCS** with anonymous access
- Inspect dims/coords/attrs
- Subset with `.sel()` / `.isel()`
- Compute area-weighted region means and simple variability diagnostics
- Plot a time series and maps (month-mean, std, range)
- (Optional) Resample hourly → daily; export a small NetCDF

## Attribution
- ERA5 data © ECMWF, distributed via Google Cloud (ARCO). Please respect the dataset license/terms.
