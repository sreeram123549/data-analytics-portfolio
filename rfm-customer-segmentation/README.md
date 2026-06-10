RFM Customer Segmentation Analysis
What This Project Is
I segmented 5,878 online retail customers into five groups based on how recently they bought, how often they buy, and how much they spend. The big finding: my best 3% of customers bring in almost 50% of the revenue.
The Data

What: 768K transactions from an online gift shop (Dec 2009 – Dec 2011)
Who: 5,878 unique customers
Cleaned: Removed ~45K transactions with missing customer IDs and duplicates (total 4.3% loss — fully documented)

How I Scored Customers
I gave every customer three scores (1–5 each):
Recency — How long since they last bought?

5 = bought within 2 weeks (awesome)
3 = bought 2–6 months ago (okay)
1 = haven't bought in over a year (gone)

Frequency — How often do they buy?

5 = 8+ purchases (super loyal)
3 = 3–4 purchases (casual)
1 = only 1 purchase (one-timer)

Monetary — How much do they spend total?

5 = over £2,900 (whale customer)
3 = £600–£1,200 (average)
1 = under £284 (small spender)

The Five Segments
NameHow Many% of RevenueWhat It MeansChampions160 (3%)~50%Perfect 5/5/5 — your VIPsLoyal890 (15%)~25%Really good customers, consistentAt Risk1,490 (25%)~15%Big spenders but haven't bought lately — need to win backPotential705 (12%)~5%Recent buyers, just haven't bought much yetLost370 (6%)~1%Haven't bought in forever, skip themOther1,724 (29%)~4%Middle-of-the-road customers — growth opportunity
The Key Insight
3% of customers = 50% of revenue. That's huge. It means if you keep your Champions happy, you're printing money. Losing even a few of them costs way more than losing 100 regular customers.
What I Used

MySQL — cleaned data and calculated the R/F/M scores
Power BI — made the dashboard and calculated the segment rules in DAX
Excel — figured out the score thresholds using percentiles

The Files

rfm_dashboard.pbix — the actual Power BI dashboard (open locally)
rfm_final.csv — customer-level scores if you want to explore more

What I Learned Building This

Data quality > data quantity. Those 45K rows I excluded mattered way less than getting the ones I kept exactly right.
Percentiles work better than guessing. Instead of picking arbitrary thresholds, I let the data tell me what "top 20%" actually meant.
Three simple metrics beat a thousand complex ones. R/F/M is powerful because everyone understands it.
Show the contrast. The real story wasn't "Champions have high revenue" — it was "Champions are a tiny slice with huge revenue." The treemap made that obvious.
