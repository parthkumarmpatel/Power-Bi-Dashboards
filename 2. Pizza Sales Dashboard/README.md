# 🍕 Pizza Sales Dashboard

## **Project Overview**
This project is a comprehensive **Pizza Sales Dashboard** designed to provide actionable insights into sales performance, order trends, and pizza popularity. The dashboard combines **SQL queries** for data extraction with **Power BI** for visualization and interactive reporting.  

The goal of the dashboard is to help stakeholders quickly identify trends in revenue, top-selling pizzas, customer ordering patterns, and performance by category and size.  

---

## **Data Source**
- **Database:** `pizza_sales` table  
- **Key Columns:** `order_id`, `order_date`, `pizza_name`, `pizza_category`, `pizza_size`, `quantity`, `total_price`  

---

## **Key Metrics (KPIs)**
The dashboard highlights essential business KPIs:

| KPI | Description |
|-----|-------------|
| **Total Revenue** | Total sales revenue generated over the period |
| **Average Order Value** | Average value of a single order |
| **Total Pizza Sold** | Total number of pizzas sold |
| **Total Orders** | Count of distinct customer orders |
| **Average Pizzas per Order** | Average number of pizzas per order |

> These KPIs provide a high-level overview of overall sales performance.  

---

## **Visual Insights**
The dashboard contains a series of interactive visualizations to explore trends and patterns:  

### **1. Daily Orders Trend**
- Shows the distribution of total orders by day of the week.  
- Highlights peak ordering days and helps identify **weekend spikes** in sales.  

### **2. Monthly Orders Trend**
- Displays total orders by month.  
- Helps track **seasonal sales trends**, with higher sales in months like **January and July**.  

### **3. Pizza Category Analysis**
- Shows percentage contribution of each pizza category to total sales.  
- Helps identify **most popular categories** and focus areas for marketing or menu optimization.  

### **4. Pizza Size Analysis**
- Displays sales contribution by pizza size.  
- Identifies **most ordered pizza sizes**, supporting inventory and production planning.  

### **5. Top and Bottom Performing Pizzas**
- Highlights **Top 5 pizzas by revenue and quantity sold**.  
- Also identifies **Bottom 5 pizzas** to guide menu review or promotions.  
- Helps focus business strategy on **high-performing products** and improve low-performing ones.  

---

## **Dashboard Features**
- **Interactive filters:** Slice data by **date, category**.  
- **Dynamic insights:** Top/bottom performers update automatically with applied filters.  
- **Readable KPI cards:** Display critical metrics at a glance.  
- **Text-based commentary:** Highlights key insights in plain language for decision-makers.  

---

## **Technologies Used**
- **SQL:** For data extraction from the pizza sales database. (Data Validation) 
- **Power BI:** For interactive dashboards, charts, and KPI cards.(Insights)  
- **DAX Measures:** To compute dynamic insights and text commentary.  

---

## **Usage**
- Open the Power BI dashboard file.  
- Use **slicers** for filtering by **date, category, or size**.  
- KPI cards and charts will automatically update to reflect the selected filters.  
- Review **top/bottom performers** and percentage breakdowns for actionable insights.  

---

## **Outcome**
This dashboard allows stakeholders to:  
- Identify **peak sales periods** by day and month.  
- Understand **customer preferences** by category and size.  
- Quickly spot **high and low-performing pizzas**.  
- Make **data-driven business decisions** for promotions, menu optimization, and inventory management.  
