# Marketing Mix Modeling (MMM) Analysis – Revenue Drivers

## Overview
This project analyzes the impact of various marketing channels and business actions on weekly revenue using a multi-year dataset. The analysis identifies **positive and negative drivers of revenue** to inform marketing and pricing strategies.

---

([Open Notebook in Google Colab](https://colab.research.google.com/drive/1A2B3C4D5E6F7G8H9I0J))


## Raw Data
The dataset contains weekly data on:  

- Paid media spend (`facebook_spend`, `google_spend`, `tiktok_spend`, `instagram_spend`, `snapchat_spend`)  
- Social followers (`social_followers`)  
- Product pricing (`average_price`)  
- Promotions (`promotions`)  
- Direct marketing (`emails_send`, `sms_send`)  
- Revenue (`revenue`)  

---

## Methodology
- **Feature Engineering:** Log-transformation applied to spend variables to handle skewness.  
- **Mediator Assumption:** Google spend is treated as a mediator between social/display channels and revenue.  
- **Model:** Ridge regression (regularized linear regression) to estimate the effect of each input on revenue.  
- **Evaluation:** Coefficients interpreted as the relative contribution of each variable to revenue.  

---

## Key Findings

### Top Positive Drivers of Revenue
| Feature | Coefficient | Interpretation |
|---------|-------------|----------------|
| `log_instagram_spend` | 2.21 | Strongest positive impact – increasing Instagram spend increases revenue significantly. |
| `sms_send` | 0.55 | SMS campaigns positively contribute to revenue. |
| `google_pred` | 0.22 | Google spend (mediated via social/display channels) positively influences revenue. |
| `promotions` | 0.20 | Running promotions slightly increases revenue. |
| `emails_send` | 0.15 | Email campaigns have a small positive effect. |

### Top Negative Drivers of Revenue
| Feature | Coefficient | Interpretation |
|---------|-------------|----------------|
| `average_price` | -1.55 | Raising prices decreases revenue significantly. |
| `log_tiktok_spend` | -0.51 | TikTok spend has a negative impact on revenue in this dataset. |
| `social_followers` | -0.18 | More followers do not necessarily translate to higher revenue. |
| `log_facebook_spend` | -0.16 | Facebook spend slightly reduces revenue. |
| `log_snapchat_spend` | -0.03 | Snapchat spend has a very small negative effect. |

---

## Recommendations
1. Prioritize **Instagram ads, SMS campaigns, and Google channels** to maximize revenue.  
2. Monitor **pricing strategies carefully**, as increases in average price reduce revenue.  
3. Review spending on TikTok, Facebook, and Snapchat; optimize or reallocate budget.  
4. Use promotions and emails strategically to support revenue growth.   

---

Ankit Pallav | ankitpallav2602@gmail.com
