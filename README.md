# Experiment 1.B : Product Price Analysis Using Python Functions

## Aim
To analyze quarterly product sales data across multiple products and quarters using 2D NumPy arrays and Python statistical functions.

## Algorithm

1. **Start** the program.
2. **Import Library**: Import the `numpy` module as `np` for numerical array operations.
3. **Initialize 2D Sales Matrix**: Create a $3 \times 4$ NumPy array `sales` containing quarterly sales figures for 3 products across 4 quarters.
4. **Compute Product-Wise Totals**: Calculate the sum of sales across columns (`axis=1`) for each product using `np.sum(sales, axis=1)`.
5. **Compute Quarter-Wise Totals**: Calculate the sum of sales across rows (`axis=0`) for each quarter using `np.sum(sales, axis=0)`.
6. **Compute Overall Statistical Metrics**:
   * Calculate the overall mean sales across all entries using `np.mean(sales)`.
   * Identify the maximum sales figure using `np.max(sales)`.
   * Identify the minimum sales figure using `np.min(sales)`.
7. **Display Analysis Summary**: Print the original sales matrix, product-wise totals, quarter-wise totals, overall average, highest sale, and lowest sale.
8. **Stop** the program.
## Program

import pandas as pd  

# Customer Data Exploration using Pandas  
 
# Step 1: Create a sample customer dataset  
data = {  
    "Customer_ID": [101, 102, 103, 104, 105, 106, 107, 108],  
    "Customer_Name": [  
        "Ananya Sharma",  
        "Rohan Verma",  
        "Priya Nair",  
        "Karthik Iyer",  
        "Meera Krishnan",  
        "Arjun Mehta",  
        "Divya Menon",  
        "Vikram Rao",  
    ],            
    "Region": [    
        "South",  
        "North",  
        "South",  
        "South",  
        "West",  
        "North",  
        "West",  
        "East",  
    ],  
    "Age": [28, 35, 24, 42, 31, 46, 29, 38],  
    "Annual_Income": [65000, 82000, 52000, 95000, 74000, 88000, 61000, 71000],  
    "Spending_Score": [78, 64, 85, 58, 91, 52, 73, 69],  
    "Loyalty_Years": [3, 6, 2, 8, 5, 9, 4, 5],  
}  

# Step 2: Convert to a Pandas DataFrame  
df = pd.DataFrame(data)  
print("--- Full Customer Dataset ---")  
print(df)  

# Step 3: Basic exploration  
print("\n--- Shape ---")  
print(df.shape)  

print("\n--- Columns ---")  
print(df.columns)  

print("\n--- DataFrame Info ---")  
df.info()  

print("\n--- Descriptive Statistics ---")  
print(df.describe())  

# Step 4: Display first and last few records  
print("\n--- First 3 Records ---")  
print(df.head(3))  

print("\n--- Last 3 Records ---")  
print(df.tail(3))  
  
# Step 5: Sort customers by Annual Income (descending)  
sorted_by_income = df.sort_values(by="Annual_Income", ascending=False)  
print("\n--- Customers Sorted by Annual Income (Descending) ---")  
print(sorted_by_income)  

# Step 6: Filter high-income customers (Income > 70000)  
high_income_customers = df[df["Annual_Income"] > 70000]          
print("\n--- High-Income Customers (Annual_Income > 70000) ---")    
print(high_income_customers)  

# Step 7: Group customers by Region and find average Income and Spending Score          
regional_averages = df.groupby("Region")[["Annual_Income", "Spending_Score"]].mean()    
print("\n--- Regional Average Income and Spending Score ---")  
print(regional_averages)  

# Step 8: Count number of customers in each Region  
region_counts = df["Region"].value_counts()    
print("\n--- Customer Count per Region ---")    
print(region_counts)    

# Step 9: Identify customer with maximum Spending Score  
top_spender_idx = df["Spending_Score"].idxmax()  
top_spender = df.loc[top_spender_idx]  
print("\n--- Customer with Maximum Spending Score ---")  
print(top_spender)  

# Step 10: Compute overall averages  
overall_avg_income = df["Annual_Income"].mean()    
overall_avg_spending = df["Spending_Score"].mean()  
print("\n--- Overall Averages ---")  
print(f"Average Annual Income: {overall_avg_income:.2f}")      
print(f"Average Spending Score: {overall_avg_spending:.2f}")  

## Output

<img width="590" height="497" alt="image" src="https://github.com/user-attachments/assets/9dae1b44-48c3-4840-9736-ac78fd319fe1" />
<img width="612" height="462" alt="image" src="https://github.com/user-attachments/assets/1c8b6b58-cacb-4674-a8ed-88bf7c4bde71" />
<img width="618" height="383" alt="image" src="https://github.com/user-attachments/assets/a3bd9341-ce16-4b3d-8cf8-8c9ae4d0c21e" />
<img width="623" height="497" alt="image" src="https://github.com/user-attachments/assets/f5cc64b3-b56c-4b32-b24c-4d384722fee2" />
<img width="391" height="657" alt="image" src="https://github.com/user-attachments/assets/8e2e7923-0251-4f5c-86bb-99f380bc57e3" />

## Result

The program successfully analyzes quarterly product sales using 2D NumPy arrays and Python statistical aggregation functions.
