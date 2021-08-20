# Amazon_Vine_Analysis

## Overview of Analyis 
The purpose of this project was to analyze Amazon reviews written by members of the paid Amazon Vine Program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. I chose an Amazon dataset based on music. I used PySpark to perform the ETL process. I also connected to an Amazon RDS instance and loaded the data into pgAdmin. Lastly, I used PySpark to determine if there was any bias toward favorable reviews from paid Vine members. 

## Results

Step 1: I filtered the reviews to only include those with 20 or more total votes in order to pick reviews that are more likely to be helpful and to avoid having division by zero error later on. 

<img width="664" alt="Screen Shot 2021-08-20 at 11 47 52 AM" src="https://user-images.githubusercontent.com/83051034/130273516-a2163298-a121-4ae3-8a32-6913d19c3bbc.png">

Step 2: I then created a new dataframe that only included reviews where the # of helpful votes / # of total votes was >= 50%. 

<img width="661" alt="Screen Shot 2021-08-20 at 11 49 25 AM" src="https://user-images.githubusercontent.com/83051034/130273706-f62487ed-0e03-4653-a530-8d6c5cf9f125.png">

Step 3: I created a new dataframe by filtering for paid reviews.

<img width="659" alt="Screen Shot 2021-08-20 at 11 52 13 AM" src="https://user-images.githubusercontent.com/83051034/130274091-a30bc83a-16ff-4b93-abba-c184893344ed.png">

Step 4: I created a new dataframe by filtering for unpaid reviews.

<img width="662" alt="Screen Shot 2021-08-20 at 11 53 27 AM" src="https://user-images.githubusercontent.com/83051034/130274164-a73cbebd-d6f1-4813-a466-2f090b0d826a.png">

* How many Vine (paid) reviews and non-Vine (unpaid) reviews were there?

I used the filtered dataframe created in steps 3 and 4 in order to answer the following questions. There were only 7 paid reviews in my dataset, and 105979 unpaid. 

<img width="305" alt="Screen Shot 2021-08-20 at 11 54 31 AM" src="https://user-images.githubusercontent.com/83051034/130274300-add367d9-85a1-446c-976e-e289afccc631.png">

<img width="340" alt="Screen Shot 2021-08-20 at 11 54 40 AM" src="https://user-images.githubusercontent.com/83051034/130274313-eb0f1a06-019a-4821-b9c0-524f7c9b6bf2.png">

* How many Vine (paid) reviews were 5 stars? How many non-Vine (unpaid) reviews were 5 stars?

For my dataset, there were 0 Vine 5 star reviews and 67580 unpaid 5 star reviews. 

<img width="580" alt="Screen Shot 2021-08-20 at 11 56 50 AM" src="https://user-images.githubusercontent.com/83051034/130274549-d73d187e-374b-4169-9764-8ee5465903d3.png">

<img width="617" alt="Screen Shot 2021-08-20 at 11 56 57 AM" src="https://user-images.githubusercontent.com/83051034/130274556-5b690468-cc7d-4a5d-ae36-0745a14d574d.png">

* What percentage of Vine (paid) reviews were 5 stars? What percentage of non-Vine (unpaid) reviews were 5 stars?

For my dataset, the percentage of Vine reviews that were 5 stars was 0. However, the population was very small and only included 7 reviews. The percentage of non-Vine reviews that were 5 stars was 63.77%. 

<img width="409" alt="Screen Shot 2021-08-20 at 12 00 05 PM" src="https://user-images.githubusercontent.com/83051034/130274864-2bfdc229-1e6c-4a59-9b4b-deb2b6212a47.png">

<img width="460" alt="Screen Shot 2021-08-20 at 12 00 15 PM" src="https://user-images.githubusercontent.com/83051034/130274872-c4f63d05-56a5-450f-8b8c-61e9096f26b1.png">

## Summary 

For my dataset, it is difficult to determine if there is any positivity bias because there were only 7 total vine (paid) reviews, and 0 Vine 5 star reviews. However, if we choose to use this dataset regardless, then there was positivity bias towards the non-Vine (unpaid) reviews as compared to the Vine (paid) reviews. (63.77% vs 0%) 

Further analysis must incorporate a larger dataset which includes a greater number of Vine (paid) reviews. If this is not possible, including 4 star reviews should be considered. 










