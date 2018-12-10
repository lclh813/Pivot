# Pivot
### Data 1. Original
| Date       | Farm      | Total | Apple | Apple % | Banana | Banana % | ... | Pineapple | Pineapple % |
|:---:       |:---       | ---:  | ---:  | ---:    | ---:   | ---:     |:---:| ---:      | ---:        |
| 2017/01/01 | Farm 1    | 100   | 20    | 20%     | 30     | 30%      | ... | 10        | 10%         |
| 2017/01/01 | Farm 2    | 200   | 20    | 10%     | 40     | 20%      | ... | 60        | 30%         |
| ...        | ...       | ...   | ...   | ...     | ...    | ...      | ... | ...       | ...         |
| 2018/11/30 | Farm 3-1  | 500   | 100   | 20%     | 100    | 20%      | ... | 50        | 10%         |
| 2018/11/30 | Farm 3-2  | 400   | 100   | 25%     | 40     | 10%      | ... | 20        | 5%          |
| 2018/11/30 | Farm 4    | 100   | 10    | 10%     | 40     | 40%      | ... | 5         | 5%          |

### Data 2. Drop
| Date       | Farm      | Apple | Banana | ... | Pineapple | 
|:---:       |:---       | ---:  | ---:   |:---:| ---:      |
| 2017/01/01 | Farm 1    | 20    | 30     | ... | 10        | 
| 2017/01/01 | Farm 2    | 20    | 40     | ... | 60        | 
| ...        | ...       | ...   | ...    | ... | ...       | 
| 2018/11/30 | Farm 3-1  | 100   | 100    | ... | 50        | 
| 2018/11/30 | Farm 3-2  | 100   | 40     | ... | 20        |
| 2018/11/30 | Farm 4    | 10    | 40     | ... | 5         |

### Data 3. Melt
| Date       | Farm      | Fruit_Name      | Qty |
| :---:      | ---       | :---:           | ---:| 
| 2017/01/01 | Farm 1    | Apple           | 20  | 
| 2017/01/01 | Farm 1    | Banana          | 30  |
| 2017/01/01 | Farm 1    | Pineapple       | 10  | 
| ...        | ...       | ...             | ... | 
| 2017/01/01 | Farm 2    | Apple           | 20  | 
| 2017/01/01 | Farm 2    | Banana          | 40  |
| 2017/01/01 | Farm 2    | Pineapple       | 60  | 
| ...        | ...       | ...             | ... |
| 2017/01/01 | Farm 3-1  | Apple           | 100 | 
| 2017/01/01 | Farm 3-1  | Banana          | 100 |
| 2017/01/01 | Farm 3-1  | Pineapple       | 50  | 
| ...        | ...       | ...             | ... |
| 2017/01/01 | Farm 3-2  | Apple           | 100 | 
| 2017/01/01 | Farm 3-2  | Banana          | 40  |
| 2017/01/01 | Farm 3-2  | Pineapple       | 20  | 
| ...        | ...       | ...             | ... |
| 2017/01/01 | Farm 4    | Apple           | 10  | 
| 2017/01/01 | Farm 4    | Banana          | 40  |
| 2017/01/01 | Farm 4    | Pineapple       | 5   |    

### Data 4. Melt
| 2017/01/01 | Store 1 | Banana          | APPL002       | Royal Gala         |   50 |  
| 2017/01/01 | Store 1 | Cranberry       | GRAP001       | Golden Muscat      |   30 |  
| ...        | Store 2 | Durian          | KIWI001       | Sungold Kiwifruit  |  200 |  
| 2018/08/30 | Store 3 | Fig             | APPL003       | Fuji               |  150 | 
| 2018/08/31 | Store 3 | Green Kiwi      | GRAP002       | Red Globe          |   80 |  
| 2018/08/31 | Store 3 | Sungold Kiwi    | GRAP002       | Red Globe          |   80 | 
| 2018/08/31 | Store 3 | Kiwifruit       | GRAP002       | Red Globe          |   80 | 
| 2018/08/31 | Store 3 | Grape           | GRAP002       | Red Globe          |   80 | 
| 2018/08/31 | Store 3 | Grapefruit      | GRAP002       | Red Globe          |   80 | 
| 2018/08/31 | Store 3 | Guava           | GRAP002       | Red Globe          |   80 | 
| 2018/08/31 | Store 3 | Lemon           | GRAP002       | Red Globe          |   80 | 
| 2018/08/31 | Store 3 | Yuherbau        | GRAP002       | Red Globe          |   80 | 
| 2018/08/31 | Store 3 | Lychee          | GRAP002       | Red Globe          |   80 | 
| 2018/08/31 | Store 3 | Mango           | GRAP002       | Red Globe          |   80 | 
| 2018/08/31 | Store 3 | Satsuma         | GRAP002       | Red Globe          |   80 | 
| 2018/08/31 | Store 3 | Orange          | GRAP002       | Red Globe          |   80 | 
| 2018/08/31 | Store 3 | Papaya          | GRAP002       | Red Globe          |   80 | 
| 2018/08/31 | Store 3 | Pear            | GRAP002       | Red Globe          |   80 | 
| 2018/08/31 | Store 3 | Pineapple       | GRAP002       | Red Globe          |   80 | 








