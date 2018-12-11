# Pivot Analysis
## Part 1. Objective
To create a table as follows on a ```monthly``` basis to better know ```how many``` and ```from where``` the listed fruits are purchased from 2016 to 2017.

- Table: Order History of the Fruit Shop  
- Time: Jan-2016

| Fruit_Name     | Farm 1  | Farm 2  | Farm 3  | Farm 4  |
| :---           | ---:    | ---:    | ---:    | ---:    |
| Red Delicious  | 100,000 | 110,000 | 150,000 | 70,000  |
| Royal Gala     | 90,000  | 100,000 | 80,000  | 60,000  |
| Golden Muscat  | 120,000 | 100,000 | 80,000  | 100,000 |
| KIWI           | 130,000 | 90,000  | 50,000  | 110,000 |

## Part 2. Data
### 2.1. Fruits Purchased by the Fruit Shop
| Fruit_Type_ID  | Fruit_Type | Fruit_Name_ID | Fruit_Name        | Purchase_Year |
| :---           | :---       | :---          | :---              | :---          |
| APPL           | Apple      | APPL001       | Red Delicious     | 2016          |
| APPL           | Apple      | APPL002       | Royal Gala        | 2017          |
| GRAP           | Grape      | GRAP001       | Golden Muscat     | 2016, 2017    |
| KIWI           | Kiwifruit  | KIWI001       | Sungold Kiwifruit | 2016, 2017    |

### 2.2. Original Data
- Monthly Data: There are 24 xls files in sum, one file per month with a subtotal displayed in the last row, which represents total purchase for the selected month.

| Purchase_Date | Farm                      | Total Qty | APPL | APPL % | GRAP | GRAP % | KIWI | KIWI % |
| :---:         | :---                      | ---:      | ---: | ---:   | ---: | ---:   | ---: | ---:   |       
| 2016/01/01    | Farm 1 &nbsp;&nbsp;&nbsp; | 100       | 20   | 20%    | 70   | 70%    | 10   | 10%    |
| 2016/01/01    | Farm 2 &nbsp;&nbsp;&nbsp; | 200       | 20   | 10%    | 120  | 60%    | 60   | 30%    |
| ...           | ... &nbsp;&nbsp;&nbsp;    | ...       | ...  | ...    | ...  | ...    | ...  | ...    |
| Jan-2016      | - &nbsp;&nbsp;&nbsp;      | 1,500     | 300  | 20%    | 600  | 40%    | 600  | 40%    |

| Purchase_Date | Farm      | Total Qty | APPL | APPL % | GRAP | GRAP % | KIWI   | KIWI % |
| :---:         | :---      | ---:      | ---: | ---:   | ---: | ---:   | ---:   | ---:   | 
| ...           | ...       | ...       | ...  | ...    | ...  | ...    | ...    | ...    |
| 2017/12/31    | Farm 3-1  | 500       | 100  | 20%    | 350  | 70%    | 50     | 10%    |
| 2017/12/31    | Farm 3-2  | 400       | 100  | 25%    | 280  | 70%    | 20     | 5%     |
| 2017/12/31    | Farm 4    | 100       | 10   | 10%    | 85   | 85%    | 5      | 5%     |
| Dec-2017      | -         | 3,000     | 900  | 30%    | 600  | 20%    | 1,500  | 50%    |

## Part 3. Outline
### 3.1. Drop Columns 
- Drop columns that are not needed for further analysis which include ```Total Qty``` and those containing ```%```. 
- Tool: Python ```drop```

| Purchase_Date | Farm      | APPL | GRAP | KIWI | 
|:---:          |:---       | ---: | ---: | ---: | 
| 2016/01/01    | Farm 1    | 20   | 70   | 30   |
| 2016/01/01    | Farm 2    | 20   | 120  | 60   |
| ...           | ...       | ...  | ...  | ...  |
| 2017/12/31    | Farm 3-1  | 100  | 350  | 50   | 
| 2017/12/31    | Farm 3-2  | 100  | 280  | 20   |
| 2017/12/31    | Farm 4    | 10   | 85   | 5    |

### 3.2. Reshape Dataframe
- Prepare to move ```Fruit_Type_ID``` to the row axis while ```Purchase_Date``` and ```Farm``` remain at the header. 
- Tool: Python ```melt``` 
 
| Purchase_Date | Farm      | Fruit_Type_ID | Qty |
| :---:         | ---       | :---          | ---:| 
| 2016/01/01    | Farm 1    | APPL          | 20  | 
| 2016/01/01    | Farm 1    | GRAP          | 70  |
| 2016/01/01    | Farm 1    | KIWI          | 30  | 
| ...           | ...       | ...           | ... |
| 2017/12/31    | Farm 4    | APPL          | 10  | 
| 2017/12/31    | Farm 4    | GRAP          | 85  |
| 2017/12/31    | Farm 4    | KIWI          | 5   |    

### 3.3. Pivot Analysis
#### 3.3.1. Drop Column
- Drop ```Purchase_Date``` which is of no use for pivot analysis. 
#### 3.3.2. Create Pivot Table
- Set ```Fruit_Type_ID``` at row axis and ```Farm``` at the column axis. 
#### 3.3.3. Rename Columns
- ```Apple``` purchased in 2016 is ```Red Delicious``` and ```Royal Gala``` in 2017. 
#### 3.3.4. Sum up Rows
- Add ```Farm 3-1``` and ```Farm 3-2``` together to get ```Farm3```.
- Tool: Python ```drop``` ```if``` ```pivot_table```

## Part 4. Steps
### Step 1. Preparation
[1.Import Library]
