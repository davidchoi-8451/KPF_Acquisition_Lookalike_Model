# KPF 3P Gift Lookalike Model to refine Acquisition strategy for 2026 and forward, starting with Holiday.

Goal: Create a look-alike model to predict new acquisition HHs in the gift card category and evaluate how different the targeted HHs is from our current acquisition strategy. Test this new targeting strategy for future campaigns.

Current Acquisition Strategy: Very generic strategy with potential overlap of HHs in groups.
-	3-Month Fuel Redeemers (Three-Month Fuel Redeemers): Households that have used fuel points to get a discount (points redeemed < 0) within the last 12 weeks. H/M/L segment.
-	Functional Loyalty: New Households: FunLo labeled as completely new households.
-	Functional Loyalty: Top Loyal 
-	L52W Open Loop Buyers (l52_open_loop_buyers): Customers who purchased Open Loop gift cards in the last 52 weeks (Golden Rules and Division Exclusions Applied).
-	L52W Greeting Card Buyers (l52_greeting_card_buyers): Shoppers who bought greeting cards in the last year (Golden Rules and Division Exclusions Applied).
-	L52W 3P Gift Card Buyers (l52_3p_gift_buyers): Shoppers who bought Gift Cards in the last year.
-	Lapsed 3rd Party Gift Card Buyers (lapsed_3p_gift_buyers): HHs who did not buy gift cards last year, but purchased 2 years ago

Using KPF-specific data and features that more closely tie in with KPF business knowledge,
  1. Create a binary classification model that distinguishes a potential 3P Gift HH from a non-gifting HH.
  2. In the future, use causal inference to determine: out of the HHs that we targeted successfully with the lookalike model, how many of those were organic? Vs. how many of those HHs actually converted as a result of
     our campaigns / targeting? AKA what is the TRUE uplift in HHs as a result of KPF campaigns?

EDA File: Utilized KPM, KPF, ACDS, and Fuel Points metadata to create feature ideas + retroactively test features of soon-to-be gift HHs vs. non gift HHs (test vs. control) to see if there is any advantage in using those features. 
Features include: 
- Net Spend Amt - Worked well in legacy model, easy feature to add / prune
- Transaction and buyer history (spend per trip, total trip, number trips) during most recent holiday season (biggest kpf gifting season + first test with acquisition model being done in 26 Holiday)
- Transaction and buyer history (spend per trip, total trip, number trips) during most recent easter / mothers day / fathers day / graduation seasons (kpf gifting seasons)
- Greeting Card Sales, Number of trips involving greeting cards, avg number of days between transactions involving greeting cards, Flag (are they a one time greeting card buyer or not)
- Fuel Points Redemption and Earned Amount (lifetime, last month)
- Digital Engagement Segmentation (People who interact w/ Kroger digital media .. are they more likely to interact with SSEs, TDC, PUSH, ect)
- Customer Dimensions (funlo): Price, Health, Convenience Dimensions
- More .. ask Michelle Kelleher

Note that features in the diagnostic EDA file will be modified to prevent data leakage in the actual train/validation/test sets.
