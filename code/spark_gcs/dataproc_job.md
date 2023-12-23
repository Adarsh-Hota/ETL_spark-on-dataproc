## Folder structure - de-spark-storage bucket
```
├── de-spark-storage
│   ├── sparkSQL_job/
|   |   ├── input
|   |   |   ├── green_taxi
|   |   |   |   ├── green_tripdata_2023-01.parquet 
|   |   |   ├── yellow_taxi
|   |   |   |   ├── yellow_tripdata_2023-01.parquet
|   |   ├── output
|   |   ├── script
|   |   |   ├── use_sparkSQL.py
```

## Dataproc job - use sparkSQL and store output in Cloud Storage
```
gcloud dataproc jobs submit pyspark \
    --cluster=de-spark-cluster \
    --region=asia-south1 \
    gs://de-spark-storage/sparkSQL_job/script/use_sparkSQL.py \
    -- \
        --input_green=gs://de-spark-storage/sparkSQL_job/input/green_taxi/green_tripdata_2023-01.parquet \
        --input_yellow=gs://de-spark-storage/sparkSQL_job/input/yellow_taxi/yellow_tripdata_2023-01.parquet \
        --output=gs://de-spark-storage/sparkSQL_job/output
```
