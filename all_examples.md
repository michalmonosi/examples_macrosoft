# priklady

```python
dobs = ["1990-05-24", "1985-12-15", "2000-07-30"]
        
# function to calculate age from date of birth
def calculate_age(dob):
    from datetime import datetime, date
    dob_date = datetime.strptime(dob, "%Y-%m-%d").date()
    today = date.today()
    age = today.year - dob_date.year - ((today.month, today.day) < (dob_date.month, dob_date.day))
    return age
ages = [calculate_age(dob) for dob in dobs]
print(ages) # output the calculated ages
```

---------------------------------------------------------------------------
import os

API_KEY = os.getenv("OPENROUTER_API_KEY")
print(API_KEY)

---------------------------------------------------------------------------

#create an excel file with some user data
import pandas as pd
data = {'Name': ['Alice', 'Bob', 'Charlie', 'Michal'],
        'Age': [24, 27, 22, 32],
        'City': ['New York', 'Los Angeles', 'Chicago', 'Houston'],
        'birthdate': [2025 - age]}  
df = pd.DataFrame(data)
df.to_excel('user_data.xlsx', index=False)
print("Excel file 'user_data.xlsx' created successfully.")

---------------------------------------------------------------------------


print ("hello")
vals = [1,2,3,4,5]
mysum=0
for val in vals:
    mysum=mysum+val

my_sum=sum(vals)
print("sum of values is", my_sum )
---------------------------------------------------------------------------
import csv

occupations = set()

with open('users.csv', newline='', encoding='utf-8') as csvfile:
    reader = csv.DictReader(csvfile)
    for row in reader:
        occupation = row.get('occupation').lower()
        if occupation:
            occupations.add(occupation)

print("Unique occupations:")
for occ in sorted(occupations):
    print(occ)
---------------------------------------------------------------------------


import sys
print(sys.version)
print(sys.executable)
print(sys.path)


# get total memory in GB
import psutil
mem = psutil.virtual_memory()
print(f"Total memory: {mem.total / (1024 ** 3):.2f} GB")
---------------------------------------------------------------------------
import csv
import openpyxl

# Read CSV data
csv_file = 'users.csv'
excel_file = 'users.xlsx'

wb = openpyxl.Workbook()
ws = wb.active

with open(csv_file, newline='', encoding='utf-8') as f:
    reader = csv.reader(f)
    for row in reader:
        ws.append(row)

wb.save(excel_file)
print(f'Excel file "{excel_file}" generated successfully.')
---------------------------------------------------------------------------
import csv
import matplotlib.pyplot as plt

def generate_salary_chart():
	# Read data from users.csv
	occupations = []
	salaries = []
	with open('users.csv', newline='', encoding='utf-8') as csvfile:
		reader = csv.DictReader(csvfile)
		for row in reader:
			occupations.append(row['occupation'].strip())
			salaries.append(int(row['salary']))

	# Create bar chart
	plt.figure(figsize=(10,6))
	plt.bar(occupations, salaries, color='skyblue')
	plt.xlabel('Occupation')
	plt.ylabel('Salary')
	plt.title('Salary by Occupation')
	plt.xticks(rotation=45, ha='right')
	plt.tight_layout()

	# Save chart as PNG
	plt.savefig('salary_barchart.png')
	plt.close()

if __name__ == "__main__":
	generate_salary_chart()
---------------------------------------------------------------------------
from datetime import datetime


age = [12,15,10,20]
birthyears = [datetime.now().year  - a for a in age]

print(birthyears)

import pandas as pd
data = {'age': age, 'birthyears': birthyears}
df = pd.DataFrame(data)
df.to_excel('age_data.xlsx', index=False)   
print("Birth years are:", birthyears)
---------------------------------------------------------------------------
hodnoty = [1,2,3,4,5,6,7,8,9,10]

suma1 = 0
for hodnota in hodnoty:
    suma1 = suma + hodnota
print("Suma hodnot je:", suma)
---------------------------------------------------------------------------

---------------------------------------------------------------------------

---------------------------------------------------------------------------
