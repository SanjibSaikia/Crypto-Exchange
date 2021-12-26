# Bitcoin Monitor

This is an ETL pipeline to pull bitcoin exchange data from [CoinCap API](https://docs.coincap.io/) and load it into our data warehouse. 
The /exchanges endpoint offers an understanding into the where cryptocurrency is being exchanged and offers high-level information on those exchanges.

## Architecture

View the pipeline architecture at : assets/images/bc_arch.png

We use python to pull, transform and load data. Our warehouse is postgres. We also spin up a Metabase instance for our presentation layer.

## Setup

1. Check Coincap API for pulling Crypto Exchange Data (https://docs.coincap.io/#e1c56fd0-d57a-40dd-8a24-4b0883b58cfb) 

2. Set Up Postgres Database in local instance as per the parameters mentioned in containers/warehouse/setup-exchange.sql

3. Put Database Crednetials in src/bitcoinmonitor/utils/db.py

4. Download Metabase.jar file from https://www.metabase.com/docs/latest/operations-guide/running-the-metabase-jar-file.html

5. Launch Metabase from terminal : java -jar metabase.jar

6. Access Metabase at http://localhost:3000 and connect to Postgres Database  

7. Run exchange_data_etl.py. Data will get loaded from CoinCap API and can be visualized in Metabase.


