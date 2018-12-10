# Pivot
| Index  | Fruit_Type_ID  | Fruit_Type | 
| :---:  | :---           | :---       | 
|      1 | APPL           | Apple      |
|      2 | GRAP           | Grape      |
|      3 | KIWI           | Kiwifruit  |

| Index  | Store   | Order | Fruit_Name_ID | Fruit_Name         | Qty  |  
| :---:  | ---     | :---: | ---           | ---                | ---: | 
|      1 | Store 1 |     1 | APPL001       | Red Delicious      |  100 | 
|      2 | Store 1 |     2 | APPL002       | Royal Gala         |   50 |  
|      3 | Store 1 |     3 | GRAP001       | Golden Muscat      |   30 |  
|      4 | Store 2 |     1 | KIWI001       | Sungold Kiwifruit  |  200 |  
|      5 | Store 3 |     1 | APPL003       | Fuji               |  150 | 
|      6 | Store 3 |     2 | GRAP002       | Red Globe          |   80 |  
|      7 | Store 4 |     1 | APPL002       | Royal Gala         |   20 |  
|      8 | Store 4 |     2 | APPL003       | Fuji               |   30 |  

### Data 1. Original
| Date       | Farm      | Total | Apple Qty | Apple % | Grape Qty | Grape % | ...   | Pear Qty | Pear % |
| :---:      | :---      | ---:  | :---:     | :---:   | :---:     | :---:   | :---: | :---:    | :---:  |        
| 2016/01/01 | Farm 1    | 100   | 20        | 20%     | 30        | 30%     | ...   | 10       | 10%    |
| 2016/01/01 | Farm 2    | 200   | 20        | 10%     | 40        | 20%     | ...   | 60       | 30%    |
| ...        | ...       | ...   | ...       | ...     | ...       | ...     | ...   | ...      | ...    |
| 2017/12/31 | Farm 3-1  | 500   | 100       | 20%     | 100       | 20%     | ...   | 50       | 10%    |
| 2017/12/31 | Farm 3-2  | 400   | 100       | 25%     | 40        | 10%     | ...   | 20       | 5%     |
| 2017/12/31 | Farm 4    | 100   | 10        | 10%     | 40        | 40%     | ...   | 5        | 5%     |

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









