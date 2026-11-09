# Light dashboard

From the repository folder, install the standalone dashboard dependencies and run:

```powershell
python -m pip install -r requirements-dashboard.txt
python -m streamlit run app.py
```

The dashboard does not require compiling the C++ engine to explore existing CSV files.

Upload a quotes CSV in the sidebar, then click **Load / Reload**. An uploaded
file takes priority over the corresponding local file path. PnL CSV uploads are
optional. Uploads are read in memory and are not committed to the repository.
Download the example CSV under **CSV format help** to try the dashboard.

Quotes require a timestamp and bid/ask prices. Supported timestamp names include
`ts_ns`, `time_ns`, `timestamp_ns`, `ts_us`, `ts_ms`, `ts`, `timestamp`, and `time`.
Use ISO timestamps for names without a unit suffix. Common price names such as
`bid`/`ask` and `bid_px`/`ask_px` are detected automatically. Custom price and size
names can be entered in **Column mapping**. Sizes enable microprice calculations.

The light dashboard includes mid-price, spread and microprice cards, price and
spread charts, optional PnL/inventory charts, and optional depth heatmaps. The
time cursor and playback controls move through the loaded quotes. Quote sample
count reflects the selected resampling interval. Reload after changing mappings
or smoothing options.
