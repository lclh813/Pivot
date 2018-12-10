# Pivot Analysis
## Part 1. Objective
To create a table as follows on a ```monthly``` basis to better know ```how many``` and ```from where``` the listed fruits are purchased from 2016 to 2017.

- Table: Order History of the Fruit Shop  
- Time: Jan-2016

| Fruit_Name     | Farm 1 | Farm 2 | Farm 3 | Farm 4 |
| :---           | ---:   | ---:   | ---:   | ---:   |
| Red Delicious  | 10,000 | 11,000 | 15,000 | 7,000  |
| Royal Gala     | 9,000  | 10,000 | 8,000  | 6,000  |
| Golden Muscat  | 12,000 | 10,000 | 8,000  | 10,000 |
| KIWI           | 13,000 | 9,000  | 5,000  | 11,000 |

## Part 2. Data
### 2.1. Fruits Purchased by the Fruit Shop
| Fruit_Type_ID  | Fruit_Type | Fruit_Name_ID | Fruit_Name        | Purchase Year |
| :---           | :---       | :---          | :---              | :---          |
| APPL           | Apple      | APPL001       | Red Delicious     | 2016          |
| APPL           | Apple      | APPL002       | Royal Gala        | 2017          |
| GRAP           | Grape      | GRAP001       | Golden Muscat     | 2016, 2017    |
| KIWI           | Kiwifruit  | KIWI001       | Sungold Kiwifruit | 2016, 2017    |

### 2.2. Original Data
| Purchase Date | Farm      | Total Qty | APPL001 | APPL001 % | GRAP | GRAP % | KIWI | KIWI % |
| :---:         | :---      | ---:      | ---:    | ---:      | ---: | ---:   | ---: | ---:   |       
| 2016/01/01    | Farm 1&nbsp;&nbsp;&nbsp;| 100       | 20      | 20%       | 70   | 70%    | 10   | 10%    |
| 2016/01/01    | Farm 2&nbsp;&nbsp;&nbsp;| 200       | 20      | 10%       | 120  | 60%    | 60   | 30%    |
| ...           | ...       | ...       | ..      | ...       | ...  | ...    | ...  | ...    |

| Purchase Date | Farm      | Total Qty | APPL002 | APPL002 % | GRAP | GRAP % | KIWI | KIWI % |
| :---:         | :---      | ---:      | ---:    | ---:      | ---: | ---:   | ---: | ---:   | 
| ...           | ...       | ...       | ..      | ...       | ...  | ...    | ...  | ...    |
| 2017/12/31    | Farm 3-1  | 500       | 100     | 20%       | 350  | 70%    | 50   | 10%    |
| 2017/12/31    | Farm 3-2  | 400       | 100     | 25%       | 280  | 70%    | 20   | 5%     |
| 2017/12/31    | Farm 4    | 100       | 10      | 10%       | 85   | 85%    | 5    | 5%     |

## Part 3. Outline
### 3.1. Drop Columns 
- Drop columns that are not needed for further analysis which include ```Total Qty``` and those containing ```%```. 
- Tool: Python ```drop```

| Purchase Date | Farm      | APPL001 | GRAP | KIWI | 
|:---:          |:---       | ---:    | ---: | ---: | 
| 2016/01/01    | Farm 1    | 20      | 70   | 30   |
| 2016/01/01    | Farm 2    | 20      | 120  | 60   |

| 2017/12/31    | Farm 3-1  | 100  | 350  | 50   | 
| 2017/12/31    | Farm 3-2  | 100  | 280  | 20   |
| 2017/12/31    | Farm 4    | 10   | 85   | 5    |

### 3.2. Reshape Dataframe
- Prepare to move ```Fruit_Type_ID``` to the row axis while ```Purchase Date``` and ```Farm``` remain at the header. 
- Tool: Python ```melt``` 
 
| Purchase Date | Farm      | Fruit_Type_ID | Qty |
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
- Drop ```Purchase Date``` which is of no use for pivot analysis. 
#### 3.3.2. Create Pivot Table
- Set ```Fruit_Type_ID``` at row axis and ```Farm``` at the column axis. 
#### 3.3.3. Rename Columns
- ```Apple``` purchased in 2016 is ```Red Delicious``` and ```Royal Gala``` in 2017. 
#### 3.3.4. Sum up Rows
- Add ```Farm 3-1``` and ```Farm 3-2``` together to get ```Farm3```.
- Tool: Python ```drop``` ```if``` ```pivot_table```
