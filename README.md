# Amazon_Vine_Analysis

Review Of Datasets

A database was created with Amazon RDS and PgAdmin was used to create a new database to connect in Amazon RDS server.  With the help of the code from the challenge schema, created four tables in my database: customers table, products table, review id table and the vine table.  One of the review datasets was extracted and used to create a new DataFrame.

The customers table id, the products table, the review id, and the vine table DataFrames were then used to create other dataframes, namely count(customer id.  This function was done to match the schema for the customer table in pgAdmin.

Samples of the Tables:

+--------------+-----------+-------------+-----------+----+-----------------+
|     review_id|star_rating|helpful_votes|total_votes|vine|verified_purchase|
+--------------+-----------+-------------+-----------+----+-----------------+
|R3KKUSGFZWSUIY|          5|           56|         63|   Y|                N|
|R10FO5UKKVZBK2|          3|           23|         23|   Y|                N|
| RM4KSGEOR7MU1|          5|           19|         24|   Y|                N|
| RG7VRMYLEXD23|          4|           22|         26|   Y|                N|
|R11O4YSCPSNL6L|          3|           20|         26|   Y|                N|
|R286MFBAJ8NPD6|          5|           46|         51|   Y|                N|
|R1JRR530H4COA2|          5|           22|         28|   Y|                N|
| RQ5WD90PUNBU9|          5|           21|         24|   Y|                N|
|R12648VHCQWUV9|          4|           21|         28|   Y|                N|
|R3KAW29CJ8L6DQ|          5|           17|         20|   Y|                N|
+--------------+-----------+-------------+-----------+----+-----------------+
only showing top 10 rows

+--------------+-----------+-------------+-----------+----+-----------------+
|     review_id|star_rating|helpful_votes|total_votes|vine|verified_purchase|
+--------------+-----------+-------------+-----------+----+-----------------+
| R4PKAZRQJJX14|          1|           21|         34|   N|                N|
|R2CI0Y288CC7E2|          1|           21|         35|   N|                Y|
|R127WEQY2FM1T3|          1|          147|        175|   N|                Y|
|R2FJ94555FZH32|          2|           55|         60|   N|                N|
|R1U3AR67RE273L|          1|           51|         65|   N|                Y|
|R3PZOXA5X1U8KW|          4|           31|         36|   N|                N|
| R6KTC1OPIOIIG|          2|           19|         34|   N|                Y|
|R36O341WWXXKNP|          5|           28|         31|   N|                N|
|R10LZVBLQHBVJ0|          2|          151|        198|   N|                N|
|R1VR5GLGY1GE7N|          1|           49|         51|   N|                Y|
+--------------+-----------+-------------+-----------+----+-----------------+
only showing top 10 rows

+--------------+-----------+-------------+-----------+----+-----------------+
|     review_id|star_rating|helpful_votes|total_votes|vine|verified_purchase|
+--------------+-----------+-------------+-----------+----+-----------------+
| R4PKAZRQJJX14|          1|           21|         34|   N|                N|
|R2CI0Y288CC7E2|          1|           21|         35|   N|                Y|
|R127WEQY2FM1T3|          1|          147|        175|   N|                Y|
|R2FJ94555FZH32|          2|           55|         60|   N|                N|
|R1U3AR67RE273L|          1|           51|         65|   N|                Y|
|R3PZOXA5X1U8KW|          4|           31|         36|   N|                N|
| R6KTC1OPIOIIG|          2|           19|         34|   N|                Y|
|R36O341WWXXKNP|          5|           28|         31|   N|                N|
|R10LZVBLQHBVJ0|          2|          151|        198|   N|                N|
|R1VR5GLGY1GE7N|          1|           49|         51|   N|                Y|
+--------------+-----------+-------------+-----------+----+-----------------+
only showing top 10 rows

# The total number of reviews, the number of 5-star reviews, and the percentage 5-star reviews are calculated for all Vine and non-Vine reviews (15 pt)

# Determine the percentage of five-star reviews among Vine reviews
vine_number = vine_review_df.count()
vine_five_star_number = vine_review_df.filter(vine_review_df['star_rating']== 5).count()
percentage_five_star_vine = float(vine_five_star_number) / float(vine_number)
print(vine_number)
print(vine_five_star_number)
print(percentage_five_star_vine)

# Determine the percentage of five-star reviews among non-Vine reviews.
no_vine_number = no_vine_review_df.count()
no_vine_five_star_number = no_vine_review_df.filter(no_vine_review_df['star_rating']== 5).count()
percentage_five_star_no_vine = float(no_vine_five_star_number) / float(no_vine_number)
print(no_vine_number)
print(no_vine_five_star_number)
print(percentage_five_star_no_vine)

# Total amount of reviews
print(vine_number + no_vine_number)
94
48
0.5106382978723404
40471
15663
0.38701786464381904
40565

The Summary

The Amazon Vine program allows manufactureres and publisher to receive reviews for their products.I  this project, using Pyspark helped with ETL to process and extract datasets, transformed datasets through connection with AWS RDS and data was then loaded into PgAdmin.  
