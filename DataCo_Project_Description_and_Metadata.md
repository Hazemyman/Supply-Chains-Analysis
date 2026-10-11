# DataCo Smart Supply Chain Analytics

**Project Description & Data Dictionary (Metadata)**  
Digital Pioneers of Egypt Initiative (رواد مصر الرقمية) · Data Analytics Track

## Team

| # | Team member | Role |
|---|---|---|
| 1 | Zeyad Mohamed Moustafa Elsaeed | Team Leader |
| 2 | Ahmed Younis Atteia Elmeshad | Team Member |
| 3 | Hazem Ayman Mohammed Najib | Team Member |
| 4 | Kerolos Awad Jattas Attiya | Team Member |
| 5 | Rana Mohamed Abdalla Asker | Team Member |
| 6 | Shahd Gamil Salama Mahmoud | Team Member |

---

## 1. Project Description

**What we are doing.** We are analyzing the order, shipping, customer and product data of DataCo, a company that sells across several markets and regions. The work covers data cleaning, exploratory analysis, an interactive dashboard and a set of recommendations.

**Business problem**

- **Late deliveries** hurt customer satisfaction and repeat purchases.
- **Profit leaks** come from discounts, loss-making products and costly shipping modes.
- **Blind spots** exist in fraud and customer value.

> **Goal:** turn the data into decisions: where and why orders are late, where money is lost, who the valuable customers are, and what the company should do about each.

## 2. Objectives

- Measure delivery performance and identify where and why late deliveries happen.
- Find where profit is lost: products, categories, discount levels, markets and shipping modes.
- Understand customers: value concentration, segments and repeat behavior.
- Locate fraud and cancellation hot spots.
- Deliver clear recommendations: each finding ends with an action and an expected impact.

## 3. What We Will Analyze

| Area | Questions we answer |
|---|---|
| Delivery performance | What share of orders is late? How does it vary by shipping mode, market, region, route and month? Is the scheduled delivery promise realistic? |
| Profitability | Which categories and products make or lose the most profit? At what discount level do orders start losing money? What do loss-making orders have in common? |
| Customers | Who are the top customers (80/20)? How do segments compare? Who is at risk of churning (RFM)? Does a late delivery reduce repeat purchases? |
| Risk & fraud | How frequent are suspected-fraud and canceled orders, and in which payment types, markets and categories? |
| Demand & time | What are the monthly and weekly trends and seasonality of orders and sales? |

## 4. Planned Deliverables

- Cleaned and anonymized dataset, with a cleaning log.
- Analysis notebooks (cleaning and exploration).
- Interactive dashboard (6 pages): Executive Overview · Delivery Performance · Profitability & Discounts · Customers · Risk & Fraud · Recommendations & Data Notes.
- Final report and presentation.

## 5. Key KPIs

Late Delivery Rate · Average Delay (days) · Total Sales · Total Profit · Profit Margin % · Average Discount % · Loss-making Orders % · Fraud Rate · Cancel Rate · Average Order Value · Repeat Customer Rate.

## 6. Datasets

| File | Content | Grain |
|---|---|---|
| `DataCoSupplyChainDataset.csv` | Orders, customers, products, shipping, sales and profit: 53 columns | One row per order item (an Order Id can repeat) |
| `DescriptionDataCoSupplyChain.csv` | Official data dictionary | One row per column |

## 7. Metadata: Data Dictionary of the Main Dataset

Descriptions follow the official dictionary (`DescriptionDataCoSupplyChain.csv`). The last column states how our team treats each field.

### Shipping & delivery (7)

| Field | Description (official dictionary) | How we treat it |
|---|---|---|
| `Type` | Type of transaction made | Dimension |
| `Days for shipping (real)` | Actual shipping days of the purchased product | Measure |
| `Days for shipment (scheduled)` | Days of scheduled delivery of the purchased product | Measure |
| `Delivery Status` | Delivery status of orders: Advance shipping, Late delivery, Shipping canceled, Shipping on time | Dimension · derived from real vs. scheduled days |
| `Late_delivery_risk` | Categorical variable that indicates if sending is late (1) or not late (0) | Main late-delivery flag |
| `Shipping date (DateOrders)` | Exact date and time of shipment | Date |
| `Shipping Mode` | Shipping modes: Standard Class, First Class, Second Class, Same Day | Dimension |

### Customer (11)

| Field | Description (official dictionary) | How we treat it |
|---|---|---|
| `Customer Id` | Customer ID | Identifier |
| `Customer Fname` | Customer name | Personal data · removed |
| `Customer Lname` | Customer last name | Personal data · removed |
| `Customer Email` | Customer's email | Personal data · removed |
| `Customer Password` | Masked customer key | Personal data · removed |
| `Customer Segment` | Types of customers: Consumer, Corporate, Home Office | Dimension |
| `Customer City` | City where the customer made the purchase | Dimension |
| `Customer Country` | Country where the customer made the purchase | Dimension |
| `Customer State` | State to which the store where the purchase is registered belongs | Dimension · store-level |
| `Customer Street` | Street to which the store where the purchase is registered belongs | Personal data · removed |
| `Customer Zipcode` | Customer zipcode | Dimension |

### Order (10)

| Field | Description (official dictionary) | How we treat it |
|---|---|---|
| `Order Id` | Order code | Identifier · repeats per order item |
| `order date (DateOrders)` | Date on which the order is made | Date |
| `Order Customer Id` | Customer order code | To verify vs. Customer Id |
| `Order Status` | COMPLETE, PENDING, CLOSED, PENDING_PAYMENT, CANCELED, PROCESSING, SUSPECTED_FRAUD, ON_HOLD, PAYMENT_REVIEW | Dimension |
| `Market` | Market where the order is delivered: Africa, Europe, LATAM, Pacific Asia, USCA | Dimension |
| `Order Region` | Region of the world where the order is delivered (24 regions) | Dimension |
| `Order Country` | Destination country of the order | Dimension |
| `Order State` | State of the region where the order is delivered | Dimension |
| `Order City` | Destination city of the order | Dimension |
| `Order Zipcode` | Not described in the official dictionary | To profile (likely mostly empty) |

### Order item & finance (12)

| Field | Description (official dictionary) | How we treat it |
|---|---|---|
| `Order Item Id` | Order item code | Identifier (row level) |
| `Order Item Cardprod Id` | Product code generated through the RFID reader | To verify vs. Product Card Id |
| `Order Item Product Price` | Price of products without discount | Measure |
| `Order Item Quantity` | Number of products per order | Measure |
| `Order Item Discount` | Order item discount value | Measure |
| `Order Item Discount Rate` | Order item discount percentage | Measure |
| `Sales` | Value in sales | Measure · definition to verify |
| `Order Item Total` | Total amount per order | Measure · definition to verify |
| `Order Item Profit Ratio` | Order item profit ratio | Measure |
| `Order Profit Per Order` | Order profit per order | Measure · main profit field |
| `Benefit per order` | Earnings per order placed | To verify vs. Order Profit Per Order |
| `Sales per customer` | Total sales per customer made per customer | Customer-level value · never summed |

### Product & category (11)

| Field | Description (official dictionary) | How we treat it |
|---|---|---|
| `Product Card Id` | Product code | Identifier |
| `Product Category Id` | Product category code | To verify vs. Category Id |
| `Category Id` | Product category code | Identifier |
| `Category Name` | Description of the product category | Dimension |
| `Department Id` | Department code of store | Identifier |
| `Department Name` | Department name of store | Dimension |
| `Product Name` | Product name | Dimension |
| `Product Price` | Product price | Measure |
| `Product Description` | Product description | To profile (likely empty) |
| `Product Image` | Link of visit and purchase of the product | Not analytical · dropped |
| `Product Status` | Status of the product stock: 1 = not available, 0 = available | Dimension (stock availability) |

### Geography (2)

| Field | Description (official dictionary) | How we treat it |
|---|---|---|
| `Latitude` | Latitude corresponding to location of store | Store location (not destination) |
| `Longitude` | Longitude corresponding to location of store | Store location (not destination) |

## 8. Data Notes & Limitations

- **Grain:** the main file is at order-item level. Orders are counted with distinct Order Id.
- **Personal data:** name, email, street and the masked password are removed before anything is published.
- **Delivery fields:** Delivery Status, Late_delivery_risk and the actual vs. scheduled shipping days describe the same event, so they are used consistently. Orders with "Shipping canceled" are excluded from delay analysis.
- **Possible duplicates** (verified by comparing values before removal): Benefit per order vs. Order Profit Per Order · Order Item Cardprod Id vs. Product Card Id · Product Category Id vs. Category Id · Order Customer Id vs. Customer Id.
- **Sales per customer** is a customer-level total repeated on each row, so it is never summed.
- **Coordinates** describe the store location, not the delivery destination; delivery maps use Order Country and Order Region.
- **Money fields:** the dictionary does not say whether Sales and Order Item Total are before or after discount. We settle this with formulas on the data.
- **Source:** public dataset, used for educational purposes; findings describe patterns in this dataset.

---

<div dir="rtl">

# وصف المشروع

تحليل سلسلة الإمداد لشركة DataCo · مبادرة رواد مصر الرقمية · مسار تحليل البيانات

## إحنا داخلين نعمل إيه؟

بنحلل بيانات الطلبات والشحن والعملاء والمنتجات لشركة DataCo، وهي شركة بتبيع في أسواق ومناطق كتير. الشغل بيشمل تنظيف الداتا، والتحليل الاستكشافي، وداشبورد تفاعلي، وتوصيات قابلة للتنفيذ.

## المشكلة

- **تأخير في التوصيل** بيأثر على رضا العميل وإعادة الشراء.
- **تسريب في الربح** بسبب الخصومات والمنتجات الخسرانة ووسائل الشحن الغالية.
- **نقاط عمى** في الاحتيال وقيمة العملاء.

## هدفنا

> نحوّل الداتا لقرارات: فين وليه الطلبات بتتأخر، فين الفلوس بتضيع، مين العملاء المهمين، وإيه اللي المفروض الشركة تعمله في كل حالة.

## هنحلل إيه؟

- **أداء التوصيل:** نسبة التأخير حسب وسيلة الشحن والسوق والمنطقة والمسار، وهل الوعد المجدول واقعي.
- **الربحية:** أكتر وأقل الفئات والمنتجات ربحًا، وأثر الخصم على الهامش، والطلبات الخسرانة.
- **العملاء:** تركّز المبيعات (قاعدة 80/20)، والشرائح، وتقسيم RFM، وأثر التأخير على إعادة الشراء.
- **المخاطر والاحتيال:** الاحتيال المشتبه به والإلغاء حسب طريقة الدفع والسوق والفئة.
- **الطلب والوقت:** الاتجاهات الشهرية والموسمية.

## المخرجات

- بيانات نضيفة ومجهولة الهوية مع سجل التنظيف.
- Notebooks للتنظيف والتحليل.
- داشبورد من ٦ صفحات.
- تقرير نهائي وعرض تقديمي.

## ملاحظات على الداتا

- الملف الأساسي على مستوى عنصر الطلب (٥٣ عمود)، فعدد الطلبات بيتحسب بـ Order Id مميز.
- البيانات الشخصية (الاسم والإيميل والشارع والباسورد) بتتشال قبل أي نشر.
- حالة التوصيل وخطر التأخير وأيام الشحن كلها بتوصف نفس الحدث، فبنتعامل معاها بشكل متسق، والطلبات الملغية بتتشال من تحليل التأخير.
- الإحداثيات بتعبّر عن موقع المتجر مش وجهة التوصيل.

</div>
