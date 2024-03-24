# 4844 Data Challenge

## Background
The EIP-4844 proposal is about introducing a new type of transaction to optimize how layer 2 settles to the base layer.
Its significance mainly lies in greatly reducing the transaction cost(Gas fee) and the gas fee generated when writing from layer 2 to the base layer is a huge expenditure.
Key changes introduced by EIP-4844 include:
1.  creating space for “blobs” of data for L2 settlement instead of using call data.
2.  Introduce new type-3 transactions.
3.  Each block can have up to 6 blobs and each blob can store up to 128kb of data. Blobs are only required to be stored for around 18 days.

## **Design and Development**
We have developed a dashboard on Dune to analyze 4844-related data, the link to our Dune dashboard is [https://dune.com/4844challenge/4844-data-analysis](https://dune.com/4844challenge/4844-data-analysis).

  

Our work focused on exploring the blob-related data on the Ethereum chain. Specifically, this work will examine the following questions:

1.  What is the distribution for the blob submitters from Ethereum transactions data in the past week?
    
2.  What is the trend of different protocols adopting type-3 transactions in their protocols since the launch date(2024-3-13)?
    
3.  What has been the influence of EIP-4844 on gas fees since it was launched?
    
4.  How significant is the influence?

Questions 1 and 2 focus on the acceptance and adoption of the EIP-4844 proposal by Ethereum communities. Questions 3 and 4 analyze the impact of the proposal on gas fees, aiming to assess whether the goal of the proposal's launch has been successful.

For the first two questions, we used SQL to collect data from query_3523693 in Dune, which includes all Ethereum transactions since Block #19426589. This block marks the launch of EIP-4844. For the last two questions, we collected all Ethereum transaction data since March 10, 2024, from the 'ethereum. transactions' dataset in Dune. We included data from three days before the launch date to provide a comprehensive view of the gas fee transition.
## **Analytics**

For this section, the above-proposed questions will be discussed and analyzed.

1.  Based on the blob submitter pie chart from the dune dashboard, we can clearly see that in the last 7 days, StarkNet, Base and Arbitrum are the top 3 most active blob submitters, each representing 25.3%, 22.7% and 20.5% of the total blob transactions occurred. On the other hand, protocols like Mode, Paradex and XPFP are falling behind in the total number of type-3 transactions.
    
2.  From the blob submitter bar chart, we can conclude that since the launch date of EIP-4844, many protocols started to quickly adopt the new EIP-4844 protocols. On the first day of the launch(2024-3-13), StarNet and Zksync were the first two to widely adopt EIP-4844 and since then, other protocols have started using the EIP-4844 in their base-layer settlements and stabilizing its blob usage. The counter in the dashboard has shown that StarNet, Base and Arbitrum have almost fully adopted the type-3 transactions.
    
3.  From the total gas fee and average gas per transaction charts, we can observe a clear decreasing trend of gas fees since March 13, the launch date of EIP-4844. Despite this trend, the number of transactions per day remains relatively steady.
    
4.  By evaluating the decreasing trends, the charts show that both the total gas and average gas decreased by roughly 50% since the proposal was launched. Compared to the fluctuations in gas fees before March 13, such decreases are substantial.
## **Conclusions**
To sum up, we obtained some key insights:

1.  The EIP-4844 has drawn great interest from various L2-layer protocols, especially for StarkNet, Base and Arbitrum protocols. Up to now, the blob usage by different protocols has been stabilized since the launch date.
    
2.  The EIP-4844 proposal reduced total and average gas fees by nearly 50% while maintaining a relatively stable number of transactions per day. The implementation of EIP-4844 has led to notable and beneficial changes in the gas fee mechanism on the Ethereum network.
    
Suggestions for future development:

1.  More participation and adoption by Layer-2 protocols, as some protocols like Arbitrum, have not yet fully adopted the type-3 transactions up to now.
    
2.  The inefficient usage of blob space leads to high gas fees, which can be further reduced by employing storage more efficiently by methods like sharing the blob space.
