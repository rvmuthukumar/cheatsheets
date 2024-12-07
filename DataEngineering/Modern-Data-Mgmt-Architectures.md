### Data lakes

- central repo for all structure and unstructured data at any scale
- has layers or zones
    - first layer of data lake is to store as-is
        - DMS are used to bring data data here
        - AWS Transfer to transfer files to S3 using FTP push
        - 
    - Next layer
        - data is compressed, partitioned, and audit columns are added
    - Final layer - used for consumption



### Data lakehouse

- An arrangement that does not try to force unstructured data into the strict models of data warehouse.
- With this transformed data, open formats like Apache Parquet etc can be consumed for Feature engineering and ML


### Data Mesh


### Data Product