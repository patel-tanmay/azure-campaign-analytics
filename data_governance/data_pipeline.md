# Data Pipeline (Azure + Databricks)


1. **Ingest:**
- Read parquet from Azure Data Lake: `abfss://curated@{storage}.dfs.core.windows.net/criteo-1m-features`
2. **Clean & Engineer:**
- Renamed columns
- Added uplift label using treatment + conversion
3. **Split:**
- Stratified split using uplift_label (train/test)
4. **Store:**
- Saved clean train/test sets into Databricks DBFS tables
