# Pivot Analysis
## Part 1. Objective
Create a table as follows on a ***monthly*** basis to better know ***how many*** and ***from where*** the listed fruits are purchased from 2016 to 2017.

> ***Table: Order History of the Fruit Shop***   
> ***Time: January, 2016***

| Fruit_Type | Farm 1  | Farm 2  | Farm 3-1 | Farm 4  |
| :---       | ---:    | ---:    | ---:     | ---:    |
| Apple      | 100,000 | 110,000 | 150,000  | 70,000  |
| Grape      | 90,000  | 100,000 | 80,000   | 60,000  |
| Kiwifruit  | 120,000 | 100,000 | 80,000   | 100,000 |

> ***Table: Order History of the Fruit Shop***   
> ***Time: December, 2017***

| Fruit_Type | Farm 1  | Farm 2  | Farm 3-2 | Farm 4  |
| :---       | ---:    | ---:    | ---:     | ---:    |
| Apple      | 120,000 | 100,000 | 130,000  | 80,000  |
| Grape      | 70,000  | 110,000 | 80,000   | 90,000  |
| Kiwifruit  | 130,000 | 110,000 | 60,000   | 50,000  |

## Part 2. Data
### 2.1. Background Information
> ***2.1.1. Info 1. Fruits Purchased by the Fruit Shop***

| Fruit_Type_ID  | Fruit_Type | Fruit_Name_ID | Fruit_Name        | 
| :---           | :---       | :---          | :---              | 
| APPL           | Apple      | APPL001       | Red Delicious     | 
| APPL           | Apple      | APPL002       | Royal Gala        | 
| GRAP           | Grape      | GRAP001       | Golden Muscat     | 
| KIWI           | Kiwifruit  | KIWI001       | Sungold Kiwifruit | 

> ***2.1.2. Info 2. Order History***

| Supplier | Purchase_Year |
| :---     | :---          |
| Farm 1   | 2016, 2017    |
| Farm 2   | 2016, 2017    |
| Farm 3-1 | 2016          |
| Farm 3-2 | 2017          |
| Farm 4   | 2016, 2017    |

### 2.2. Original Data
- ***Monthly Data:*** There are 24 xls files in sum, one file per month with a subtotal displayed in the last row, which represents total purchase for the entire month.

| Purchase_Date | Supplier | Total<br>Qty | APPL<br>001 Qty | APPL<br>001 % | APPL<br>002 Qty | APPL<br>002 % | GRAP<br>Qty | GRAP<br>%  | KIWI<br>Qty | KIWI<br>% |
| :---:         | :---:   | :---:  | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |  
| 2016/01/01    | Farm 1  | 100    | 10    | 10%   | 10    | 10%   | 70    | 70%   | 10    | 10%   |
| 2016/01/01    | Farm 2  | 200    | 10    | 5%    | 10    | 5%    | 120   | 60%   | 60    | 30%   |
| 2016/01/01    | Farm 3  | 300    | 30    | 10%   | 60    | 20%   | 105   | 35%   | 105   | 35%   |
| 2016/01/01    | Farm 4  | 400    | 40    | 10%   | 60    | 15%   | 200   | 50%   | 100   | 25%   |
| ...           | ...     | ...    | ...   | ...   | ...   | ...   | ...   | ...   | ...   | ...   |
| Jan-2016      | -       | 15,000 | 1,500 | 10%   | 1,500 | 10%   | 6,000 | 40%   | 6,000 | 40%   |

| Purchase_Date | Supplier | Total<br>Qty | APPL<br>001 Qty | APPL<br>001 % | APPL<br>002 Qty | APPL<br>002 % | GRAP<br>Qty | GRAP<br>%  | KIWI<br>Qty | KIWI<br>% |
| :---:         | :---:   | :---:  | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ...           | ...     | ...    | ...   | ...   | ...   | ...   | ...   | ...   | ...   | ...   |
| 2017/12/31    | Farm 1  | 500    | 100   | 20%   | 200   | 40%   | 150   | 30%   | 50    | 10%   |
| 2017/12/31    | Farm 2  | 400    | 160   | 40%   | 80    | 20%   | 80    | 20%   | 80    | 20%   |
| 2017/12/31    | Farm 3  | 300    | 90    | 30%   | 30    | 10%   | 75    | 25%   | 105   | 35%   |
| 2017/12/31    | Farm 4  | 200    | 20    | 10%   | 30    | 15%   | 100   | 50%   | 50    | 25%   |
| Dec-2017      | -       | 18,000 | 9,000 | 50%   | 2,000 | 11%   | 3,000 | 17%   | 4,000 | 22%   |

## Part 3. Outline
### 3.1. Clean Dataset
### 3.1.1. Drop Columns 
- Drop columns that are not needed for further analysis which include ***Total Qty*** and those containing ***%***. 
- Tool: Python ```drop```

| Purchase_Date | Supplier  | APPL001 | APPL002 | GRAP | KIWI | 
|:---:          |:---       | ---:    | ---:    | ---: | ---: | 
| 2016/01/01    | Farm 1    | 10      | 10      | 70   | 10   |
| 2016/01/01    | Farm 2    | 10      | 10      | 120  | 60   |
| ...           | ...       | ...     | ...     | ...  | ...  |
| 2017/12/31    | Farm 3-1  | 100  | 350  | 50   | 
| 2017/12/31    | Farm 3-2  | 100  | 280  | 20   |
| 2017/12/31    | Farm 4    | 10   | 85   | 5    |

### 3.1.2. Reshape Dataframe
- Prepare to move ***Fruit_Type_ID*** to the row axis while ***Purchase_Date*** and ***Supplier*** remain at the header. 
- Tool: Python ```melt``` 
 
| Purchase_Date | Supplier  | Fruit_Type_ID | Qty |
| :---:         | ---       | :---          | ---:| 
| 2016/01/01    | Farm 1    | APPL          | 20  | 
| 2016/01/01    | Farm 1    | GRAP          | 70  |
| 2016/01/01    | Farm 1    | KIWI          | 30  | 
| ...           | ...       | ...           | ... |
| 2017/12/31    | Farm 4    | APPL          | 10  | 
| 2017/12/31    | Farm 4    | GRAP          | 85  |
| 2017/12/31    | Farm 4    | KIWI          | 5   |    

### 3.1.3. Data Type Conversion
- Records in Column ***Qty*** turned out to be string objects rather than numeric values because they are formatted with thousand separator. It is necessary to convert strings to numbers to proceed further calculation.
#### 3.1.3.1. Conversion to String
- Tool: Python ```astype```
#### 3.1.3.2. Remove Thousand Separator
- Tool: Python ```apply``` ```lambda```
#### 3.1.3.3. Conversion to Integer
- Tool: Python ```astype```
#### 3.1.4. Output Dataset for Analysis
- Tool: Python ```groupby``` ```to_csv```

### 3.2. Pivot Analysis
#### 3.2.1. Drop Column
- Drop ***Purchase_Date*** which is of no use for pivot analysis. 
#### 3.2.2. Create Pivot Table
- Set ***Fruit_Type_ID*** at row axis and ***Supplier*** at column axis. 
#### 3.2.3. Rename Columns
- ***Apple*** purchased in 2016 is ***Red Delicious*** and ***Royal Gala*** in 2017. 
#### 3.2.4. Sum up Rows
- Add ***Farm 3-1*** and ***Farm 3-2*** together to get ***Farm3***.
- Tool: Python ```drop``` ```if``` ```pivot_table```

## Part 4. Steps
### Step 1. Preparation
[1.Import Library]


