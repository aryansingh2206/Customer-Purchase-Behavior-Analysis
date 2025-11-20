

# **Introduction**

OList, an online retail platform, has recently encountered financial losses and aims to optimize its inventory to eliminate unnecessary expenses. The goal is to determine which product categories can be removed without negatively impacting overall business performance.

---

# **Objective**

* Identify products that generate the highest revenue
* Analyze customer purchasing patterns to understand which products are bought independently or alongside others
* Recommend strategies to improve inventory planning and reduce excess costs

---

# **Assumptions**

* Only orders marked *“delivered”* are included in the analysis.
* `order_approved_at` is treated as equivalent to `order_purchase_timestamp`, and `order_delivered_timestamp` is considered equivalent to `order_estimated_delivery_date`.
* For market basket analysis, only product categories with more than five orders are considered.

---

# **Data Cleaning**

##### **Orders**

* Only successfully delivered orders are considered, accounting for ~97% of total orders.
* Missing `order_approved_at` values are filled using `order_purchase_timestamp`.
* Missing `order_delivered_timestamp` values are replaced with the corresponding `order_estimated_delivery_date`.

##### **Customer**

* Duplicate customer entries are removed, keeping only the first occurrence.

##### **Products**

* Missing product categories are filled with the mode, *"toys"*, since it represents nearly 75% of the dataset.
* Since product dimensions and weight are right-skewed and lack major outliers, missing values are imputed using median values instead of mean.

---

# **EDA and Visualizations**

A detailed exploratory analysis was conducted to uncover customer buying patterns. All visual dashboards were created in Tableau.

##### **Top 20 Products by Revenue and Order Count**

![image](https://user-images.githubusercontent.com/103338455/162641460-56a0dff3-acea-4c0d-b9f1-a314629d285c.png)

* Highest recorded revenue from a single product is 63,885.
* The top-earning product falls under the Toys category.
* Most high-earning products within the top 20 are categorized as toys.

![image](https://user-images.githubusercontent.com/103338455/162641468-69bc21ea-2940-4bfa-b8e2-67027d72118d.png)

* The most frequently purchased item has been ordered 467 times.
* Some products maintain strong demand despite high pricing.

##### **Orders by Category**

![image](https://user-images.githubusercontent.com/103338455/162641483-ba2974f5-fc58-46d1-b164-4fdc5be4c114.png)

* The Toys category leads with 74,929 total orders.
* Only the top 20 categories with more than five orders are displayed.

##### **Orders & Cumulative Revenue Share per Product**

![image](https://user-images.githubusercontent.com/103338455/162641492-62a0b28c-e9dd-4b7b-a4f3-9c4238132293.png)

* The revenue Pareto chart shows each product’s contribution to total revenue alongside order volume.
* Useful for determining product-level revenue impact.

---

# **Market Basket Analysis**

![image](https://user-images.githubusercontent.com/103338455/162641575-1fb21e24-14eb-446b-8ebf-57081cc4a67c.png)

* Market basket analysis highlights frequently purchased category combinations.
* Toys commonly co-occur with multiple other categories.

---

# **Ideal Category Depth**

![image](https://user-images.githubusercontent.com/103338455/162641638-04809218-8db1-4db3-a877-2480533bf75e.png)

* Revenue Pareto analysis helps determine optimal product depth within each category.

---

# **Inferences**

* *Toys* dominate sales, accounting for 74,929 orders (~76% of total).
* Other highly ordered categories include *health_beauty*, *bed_bath_table*, *sports_leisure*, *computer_accessories*, and *furniture_decor*—often purchased alone or alongside toys.
* Certain high-priced products still show strong demand.

---

# **Recommendations**

* Focus marketing efforts on customers likely to purchase toys, as this is the highest-demand category.
* Provide discounts or promotions on popular product combinations and high-frequency items to increase conversions.
* Optimize category depth by phasing out infrequently purchased items or those contributing minimally to revenue, helping reduce inventory overhead.

---

