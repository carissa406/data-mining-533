# Frequent Pattern Mining With Spark

This was an assignment completed during my coursework at the Univeristy of Illinois at Springfield. The purpose of this analysis was to use the Instacart Online Grocery Shopping Dataset 2017 to mine for frequent patterns and discover association rules. https://www.instacart.com/datasets/grocery-shopping-2017

Data Description: https://www.p8105.com/dataset_instacart.html
- order_id: order identifier
- product_id: product identifier
- add_to_cart_order: order in which each product was added to cart
- reordered: 1 if this prodcut has been ordered by this user in the past, 0 otherwise
- user_id: customer identifier
- eval_set: which evaluation set this order belongs in (Note that the data for use in this class is exclusively from the “train” eval_set)
- order_number: the order sequence number for this user (1=first, n=nth)
- order_dow: the day of the week on which the order was placed
- order_hour_of_day: the hour of the day on which the order was placed
- days_since_prior_order: days since the last order, capped at 30, NA if order_number=1
- product_name: name of the product
- aisle_id: aisle identifier
- department_id: department identifier
- aisle: the name of the aisle
- department: the name of the department

### Exploratory Data Analysis:

Insights gained:
- Sunday is the most popular day for total orders
- Thursday is the least popular day for total orders
- Highest number of orders is at 10:00am
- The deparments with the highest number of individual unique items are personal care and snacks

![B](https://github.com/carissa406/CSC533/blob/main/FrequentPatternMining/mostPopularItemInABasket.PNG)

### Model Training and Findings

The FPGrowth algorithm from Spark MLlib package was utilized to find the frequency of items that are associated with each other. 

Insights gained: 
- The most frequently purchased item is bananas
- The most frequent 2 items purchased together are a combination of organic avocados, organic strawberries, and organic bananas
- The top 5 items most frequently purchased together are organic avocados, organic strawberries, organic bananas, organic raspberries, and organic baby spinach
- The top 10 purchases based on confidence are associated with organic bananas or bananas (if a person purchases strawberries, they are most likely purchasing bananas as well).

![A](https://github.com/carissa406/CSC533/blob/main/FrequentPatternMining/AssociationRules.PNG)
