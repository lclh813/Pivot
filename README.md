# Pivot
### Fruits
| Fruit_Type_ID  | Fruit_Type | Fruit_Name_ID | Fruit_Name        | Purchase Year |
| :---           | :---       | :---          | :---              | :---          |
| APPL           | Apple      | APPL001       | Red Delicious     | 2016          |
| APPL           | Apple      | APPL002       | Royal Gala        | 2016          |
| GRAP           | Grape      | GRAP001       | Golden Muscat     | 2016, 2017    |
| KIWI           | Kiwifruit  | KIWI001       | Sungold Kiwifruit | 2016, 2017    |

### Data 1. Original
| Date       | Farm      | Total Qty | APPL Qty | APPL % | GRAP Qty | GRAP % | KIWI Qty    | KIWI %    |
| :---:      | :---      | :---:     | :---:    | :---:  | :---:    | :---:  | :---:       | :---:     |       
| 2016/01/01 | Farm 1    | 100       | 20       | 20%    | 70       | 70%    | 10          | 10%       |
| 2016/01/01 | Farm 2    | 200       | 20       | 10%    | 120      | 60%    | 60          | 30%       |
| 2017/12/31 | Farm 3-1  | 500       | 100      | 20%    | 350      | 70%    | 50          | 10%       |
| 2017/12/31 | Farm 3-2  | 400       | 100      | 25%    | 280      | 70%    | 20          | 5%        |
| 2017/12/31 | Farm 4    | 100       | 10       | 10%    | 85       | 85%    | 5           | 5%        |

### Data 2. Drop
| Date       | Farm      | APPL | GRAP | KIWI | 
|:---:       |:---       | ---: | ---: | ---: | 
| 2017/01/01 | Farm 1    | 20   | 70   | 30   |
| 2017/01/01 | Farm 2    | 20   | 120  | 60   | 
| 2018/11/30 | Farm 3-1  | 100  | 350  | 50   | 
| 2018/11/30 | Farm 3-2  | 100  | 280  | 20   |
| 2018/11/30 | Farm 4    | 10   | 85   | 5    |

### Data 3. Melt + Groupby
| Date       | Farm      | Fruit_Name | Qty |
| :---:      | ---       | :---       | ---:| 
| 2017/01/01 | Farm 1    | Apple      | 20  | 
| 2017/01/01 | Farm 1    | Banana     | 30  |
| 2017/01/01 | Farm 1    | Pear       | 10  | 
| ...        | ...       | ...        | ... |
| 2017/01/01 | Farm 4    | Apple      | 10  | 
| 2017/01/01 | Farm 4    | Banana     | 40  |
| 2017/01/01 | Farm 4    | Pear       | 5   |    

### Data 4. Melt









