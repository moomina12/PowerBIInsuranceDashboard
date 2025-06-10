📊 Power BI Dashboar: Loss Analytics by Region & Policy Type

Overview
This dashboard analyzes insurance losses across different Regions and Policy Types, providing insights into loss distribution, profitability, and performance.

Dataset Used: Reinsurance dataset with columns include 
Region,Policy Type,Loss Amount,Premium Collected,Claim Count, Year

📈 Visuals & Metrics
1. ✅ Loss Distribution Pie Chart
   
Visual: Pie Chart used to quickly identify which categories (e.g., Region) contribute most to total losses.

3. 📊 Loss Ratio (%)
Loss Ratio:
Visual: Card or Matrix
Insight: Shows loss as a percentage of premiums collected. High values indicate low profitability.

4. Average Claim Severity
Avg Claim Severity
Insight: Average payout per claim — helps detect high-cost claim categories.

5. Underwriting Margin

Underwriting Margin
Insight: Shows profitability of segments (positive = profit, negative = loss).

6. Loss-to-Premium Share Ratio

Loss Share % and Premium Share % used to calculate Loss to Premium Share Ratio which then used to calculate the policy risk category

Policy Risk Category = 
SWITCH(
    TRUE(),
    [Loss to Premium Share Ratio] >= 1.2, "Unprofitable",
    [Loss to Premium Share Ratio] >= 0.9, "Borderline",
    [Loss to Premium Share Ratio] < 0.9, "Healthy",
    "Unknown"
)

Used this new measure in Table/Matrix visual with conditional formatting.

7) Highest Loss Region with Amount
Visual: Card
Insight: Displays region with highest total losses )

8. Dynamic Insight Card
Visual: Card or Multi-row card
Insight: Changes dynamically with filters/slicers (e.g., Year, Product).

Slicers & Filters
Recommended slicers with Year, Region, and policy type
These dynamically update most measures and visuals.


INSIGHTS
Top Loss-Contributing business segments:

Identify which region, policy type, or product is responsible for the largest share of total losses.

Here, Marine and liability policies in almost all regions contributing approximately 20% and above loss.

2. Identify High-Risk Areas
Insights: 1.A region or category with a disproportionately large slice may indicate higher risk exposure.

Action Required: Investigate underwriting practices, claim patterns, or environmental factors in that segment.

3. Underperforming policy types
If a policy type has high loss share but low premium share, it may be unprofitable.

Action required: Cross-check with premium distribution to evaluate loss ratios per segment.

4. Opportunities for Repricing or Re-underwriting
High-loss segments may require:
Premium adjustments
Stricter underwriting
Product redesign

5. Loss Concentration
If the chart shows heavily concentrated losses (e.g., one region is 70% of losses), the business has geographic concentration risk.

Action Required: Diversification strategies might be necessary.

6. Comparative Risk
Comparing pie charts for different dimensions (e.g., Loss by Region vs. Loss by Policy Type) helps pinpoint whether geography or product type drives losses more.
