# Amazon Vine Analysis

## Resources

Data Source: [Amazon_Reviews_pds](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt)

Software: Google Colab Notebook, PostgreSQL 11.11, pgAdmin 4 4.30, AWS (RDS, EC2)

## Overview of the analysis: 
The Amazon Vine analysis was performed to determine if there is bias toward favorable reviews from Vine members. We specifically looked at the US Shoes Amazon reviews dataset. 
We used PySpark to perform two technical technical analysis to better understand the data:
* ETL on Amazon Product Reviews (extract amazon dataset, transform/clean the data in a dataframe, and load into pgAdmin)
* Calculating review metrics

## Results: 

* How many Vine reviews and non-Vine reviews were there?

  ![paid reviews](https://user-images.githubusercontent.com/81447450/125978512-0972a8b2-331d-4d22-9785-d55b44db6326.png)

  ![unpaid reviews](https://user-images.githubusercontent.com/81447450/125978530-b3ee9c0c-a174-424d-bf24-ff8a4e597fbc.png)

* How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

  ![5 star paid](https://user-images.githubusercontent.com/81447450/125978563-57e6dbe6-35f7-4aab-a48c-965542decf1f.png)

  ![5 star unpaid](https://user-images.githubusercontent.com/81447450/125978575-96486d23-1bca-4ace-a6bd-8ece86c0515b.png)

* What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

  ![percentage paid](https://user-images.githubusercontent.com/81447450/125978604-6bb10767-9c1e-4c49-ace4-b73e443bec86.png)
  ![percentage unpaid](https://user-images.githubusercontent.com/81447450/125978611-bbf5f713-367c-4805-aae3-b3c46dd08429.png)


## Summary: 
The vine analysis shows that 59% of paid reviews are given 5-stars, compared to 54% of unpaid reviews that were given 5-stars. The difference is minimal and the percentages are about the same, therefore we can conclude there is not a strong bias towards 5-star reviews from paying Vine members. Additionally when we look at the number of paid vs unpaid counts, there over 1000 times more non-Vine reviews than there are Vine reviews, so non-Vine reviews will overshadow Vine reviews.

Another anaysis to further support our conclusion is to find the mean star ratings of Vine vs non-Vine reviews. We can do this by obtaining the summary statitics of the dataset using pandas.
