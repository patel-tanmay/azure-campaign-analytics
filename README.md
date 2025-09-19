# azure-campaign-analytics

What is the business problem?
Criteo wants to improve the conversion rate of its ad campaigns by identifying which users should be shown an ad (treatment) and which should not (control). The goal is to maximize ROI by targeting only the users who are positively influenced by the ad.

What is uplift modeling solving here?
Traditional models predict conversion probability. Uplift models go one step further:
- They estimate the incremental impact of showing the ad vs not showing it — i.e., the causal effect.
- This helps in personalized targeting, showing ads only to users who are likely to convert because of the ad, not regardless of it.

🏁 My Goal:
Build an end-to-end uplift modeling pipeline that:
1. Identifies users who are persuadable (i.e., uplift-positive)
2. Avoids wasting ad budget on sure-things or lost causes
3. Visualizes key insights to leadership
4. Provides interpretable analysis (Qini curves, segment-level lift, etc.)
5. Suggests targeting strategies based on uplift tiers
