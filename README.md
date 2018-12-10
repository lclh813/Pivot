# Pivot
### Fruits
| Fruit_Type_ID  | Fruit_Type | Fruit_Name_ID | Fruit_Name        | 
| :---           | :---       | :---          | :---              |
| APPL           | Apple      | APPL001       | Red Delicious     |
| APPL           | Apple      | APPL002       | Royal Gala        |
| APPL           | Apple      | APPL003       | Fuji              |
| GRAP           | Grape      | GRAP001       | Golden Muscat     |
| GRAP           | Grape      | GRAP002       | Red Globe         |
| KIWI           | Kiwifruit  | KIWI001       | Sungold Kiwifruit |

### Data 1. Original
| Date       | Farm      | Total | APPL001 Qty | APPL001 % | APPL002 Qty | APPL002 % | ...   | KIWI001 Qty | KIWI001 % |
| :---:      | :---      | ---:  | :---:       | :---:     | :---:       | :---:     | :---: | :---:       | :---:     |        
| 2016/01/01 | Farm 1    | 100   | 20          | 20%       | 30          | 30%       | ...   | 10          | 10%       |
| 2016/01/01 | Farm 2    | 200   | 20          | 10%       | 40          | 20%       | ...   | 60          | 30%       |
| ...        | ...       | ...   | ...         | ...       | ...         | ...       | ...   | ...         | ...       |
| 2017/12/31 | Farm 3-1  | 500   | 100         | 20%       | 100         | 20%       | ...   | 50          | 10%       |
| 2017/12/31 | Farm 3-2  | 400   | 100         | 25%       | 40          | 10%       | ...   | 20          | 5%        |
| 2017/12/31 | Farm 4    | 100   | 10          | 10%       | 40          | 40%       | ...   | 5           | 5%        |

### Data 2. Drop
| Date       | Farm      | Apple | Banana | ... | Pear | 
|:---:       |:---       | ---:  | ---:   |:---:| ---: |
| 2017/01/01 | Farm 1    | 20    | 30     | ... | 10   | 
| 2017/01/01 | Farm 2    | 20    | 40     | ... | 60   | 
| ...        | ...       | ...   | ...    | ... | ...  | 
| 2018/11/30 | Farm 3-1  | 100   | 100    | ... | 50   | 
| 2018/11/30 | Farm 3-2  | 100   | 40     | ... | 20   |
| 2018/11/30 | Farm 4    | 10    | 40     | ... | 5    |

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









