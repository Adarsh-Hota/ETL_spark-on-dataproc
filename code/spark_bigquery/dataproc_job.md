## Folder structure - 'de-spark-storage' bucket
```
├── de-spark-storage
│   ├── sparkSQL_bigquery_job/
|   |   ├── input
|   |   |   ├── green_taxi
|   |   |   |   ├── green_tripdata_2023-01.parquet 
|   |   |   ├── yellow_taxi
|   |   |   |   ├── yellow_tripdata_2023-01.parquet
|   |   ├── script
|   |   |   ├── use_sparkSQL_write_to_bigquery.py
```

## Dataproc job - use sparkSQL and write data to BigQuery
```
gcloud dataproc jobs submit pyspark \
    --cluster=de-spark-cluster \
    --region=asia-south1 \
    --jars=gs://spark-lib/bigquery/spark-bigquery-latest_2.12.jar \
    gs://de-spark-storage/sparkSQL_bigquery_job/script/use_sparkSQL_write_to_bigquery.py \
    -- \
        --input_green=gs://de-spark-storage/sparkSQL_bigquery_job/input/green_taxi/green_tripdata_2023-01.parquet \
        --input_yellow=gs://de-spark-storage/sparkSQL_bigquery_job/input/yellow_taxi/yellow_tripdata_2023-01.parquet \
        --output=trips_data.revenue_calculation
```
