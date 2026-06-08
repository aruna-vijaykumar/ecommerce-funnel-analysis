# E-Commerce Funnel & Customer Analytics
An end-to-end analysis of user behavior, revenue drivers, and customer retention for an e-commerce platform, using five interconnected tables covering 2.4M+ events, 125K orders, and 100K users.

## Objectives

- Analyze user progression through the purchase funnel
- Identify which traffic sources drive conversion
- Evaluate revenue drivers across departments, brands, and customer segments
- Measure customer retention and repeat purchase behavior using cohort analysis


## Dataset
Five relational tables:
**Table**     **Description**                                  **Rows**      
events        User session events (views, cart, purchase)      2,431,963
orders        Order-level transactions and statuses            125,226
order_items   Item-level order details with pricing            181,759
users         Customer demographics and acquisition source     100,000
products      Product catalog with category, brand, pricing    29,120

## Tools & Technologies
Python · Pandas · NumPy · Matplotlib · Seaborn 

## Key Findings

### Funnel

- 63.4% of product viewers added an item to cart
- 42.1% of cart sessions completed a purchase
- Overall product-view to purchase conversion rate: 26.7%
- Conversion rates are consistent across all traffic sources (26.5%–26.9%), suggesting checkout experience matters more than acquisition channel

### Revenue

- Men's department generated higher total revenue ($5.74M) than Women's ($5.09M) despite women making slightly more purchases — indicating higher average order value in men's products
- Top revenue categories: Outerwear & Coats, Jeans, Sweaters
- Cancellation rate: 14.86% — uniform across all categories, pointing to a platform/checkout issue rather than product-specific friction
- Average delivery time: 3.5 days

### Retention & Cohorts

- 37.7% of customers made more than one purchase
- Repeat buyers placed an average of 2.5 orders
- Steepest drop-off between 2nd and 3rd purchase (20,231 → ~5,000 customers)
- Mean monthly cohort retention rate: 12.8%
- Re-engagement campaigns targeted 3–6 months after a second purchase represent the highest-leverage retention opportunity


## Visualizations
Purchase Funnel

<img width="547" height="529" alt="image" src="https://github.com/user-attachments/assets/b497a855-e39c-43f4-9fe4-df8a6c0aa8dd" />



Funnel by Traffic Source

<img width="1189" height="589" alt="image" src="https://github.com/user-attachments/assets/51edf469-32ca-48eb-9b2a-7da61ca663c5" />



Revenue by Category

<img width="758" height="453" alt="image" src="https://github.com/user-attachments/assets/e6ce2354-4ed8-4f99-b994-8b1d18562b42" />



Revenue by Department

<img width="409" height="409" alt="image" src="https://github.com/user-attachments/assets/17a1f6ce-3a79-4dc5-9383-f235d94078f5" />



Cohort Retention Heatmap

<img width="1089" height="590" alt="image" src="https://github.com/user-attachments/assets/de80040b-e8d5-42d1-8e78-5a19110da7d7" />


Project Structure
-  Funnel_Analysis.ipynb   # Full analysis notebook
-  images/                 # Chart exports
-  README.md

## Business Recommendations

**1. Fix the cart abandonment drop-off first**
57.9% of users who add to cart don't complete a purchase. Since conversion rates
are uniform across all traffic sources (26.5%–26.9%), the problem is in the
checkout experience, not acquisition. A/B test checkout flow simplification,
guest checkout, and payment options before investing further in traffic acquisition.

**2. Investigate the 14.86% cancellation rate**
Cancellations are uniform across all categories, which rules out product-specific
issues and points to a platform or fulfillment problem — likely checkout confusion,
payment failures, or delivery expectation mismatch. Audit the post-purchase flow.

**3. Scale email marketing**
Email drives the highest purchase volume at the same conversion efficiency as
other channels. It is the most cost-effective channel to scale — increase email
list growth and campaign frequency before increasing spend on paid channels.

**4. Prioritize men's department marketing**
Men's products generate more revenue ($5.74M vs $5.09M) despite fewer purchases,
meaning higher average order value. Targeted campaigns for men's outerwear, jeans,
and sweaters would maximize revenue per campaign dollar.

**5. Target the second-to-third purchase gap**
The steepest retention drop-off is between 2nd and 3rd purchase (20,231 → ~5,000
customers). A re-engagement campaign — discount, loyalty points, or personalized
recommendation — sent 3–6 months after a second purchase is the single highest-
leverage retention opportunity in this dataset.

**6. Don't over-invest in retention too early**
Monthly cohort retention averages ~2.8%, meaning most repeat purchases are
infrequent. Focus first on converting first-time buyers to a second purchase
(the 62.3% one-time buyer problem) before optimizing for long-term loyalty.

## Limitations

- Session-based funnel: Built at session level, not user level. A single user abandoning and returning across multiple sessions is counted as separate funnel entries.
- Traffic source attribution: Uses the source recorded at event time. Multi-touch attribution is not accounted for.
- Cohort scope: Measures repeat purchasing only — browsing or wishlist activity between purchases is not captured.
- Causal inference: All associations are correlational. No causal claims are made without experimental validation such as A/B testing.
