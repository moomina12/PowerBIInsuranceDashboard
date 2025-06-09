📊 Power BI Dashboar: Loss Analytics by Region & Policy Type

Overview
This dashboard analyzes insurance losses across different Regions and Policy Types, providing insights into loss distribution, profitability, and performance.

Dataset Used: Reinsurance dataset with columns include 
Region,Policy Type,Loss Amount,Premium Collected,Claim Count, Year

📈 Visuals & Metrics
1. ✅ Loss Distribution Pie Chart
   
Visual: Pie Chart used to quickly identify which categories (e.g., Region) contribute most to total losses.

3. 📊 Loss Ratio (%)
Loss Ratio = DIVIDE(SUM('ClaimsData'[Loss Amount]), SUM('ClaimsData'[Premium Collected]))
Visual: Card or Matrix
Insight: Shows loss as a percentage of premiums collected. High values indicate low profitability.

4. Average Claim Severity
Avg Claim Severity
Insight: Average payout per claim — helps detect high-cost claim categories.

5. Underwriting Margin

Underwriting Margin
Insight: Shows profitability of segments (positive = profit, negative = loss).

6. 🧠 Loss-to-Premium Share Ratio

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
Insight: Displays region with highest total losses (e.g., "West ($3.5M)")

8. Dynamic Insight Card
Visual: Card or Multi-row card
Insight: Changes dynamically with filters/slicers (e.g., Year, Product).

Slicers & Filters
Recommended slicers with Year, Region, and policy type
These dynamically update most measures and visuals.
