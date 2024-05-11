# CSC245-lab6

![image](https://github.com/MENGXIAOZZZZZ/CSC245-lab6/assets/166454688/ebf0aef7-dde1-4a77-8832-63e04144d041)
![image](https://github.com/MENGXIAOZZZZZ/CSC245-lab6/assets/166454688/136ac30b-016a-43c7-9030-1b5b866ccd79)
![image](https://github.com/MENGXIAOZZZZZ/CSC245-lab6/assets/166454688/3accae58-8e37-470d-a833-ff1a5558da84)
![image](https://github.com/MENGXIAOZZZZZ/CSC245-lab6/assets/166454688/6cf404aa-c716-4456-b17a-cbc45cd662f6)
![image](https://github.com/MENGXIAOZZZZZ/CSC245-lab6/assets/166454688/eb5892be-4790-4fa8-b692-ac9dda588d1e)
![image](https://github.com/MENGXIAOZZZZZ/CSC245-lab6/assets/166454688/53835eb7-a2ac-4987-a092-46d916d19462)
![image](https://github.com/MENGXIAOZZZZZ/CSC245-lab6/assets/166454688/fee7336c-1abf-409f-9f89-54219331d691)
![image](https://github.com/MENGXIAOZZZZZ/CSC245-lab6/assets/166454688/9062d3e2-2ac7-433d-a628-79918a7ac880)
![image](https://github.com/MENGXIAOZZZZZ/CSC245-lab6/assets/166454688/890f540e-6bb8-4aa4-aa0c-c79ed549ed4d)
![image](https://github.com/MENGXIAOZZZZZ/CSC245-lab6/assets/166454688/1dfd7c81-d2c3-4051-aec6-c942b1aab415)
![image](https://github.com/MENGXIAOZZZZZ/CSC245-lab6/assets/166454688/30086c7e-894e-48c8-a452-f3dcee7ed5db)
![image](https://github.com/MENGXIAOZZZZZ/CSC245-lab6/assets/166454688/a0dc5163-6913-4441-aa08-8f0e3c773df3)
![image](https://github.com/MENGXIAOZZZZZ/CSC245-lab6/assets/166454688/436a4f1a-6aff-428f-92db-d18b1887a7bf)

# Exercise 1: Read Total profit of all months and show it using a line plot
month = data['month_number']
profit = data['total_profit']
plt.figure(figsize=(10, 6))
plt.plot(month, profit)
plt.title('Monthly Earnings')
plt.xlabel('Month')
plt.ylabel('Earnings')
plt.grid(True)
plt.tight_layout()
plt.savefig('monthly_earnings.png')
plt.show()


# Exercise 2: Get total profit of all months and show line plot with the following Style properties
import matplotlib.pyplot as plt

month = data['month_number']
profit = data['total_profit']

plt.figure(figsize=(10, 6))
plt.plot(month, profit, linestyle='--', color='red', marker='o', markerfacecolor='black', linewidth=3, label='profit data of last year')
plt.title('Company Sales Data of Last Year')
plt.xlabel('Month Number')
plt.ylabel('Sold Units Number')
plt.legend(loc='lower right')
plt.grid(True)
plt.tight_layout()
plt.savefig('monthly_sales_data.png')
plt.show()


# Exercise 3: Read all product sales data and show it using a multiline plot
import matplotlib.pyplot as plt

df = data  # Assuming data is loaded into a DataFrame named df

plt.figure(figsize=(10, 8))
plt.plot(df['month_number'], df['facecream'], label='Face Cream', marker='o')
plt.plot(df['month_number'], df['facewash'], label='Face Wash', marker='o')
plt.plot(df['month_number'], df['toothpaste'], label='Toothpaste', marker='o')
plt.plot(df['month_number'], df['bathingsoap'], label='Bathing Soap', marker='o')
plt.plot(df['month_number'], df['shampoo'], label='Shampoo', marker='o')
plt.plot(df['month_number'], df['moisturizer'], label='Moisturizer', marker='o')

plt.legend()
plt.title('Sales Data')
plt.xlabel('Month Number')
plt.ylabel('Sales Units')
plt.savefig('sale_data')
plt.show()


# Exercise 4: Read toothpaste sales data of each month and show it using a scatter plot
import matplotlib.pyplot as plt

# Assuming 'df' is your DataFrame and it has columns 'month_number' and 'toothpaste'
plt.figure(figsize=(10, 6))
plt.scatter(df['month_number'], df['toothpaste'], color='blue', label='Toothpaste Sales Data')

plt.grid(True, linestyle='--')
plt.legend()
plt.title('Toothpaste Sales Data')
plt.xlabel('Month Number')
plt.ylabel('Number of Units Sold')
plt.savefig('toothpaste_sales_data')
plt.show()




# Exercise 5: Read face cream and facewash product sales data and show it using the bar chart
import matplotlib.pyplot as plt
import numpy as np

# Assuming 'df' is your DataFrame
month_number = df['month_number'].tolist()

barWidth = 0.3
r1 = np.arange(len(month_number))
r2 = [x + barWidth for x in r1]

plt.figure(figsize=(12, 8))
plt.bar(r1, df['facecream'], color='blue', width=barWidth, edgecolor='grey', label='Face Cream')
plt.bar(r2, df['facewash'], color='orange', width=barWidth, edgecolor='grey', label='Face Wash')

plt.legend()
plt.title('Sales Data', fontweight='bold')
plt.xlabel('Month Number', fontweight='bold')
plt.ylabel('Sales Units', fontweight='bold')
plt.xticks([r + barWidth for r in range(len(month_number))], month_number)
plt.savefig('facewash_and_facecream_sales_data')
plt.show()



# Exercise 6: Read sales data of bathing soap of all months and show it using a bar chart. Save this plot to your hard disk
import matplotlib.pyplot as plt

# Assuming 'df' is your DataFrame
plt.figure(figsize=(10, 6))
plt.bar(df['month_number'], df['bathingsoap'], color='blue', label='Bathing Soap Sales Data')

plt.legend()
plt.title('Bathing Soap Sales Data')
plt.xlabel('Month Number')
plt.ylabel('Sales Units')
plt.grid(True, which='both', linestyle='--', linewidth=0.5)
plt.savefig('bathing_soap_sales_data_with_grid.png')
plt.show()


# Exercise 7: Read the total profit of each month and show it using the histogram to see the most common profit ranges
import matplotlib.pyplot as plt

# Assuming 'df' is your DataFrame and it has a column 'total_profit'
plt.figure(figsize=(10, 6))
plt.hist(df['total_profit'], bins=10, color='skyblue', edgecolor='black')

plt.title('Distribution of Total Profit')
plt.xlabel('Profit Range')
plt.ylabel('Frequency')
plt.grid(True, which='both', linestyle='--', linewidth=0.5)
plt.savefig('profit_data')
plt.show()


# Exercise 8: Calculate total sale data for last year for each product and show it using a Pie chart
import matplotlib.pyplot as plt

# Assuming df is your DataFrame
total_sales = df[['facecream', 'facewash', 'toothpaste', 'bathingsoap', 'shampoo', 'moisturizer']].sum()

labels = total_sales.index
sizes = total_sales.values
colors = ['gold', 'yellowgreen', 'lightcoral', 'lightskyblue', 'lightgreen', 'pink']
explode = (0.1, 0, 0, 0, 0, 0)  # only "explode" the 1st slice (i.e., 'facecream')

plt.figure(figsize=(8, 8))
plt.pie(sizes, explode=explode, labels=labels, colors=colors, autopct='%1.1f%%', shadow=True, startangle=140)

plt.title('Sales Data for Last Year - Percentage of Each Product Sold')
plt.savefig('pie_data')
plt.show()


# Exercise 9: Read Bathing soap facewash of all months and display it using the Subplot
import matplotlib.pyplot as plt

# Assuming 'df' is your DataFrame containing 'month_number', 'bathingsoap', and 'facewash' columns
plt.figure(figsize=(10, 8))

# Subplot 1: Sales Data of Bathing Soap
plt.subplot(2, 1, 1)  # (rows, columns, panel number)
plt.plot(df['month_number'], df['bathingsoap'], color='blue', marker='o')
plt.title('Sales Data of Bathing Soap')
plt.xlabel('Month Number')
plt.ylabel('Sales Units')

# Subplot 2: Sales Data of Facewash
plt.subplot(2, 1, 2)
plt.plot(df['month_number'], df['facewash'], color='orange', marker='o')
plt.title('Sales Data of Facewash')
plt.xlabel('Month Number')
plt.ylabel('Sales Units')

plt.tight_layout()
plt.savefig('double')
plt.show()



# Exercise Question 10: Read all product sales data and show it using the stack plot
import matplotlib.pyplot as plt

# Assuming 'df' is your DataFrame containing the data
months = df['month_number']
facecream_sales = df['facecream']
facewash_sales = df['facewash']
toothpaste_sales = df['toothpaste']
bathingsoap_sales = df['bathingsoap']
shampoo_sales = df['shampoo']
moisturizer_sales = df['moisturizer']

plt.stackplot(months, facecream_sales, facewash_sales, toothpaste_sales, bathingsoap_sales, shampoo_sales, moisturizer_sales,
              labels=['Facecream', 'Facewash', 'Toothpaste', 'Bathingsoap', 'Shampoo', 'Moisturizer'],
              colors=['#ff9999', '#66b3ff', '#99ff99', '#ffcc99', '#c2c2f0', '#ffb3e6'])

plt.legend(loc='upper left')
plt.title('Monthly Sales Data of All Products')
plt.xlabel('Month Number')
plt.ylabel('Sales Units')
plt.savefig('Monthly_sales_data')
plt.show()
