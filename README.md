# DataCo Smart Supply Chain Analytics

> **Digital Pioneers of Egypt Initiative (رواد مصر الرقمية)** · Data Analytics Track · Team Project

**Short description:** End-to-end analysis of the DataCo global supply chain: late deliveries, profitability, fraud signals and customer value, ending in an interactive dashboard and actionable recommendations.

---

## About the Project

DataCo sells products across several markets and regions. Its management struggles with three recurring problems:

- **Late deliveries**, which hurt customer satisfaction and repeat purchases.
- **Profit leaks** caused by discounts, loss-making products and costly shipping modes.
- **Blind spots** in fraud and customer value.

**Our goal** is to turn the company's data into decisions: where and why orders are late, where money is lost, who the valuable customers are, and what the company should do about each.

**What we analyze**

| Area | Focus |
|---|---|
| Delivery performance | Late-delivery rate by shipping mode, market, region and route; scheduled vs. actual shipping days |
| Profitability | Profit by category and product; effect of discounts on margin; loss-making orders |
| Customers | Sales concentration (80/20), segments, RFM, repeat purchases |
| Risk & fraud | Suspected-fraud and canceled orders by payment type, market and category |
| Demand & time | Monthly trends and seasonality |

**Deliverables:** cleaned and anonymized data · analysis notebooks · a 6-page dashboard · final report and presentation.

## 🇪🇬 عن المشروع

شركة DataCo بتبيع منتجاتها في أسواق ومناطق كتير، والإدارة بتواجه ٣ مشاكل متكررة:

- **تأخير في التوصيل** بيأثر على رضا العميل وإعادة الشراء.
- **تسريب في الربح** بسبب الخصومات والمنتجات الخسرانة ووسائل الشحن الغالية.
- **نقاط عمى** في الاحتيال وقيمة العملاء.

**هدفنا** إننا نحوّل بيانات الشركة لقرارات: فين وليه الطلبات بتتأخر، فين الفلوس بتضيع، مين العملاء المهمين، وإيه اللي المفروض الشركة تعمله في كل حالة.

**اللي هنحلله:** أداء التوصيل · الربحية والخصومات · العملاء (RFM) · المخاطر والاحتيال · الطلب والموسمية.

**المخرجات:** بيانات نضيفة ومجهولة الهوية · Notebooks للتحليل · داشبورد من ٦ صفحات · تقرير نهائي وعرض تقديمي.

---

## 📄 Documentation

The full **project description and data dictionary (metadata)** is in
[`docs/DataCo_Project_Description_and_Metadata.md`](docs/DataCo_Project_Description_and_Metadata.md).

## 👥 Team

| # | Name | Role |
|---|---|---|
| 1 | Zeyad Mohamed Moustafa Elsaeed | Team Leader |
| 2 | Ahmed Younis Atteia Elmeshad | Team Member |
| 3 | Hazem Ayman Mohammed Najib | Team Member |
| 4 | Kerolos Awad Jattas Attiya | Team Member |
| 5 | Rana Mohamed Abdalla Asker | Team Member |
| 6 | Shahd Gamil Salama Mahmoud | Team Member |

See [`TEAM.md`](TEAM.md).

## 🗂️ Data

| File | Description |
|---|---|
| `DataCoSupplyChainDataset.csv` | Orders, customers, products, shipping, sales and profit (53 columns, one row per order item) |
| `DescriptionDataCoSupplyChain.csv` | Official data dictionary |

> **Privacy:** customer personal data (name, email, street, password) is removed from any file published in this repository. If a raw file is too large for GitHub, it is not committed; use the cleaned version in `data/processed/` instead.

## 🧰 Tech Stack

Data Analysis & Visualization: Power BI · Tableau · Excel · Power Query · Python (Pandas, NumPy, Matplotlib, Seaborn) · SQL (as needed) · Git & GitHub

## 📁 Repository Structure

```
├── data/
│   ├── raw/            # original files (only if free of personal data and under size limits)
│   └── processed/      # cleaned, anonymized data
├── notebooks/          # cleaning and EDA
├── dashboard/          # dashboard file and screenshots
├── docs/               # project description & metadata (PDF)
├── reports/            # final report and slides
├── README.md
└── TEAM.md
```

## 📌 Status

In progress. Findings, dashboard and recommendations will be added as each phase is completed.

## 📚 Source

Public "DataCo Smart Supply Chain for Big Data Analysis" dataset (Kaggle), used for educational purposes.
