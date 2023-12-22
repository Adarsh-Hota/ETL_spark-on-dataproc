<table>
  <tr>
    <td> <img src="/docs/images/etl_spark.png" title="Project Overview" width="600" height="200"/> </td>
  </tr>
 </table>

A simple Spark project that uses Pyspark to extract data from the NYC taxi dataset, perform some transformations and store the data in GCS/BigQuery. 

The python notebook present in the notebooks folder can be executed locally in a Jupyter notebook. After running, the data is stored in the 'result' folder. 

In the code folder, two python files run on a GCP Dataproc cluster. One of the files stores the data in Cloud Storage while the other file stores it in BigQuery.
