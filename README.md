# Market Basket Analysis using Python: Understanding Customer Purchasing Patterns

## Introduction
This repository contains Python code for performing Market Basket Analysis (MBA) using retail transactional data. The primary objective is to delve into customer purchasing behavior by identifying relationships between items frequently purchased together.

## Dataset
The dataset used for this analysis is a retail transactional dataset comprising the following columns:
- `BillNo`: Bill number for each transaction.
- `Itemname`: Name of the purchased item.
- `Quantity`: Quantity of the item purchased.
- `Date`: Date and time of the transaction.
- `Price`: Price of the item.
- `CustomerID`: ID of the customer.
- `Country`: Country where the transaction occurred.

## Data Preprocessing Steps
### Data Loading and Cleaning:
- Loaded the dataset using pandas, specifying the delimiter as ';' and handling date parsing issues.
- Removed entries with mixed-type columns and handled missing values in columns Itemname and CustomerID.
- Dropped rows with negative or zero quantity and zero-priced items.
- Removed non-product entries such as 'POSTAGE,' 'DOTCOM POSTAGE,' 'Adjust bad debt,' and 'Manual.'

### Data Transformation:
- Extracted year and month from the 'Date' column for temporal analysis.
- Converted the 'Price' column from string format to a float by replacing ',' with '.'.
- Calculated the total price for each transaction by multiplying quantity and price.

### Exploratory Data Analysis (EDA):
- Analyzed monthly total sales trends over time.
- Explored monthly sales comparisons of quantity versus total sales.
- Investigated the monthly sales of top-performing countries.

### Item Analysis:
- Examined total sales for each item.
- Identified top-selling and least-selling items.
- Determined the top 10 most purchased items based on quantity sold.

## Visualizations
- Line plots displaying monthly total sales trends.
- Bar plots comparing quantity sold versus total sales for each month.
- Bar plots illustrating monthly sales by country.
- Bar plots showcasing the total sales of different items.

## Frequent Itemset Mining

Frequent Itemset Mining involves identifying combinations of items that frequently occur together within a dataset. Consider a toy box with cars, dolls, blocks, and more. Sometimes, cars and race tracks are frequently seen together during playtime. These common combinations are termed "frequent itemsets" - groups of items that regularly appear together.
Discovering these item groups allows us to comprehend consumer preferences or usage patterns. For instance, knowing that customers often purchase chips and soda together in a store helps optimize product placement and aids in understanding customer preferences.

### Key Concepts of Itemset Mining
#### Minimum Threshold:
The minimum threshold, often called the support threshold, determines the minimum occurrence frequency required for an itemset to be considered frequent. It's set to filter out itemsets that occur less frequently than the threshold. Adjusting this threshold impacts the number and significance of discovered itemsets in the mining process.
#### Association Rules:
Association Rules are used to find relationships between itemsets. For example, the first association rule can be read as- “If a person buys milk and bread, then they will also buy butter”.
#### Antecedent:
The antecedent is the itemset that comes in the ‘If’ part of the association rule. In the first association rule, the antecedent is Milk and Bread.
#### Consequent:
The consequent is the itemset that comes in the ‘Then’ part of the association rule. In the first association rule, the consequent is Butter.
#### support:
Support in frequent itemset mining indicates the frequency or occurrence of an itemset in a dataset. It's calculated as the ratio of the number of transactions where the itemset appears to the total number of transactions. Higher support values signify that the itemset appears frequently in the dataset. It helps in identifying the most common itemsets or combinations of items in a dataset.
Support(X)= support(X)/Total_Transactions(N)
#### Confidence:
Confidence in association rules measures the likelihood that if item A is purchased, item B will also be purchased. It's calculated as the ratio of the support for both items together to the support of item A alone. High confidence implies a strong association between items.
Confidence(X→Y)= Support(X)/Support(X∪Y)
#### lift:
Represents the ratio of observed support to the expected support if the antecedent and consequent were independent. Lift = Confidence (antecedent -> consequent) / Support(antecedent)
#### leverage:
Indicates the difference between the observed frequency of antecedent and consequent appearing together and the frequency that would be expected if they were independent.
conviction:
Calculates the dependency of the consequent on the antecedent.
#### zhangs_metric:
This might represent a specific measure or metric related to association rule mining, but without further context, it's difficult to provide specific details about it.

# The two most commonly used algorithms for Frequent Itemset Mining are apriori and fp-growth.¶

## Apriori Algorithm:
Step 1: Candidate Itemset Generation: Initially identifies frequent individual items (1-itemsets) in the dataset.       
Step 2: Joining and Pruning: Generates larger candidate itemsets by joining smaller frequent itemsets and pruning infrequent ones based on a minimum support threshold.      
Step 3: Repeats: Iteratively applies the join and prune steps to generate larger itemsets until no more can be formed.    
### Advantages:
Easy to understand and implement. Guarantees to find all frequent itemsets. Works well for small or medium-sized datasets.
### Disadvantages:
Computationally expensive for large datasets due to multiple scans of the data. Generates a vast number of candidate itemsets, leading to higher memory requirements.

## FP-Growth Algorithm:
Utilizes a tree-like structure called the FP-Tree to encode the dataset efficiently.     
Step 1: FP-Tree Construction: Builds an FP-Tree by encoding transactions and their itemsets.    
Step 2: Mining Frequent Itemsets: Condenses the FP-Tree and recursively mines frequent itemsets from its structure.   

### Advantages:
Requires only two scans of the dataset, making it faster than Apriori.
Consumes less memory as it compresses the dataset into a tree structure.
Efficient for large datasets and high-dimensional data.
### Disadvantages:
More complex to understand and implement than Apriori. Can be less efficient for datasets with very low support thresholds or extremely dense datasets. Both algorithms are significant in discovering frequent itemsets, but FP-Growth tends to outperform Apriori for larger datasets due to its reduced number of scans and memory usage.

## Application Areas of Frequent Itemset Mining are
Supermarkets: Helps optimize product placement for increased sales.  
Online Shopping: Recommends products based on customers' buying patterns.   
Healthcare: Identifies frequent co-occurrences of symptoms in patients for better diagnosis.

## Results
- After applying the algorithms we have discovered notable item combinations such as (HERB MARKER MINT, HERB MARKER THYME), (HERB MARKER ROSEMARY, HERB MARKER PARSLEY), and (HERB MARKER ROSEMARY, HERB MARKER BASIL) that frequently occur together, indicating strong customer preferences for these pairs.
- Leveraged these insights to suggest potential bundling opportunities or strategic product placements.

## Usage of this repository involves 

## Data Preparation:
- Ensure the dataset is in CSV format and structured similarly.
- Replace the file path in the code with your dataset path.

## Python Environment:
- Install necessary libraries: pandas, numpy, matplotlib, seaborn,mlxtend library in Python.

## Execution:
- Run the Python code cells in a Jupyter Notebook or any Python environment.

## Conclusion
This project aimed to provide insights into customer buying behavior through Market Basket Analysis. Understanding patterns in customer purchases aids in effective marketing strategies, inventory management, and sales optimization.

## References 
1.)https://medium.com/@khusheekapoor/market-basket-analysis-association-rule-mining-dd632aa31a36    
2.)https://medium.com/@anilcogalan/fp-growth-algorithm-how-to-analyze-user-behavior-and-outrank-your-competitors-c39af08879db    
The provided articles were instrumental in expanding my understanding and practical application of the concepts related to Apriori and FP-Growth algorithms. I'm immensely grateful for the valuable insights they offered.   

## Contact Information

If you have any questions or would like to discuss this research further, please feel free to reach out to me:
Name: srujitha Devineni
Email: srujitha_devineni@srmap.edu.in
