In this lab, we were given a file to complete it code blocks and answer it's questions.
1- Why is this an unsupervised learning problem?
It is unsupervised because there are no target labels (no “correct answer” or predefined customer groups). The goal is to discover hidden patterns or segments in the data using only input features. 

2- Why did we remove the CUST_ID column?
CUST_ID is just an identifier and does not contain meaningful behavioral information (numeric info). Keeping it would not help clustering and could distort results because it is non-numeric and unique for each customer.

3- Which columns had missing values?
CREDIT_LIMIT & MINIMUM_PAYMENTS

4- How did you handle the missing values?
they were handeled by scalling them, using the mean of each numeric column.

5- Why is scaling important before applying K-Means?
K-Means uses distance (Euclidean distance) to form clusters. If features are on different scales, large-scale features dominate the clustering. StandardScaler ensures all features contribute equally.

6- Which K value did you choose? Explain using elbow and silhouette score.
The chosen value was K = 4. From the elbow curve, inertia decreases sharply until around K=4, then the improvement slows down. The silhouette score is relatively high around K=4 compared to other values, indicating well-separated clusters.
So K=4 provides a good balance between compact clusters and interpretability.

7- Describe each customer segment using the cluster summary.
Cluster 0 → Moderate balance → moderate purchases → high frequency → low cash advance → regular active users
Cluster 1 → Very high balance → very high purchases → high payments → high credit limit → high-value premium customers
Cluster 2 → High balance → very high cash advance → very low purchases → cash advance dependent users
Cluster 3 → Low balance → very low purchases → low frequency → low engagement → inactive users

8- Which cluster represents high-value customers?
Cluster 1, Because it has:
Highest purchases (7681)
Highest credit limit (9696)
Highest payments (7288)
Strong usage across all purchase types.

9- Which cluster represents customers who rely more on cash advance?
Cluster 2, Because it has:
Extremely high CASH_ADVANCE (4520)
Highest CASH_ADVANCE_FREQUENCY (0.48)
Very low purchases (502)
Very low purchase frequency (0.28)

10- How can a company use these clusters for marketing strategy?
Cluster 0 → Target with loyalty rewards → cashback offers → nudges to increase spending frequency → encourage gradual upgrade to premium usage
Cluster 1 → Retain with VIP benefits → premium credit card perks → exclusive rewards → personalized high-limit offers → protect this high-value segment
Cluster 2 → Offer financial support products → cash advance alternatives (loans, installment plans) → risk monitoring → credit counseling or repayment restructuring options
Cluster 3 → Reactivation campaigns → low-fee cards → introductory offers → spending incentives → aim to increase engagement and usage
