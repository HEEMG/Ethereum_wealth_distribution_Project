# Ethereum_wealth_distribution_Project


*	**Log** In to google cloud with your **Google Account** 


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/2718986a-124d-49aa-8b62-f6d9a8191043)


*	Go to **Console**. 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/187b239b-9146-4b54-934a-a9b40e4d8f8a)



*	Open **Navigation Menu** > **BigQuery**. 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/e8c1a685-167d-4cbf-b558-8d6bbb5155f0)



![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/5539b360-8f84-4fac-a214-30bb5bacb767)



*	The Welcome to BigQuery in the Cloud Console dailog box opens and click DONE. 
![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/5a992e99-06cc-48d0-a938-576d3e1ea7b3)



*	Click **+ ADD DATA** > **Explore public datasets** .

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/f3a8d489-685b-4918-851d-1aefe52c2df1)



*	In **Search for solutions**, type ethereum and press **enter**. 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/b61d2704-650f-4fa6-a83d-744fccf267ba)



* Click **Ethereum Classic Cryptocurrency Dataset**.
![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/2346731e-c5ae-4c32-99d3-5c878289b388)



* Click **VIEW DATASET**.

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/9113a548-dc2f-4331-9c6d-2c7f05cde83f)



A new tab will open with BigQuery, and you should be on the  bigquery-publicdata.crypto_ethereum_classic dataset. 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/6be9e227-d4a6-4bcb-aa8e-fd56f82a449c)



* Click **+ Compose new query**. 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/e7fcebb3-e8be-42dd-a891-59bfed64d529)


Copy and paste this query into the query window and then press Run. 

     #standardSQL
     select * from `bigquery-public-data.crypto_ethereum.balances` order by eth_balance desc limit 100000 
     
 ![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/0d07f72e-2f4c-47de-93da-a02d0ee2d6e6)


* Click **SAVE RESULTS**. 

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/5adcb6a8-8e96-47f0-a49a-ee1eb3710834)



* Click CSV (local file) for download. 
 
 
![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/cf9a0473-5e43-474f-a53b-3842fc9a2289)



For unlimited query result,
# bigquery-public-data.crypto_ethereum.balances

    #standardSQL
    select *
    from `bigquery-public-data.crypto_ethereum.balances`
    order by eth_balance desc
    
![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/9a4cc3cb-1c1c-403c-aa21-626859b39eba)



# bigquery-public-data.crypto_ethereum_classic.balances

    #standardSQL
    select *
    from `bigquery-public-data.crypto_ethereum_classic.balances`
    order by eth_balance desc
    
    ![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/94f4ab14-9388-4841-9cca-59dc9d5684fa)



In order to prevent overlapping **bigquery-public-data.crypto_ethereum_classic**  and **bigquery-public-data.crypto_ethereum.balances** in single output
Run the following code 

      #standardSQL
      select address, eth_balance
      from `bigquery-public-data.crypto_ethereum.balances*`

      Union distinct

      select address, eth_balance
      from `bigquery-public-data.crypto_ethereum_classic.balances*`
      order by eth_balance desc
 
 ![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/157e9858-cd79-4883-974c-dba637495d54)


In order to overlapping, **bigquery-public-data.crypto_ethereum_classic**  and **bigquery-public-data.crypto_ethereum.balances** in single output.

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/6517316b-9ffc-4195-a449-e84d1353ac30)



* Click **balances** on crypto_ethereum bigquery-public-data
* Click **Export**
* Click Export to GCS.

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/2feb7e08-88ee-4b9b-a943-0d70f156c929)



A dialogue box will appear 
* 	Click **browse** to choose your bucket where you want to store your file.

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/f72ffe20-24bb-4b93-b32e-44d5e5016bb7)



* Create new bucket.


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/06564a02-a1ce-4696-800a-4d2a2a503ffe)



* Name your bucket and continue. Then.click **CREATE**.

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/37c6a96d-d701-4442-8fdd-69f703eb6abb)



*	Give a folder and file format you want to save on CSV or json file.
* Once completed Click Select.

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/26ed91b7-e10c-44d4-ba26-7fddfacb5df0)


Lastly, we come into initial phase.

* Click **Save**.


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/562a8fdb-531a-411d-8245-dd4ad8818210)



* Go to **Navigation** and Click **Cloud Storage**.


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/9914b800-2c8b-40a8-ac67-c7aafe9837af)



* Go to your bucket once you created and open the folder on it .
![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/4c55ff6e-b792-467e-9e9a-9bdb4fe52770)


Finally you will see your files downloaded in segmented and numerical CSV files .


![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/a1d0d2aa-56b3-4271-b512-b631b176b188)



You can download file either using Activate Cloud Shell down-arrow button on corner.

![image](https://github.com/Hem5555/Ethereum_wealth_distribution_Project/assets/121716939/ed3b8f8b-a2f1-43be-a39f-b9fd8e850008)



Ethereum Reference: 

https://crawling-sole-80f.notion.site/Reference-Ethereum-794caea6a28942f4a8a8e85bea1cb419






 
