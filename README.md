# Ethereum_wealth_distribution_Project


*	**Log** In to google cloud with your **Google Account** 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/85fc2ff3-b7fb-4a9d-86fd-8b9950ff4195)


*	Go to **Console**. 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/db18fba5-cb24-4c70-809a-0dd571c9428a)


*	Open **Navigation Menu** > **BigQuery**. 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/f4270637-af89-4c22-b7a4-18497ed970dc)


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/7e171b1c-c5a5-4234-b747-8c6de4c9a9bd)


*	The Welcome to BigQuery in the Cloud Console dailog box opens and click DONE. 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/ef944bda-7dac-4bd9-b6af-37a2da4d8831)


*	Click **+ ADD DATA** > **Explore public datasets** .

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/d379f5db-36c6-4d74-b8c7-6e319e61b3d8)


*	In **Search for solutions**, type ethereum and press **enter**. 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/bc9036f8-c0c6-41a6-9ace-3d381f70e824)


* Click **Ethereum Classic Cryptocurrency Dataset**.
![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/95aed4e8-c35c-449c-8d11-6d0a1191a806)


* Click **VIEW DATASET**.

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/e6f0650f-d7e9-4137-aa2a-263ca132c141)


A new tab will open with BigQuery, and you should be on the  bigquery-publicdata.crypto_ethereum_classic dataset. 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/ab804db3-167c-457c-b597-fc4d394782bf)


* Click **+ Compose new query**. 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/5dab751a-05d4-45f8-85e4-df218ce8b3c0)
Copy and paste this query into the query window and then press Run. 

     #standardSQL
     select * from `bigquery-public-data.crypto_ethereum.balances` order by eth_balance desc limit 100000 
     
 ![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/57933e8e-5129-4e4e-ac0b-0d530d11fc26)

* Click **SAVE RESULTS**. 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/b0a59771-257a-433f-be6d-7e9808dc5766)


* Click CSV (local file) for download. 
 
 
 ![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/6841383c-fe47-4eb7-94e2-730828db86d2)


For unlimited query result,
# bigquery-public-data.crypto_ethereum.balances

    #standardSQL
    select *
    from `bigquery-public-data.crypto_ethereum.balances`
    order by eth_balance desc

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/6efc00ad-65d7-479b-8cd1-d1cfb1dc9faf)


# bigquery-public-data.crypto_ethereum_classic.balances

    #standardSQL
    select *
    from `bigquery-public-data.crypto_ethereum_classic.balances`
    order by eth_balance desc

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/8e25ac2f-b816-4c15-980f-2a6a3cc61340)


In order to prevent overlapping **bigquery-public-data.crypto_ethereum_classic**  and **bigquery-public-data.crypto_ethereum.balances** in single output
Run the following code 

      #standardSQL
      select address, eth_balance
      from `bigquery-public-data.crypto_ethereum.balances*`

      Union distinct

      select address, eth_balance
      from `bigquery-public-data.crypto_ethereum_classic.balances*`
      order by eth_balance desc
      
![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/fa7789b3-de56-4118-9520-d401221d3997)


In order to overlapping, **bigquery-public-data.crypto_ethereum_classic**  and **bigquery-public-data.crypto_ethereum.balances** in single output.

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/7d80657a-7522-4bb9-8a0e-d7f5e494b12c)


* Click **balances** on crypto_ethereum bigquery-public-data
* Click **Export**
* Click Export to GCS.


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/150b0b0c-65a7-4d82-bd42-a96404f2a702)


A dialogue box will appear 
* 	Click **browse** to choose your bucket where you want to store your file.


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/76696deb-436e-4496-85df-4b0b2da5d96e)


* Create new bucket.


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/35a9622d-9c60-406c-97f5-667dafa29a61)


* Name your bucket and continue. Then.click **CREATE**.


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/6b55e4d9-3031-472d-8232-b84efcf6a075)


*	Give a folder and file format you want to save on CSV or json file.
* Once completed Click Select.


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/2789ed55-7d03-49a1-8c53-822b82246c93)

Lastly, we come into initial phase.

* Click **Save**.


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/336ba029-e589-400e-86ea-0a5df51e58f8)


* Go to **Navigation** and Click **Cloud Storage**.


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/7c27537c-e4ff-4f92-af3b-a59d90488637)


* Go to your bucket once you created and open the folder on it .

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/6cc11d2f-2afd-421a-9dd1-7aa8dcf13767)

Finally you will see your files downloaded in segmented and numerical CSV files .


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/c0c00008-d338-46fd-98e6-f47e6fe4453d)


You can download file either using Activate Cloud Shell down-arrow button on corner.

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/8988c2c9-62f2-41a1-9635-19b130b1266e)


Ethereum Reference: 

https://crawling-sole-80f.notion.site/Reference-Ethereum-794caea6a28942f4a8a8e85bea1cb419






 
