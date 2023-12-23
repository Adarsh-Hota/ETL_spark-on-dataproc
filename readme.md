## Overview

A simple Spark project that uses Pyspark to extract data from the NYC taxi dataset, perform some transformations and store the data in GCS/BigQuery. 

<table>
  <tr>
    <td> <img src="/docs/images/etl_spark.png" title="Project Overview" width="600" height="200"/> </td>
  </tr>
 </table>

The python notebook present in the notebooks folder can be executed locally in a Jupyter notebook. After running, the data is stored in the 'result' folder. 

In the code folder, two python files run on a GCP Dataproc cluster. One of the files stores the data in Cloud Storage while the other file stores it in BigQuery.

## Setup

- ### GCP Compute Engine VM
  - **Instance configuration**
    - Machine type: e2-standard-4
    - Boot disk image: ubuntu-2004-focal-v20230918
    - Boot disk size: 30 GB
    - Boot disk type: Balanced persistent disk
  - **Environment configuration**
    - Spark: 3.5.0
    - Scala: 2.13.8
    - Jupyter Notebook: 6.5.4
    - Conda: 23.7.4
    - Python: 3.11.5
    - openjdk: 11.0.21
    - OpenJDK Runtime Environment: 11.0.21+9-post-Ubuntu-0ubuntu120.04
    - OpenJDK 64-Bit Server VM: 11.0.21+9-post-Ubuntu-0ubuntu120.04

- ### Dataproc Cluster configuration
  - Image version: 2.1.35-debian11
  - **Master node: Standard (1 master, N workers)**
    - Machine type: e2-standard-2
    - Number of GPUs: 0
    - Primary disk type: pd-standard
    - Primary disk size: 500GB
    - Local SSDs: 0
  - **Worker nodes: 2**
    - Machine type: n2-standard-4
    - Number of GPUs: 0
    - Primary disk type: pd-standard
    - Primary disk size: 500GB
    - Local SSDs: 0

## Data Source

NYC Taxi & Limousine Commission website - https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page
