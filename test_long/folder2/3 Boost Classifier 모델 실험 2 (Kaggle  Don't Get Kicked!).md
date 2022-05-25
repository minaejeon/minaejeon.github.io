---
layout: single
title:  "jupyter notebook 변환하기!"
categories: coding
tag: [python, blog, jekyll]
toc: true
author_profile: false
---

<head>
  <style>
    table.dataframe {
      white-space: normal;
      width: 100%;
      height: 240px;
      display: block;
      overflow: auto;
      font-family: Arial, sans-serif;
      font-size: 0.9rem;
      line-height: 20px;
      text-align: center;
      border: 0px !important;
    }

    table.dataframe th {
      text-align: center;
      font-weight: bold;
      padding: 8px;
    }

    table.dataframe td {
      text-align: center;
      padding: 8px;
    }

    table.dataframe tr:hover {
      background: #b8d1f3; 
    }

    .output_prompt {
      overflow: auto;
      font-size: 0.9rem;
      line-height: 1.45;
      border-radius: 0.3rem;
      -webkit-overflow-scrolling: touch;
      padding: 0.8rem;
      margin-top: 0;
      margin-bottom: 15px;
      font: 1rem Consolas, "Liberation Mono", Menlo, Courier, monospace;
      color: $code-text-color;
      border: solid 1px $border-color;
      border-radius: 0.3rem;
      word-break: normal;
      white-space: pre;
    }

  .dataframe tbody tr th:only-of-type {
      vertical-align: middle;
  }

  .dataframe tbody tr th {
      vertical-align: top;
  }

  .dataframe thead th {
      text-align: center !important;
      padding: 8px;
  }

  .page__content p {
      margin: 0 0 0px !important;
  }

  .page__content p > strong {
    font-size: 0.8rem !important;
  }

  </style>
</head>



```python
# This Python 3 environment comes with many helpful analytics libraries installed
# It is defined by the kaggle/python Docker image: https://github.com/kaggle/docker-python
# For example, here's several helpful packages to load

import numpy as np # linear algebra
import pandas as pd # data processing, CSV file I/O (e.g. pd.read_csv)

# Input data files are available in the read-only "../input/" directory
# For example, running this (by clicking run or pressing Shift+Enter) will list all files under the input directory

import os
for dirname, _, filenames in os.walk('/kaggle/input'):
    for filename in filenames:
        print(os.path.join(dirname, filename))

# You can write up to 20GB to the current directory (/kaggle/working/) that gets preserved as output when you create a version using "Save & Run All" 
# You can also write temporary files to /kaggle/temp/, but they won't be saved outside of the current session
```

<pre>
/kaggle/input/DontGetKicked/example_entry.csv
/kaggle/input/DontGetKicked/training.zip
/kaggle/input/DontGetKicked/Carvana_Data_Dictionary.txt
/kaggle/input/DontGetKicked/test.zip
/kaggle/input/DontGetKicked/training.csv
/kaggle/input/DontGetKicked/test.csv
</pre>

```python
train=pd.read_csv("/kaggle/input/DontGetKicked/training.csv")
test=pd.read_csv("/kaggle/input/DontGetKicked/test.csv")
pd.options.display.max_columns=99
display(train,test)
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>RefId</th>
      <th>IsBadBuy</th>
      <th>PurchDate</th>
      <th>Auction</th>
      <th>VehYear</th>
      <th>VehicleAge</th>
      <th>Make</th>
      <th>Model</th>
      <th>Trim</th>
      <th>SubModel</th>
      <th>Color</th>
      <th>Transmission</th>
      <th>WheelTypeID</th>
      <th>WheelType</th>
      <th>VehOdo</th>
      <th>Nationality</th>
      <th>Size</th>
      <th>TopThreeAmericanName</th>
      <th>MMRAcquisitionAuctionAveragePrice</th>
      <th>MMRAcquisitionAuctionCleanPrice</th>
      <th>MMRAcquisitionRetailAveragePrice</th>
      <th>MMRAcquisitonRetailCleanPrice</th>
      <th>MMRCurrentAuctionAveragePrice</th>
      <th>MMRCurrentAuctionCleanPrice</th>
      <th>MMRCurrentRetailAveragePrice</th>
      <th>MMRCurrentRetailCleanPrice</th>
      <th>PRIMEUNIT</th>
      <th>AUCGUART</th>
      <th>BYRNO</th>
      <th>VNZIP1</th>
      <th>VNST</th>
      <th>VehBCost</th>
      <th>IsOnlineSale</th>
      <th>WarrantyCost</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
      <td>12/7/2009</td>
      <td>ADESA</td>
      <td>2006</td>
      <td>3</td>
      <td>MAZDA</td>
      <td>MAZDA3</td>
      <td>i</td>
      <td>4D SEDAN I</td>
      <td>RED</td>
      <td>AUTO</td>
      <td>1.0</td>
      <td>Alloy</td>
      <td>89046</td>
      <td>OTHER ASIAN</td>
      <td>MEDIUM</td>
      <td>OTHER</td>
      <td>8155.0</td>
      <td>9829.0</td>
      <td>11636.0</td>
      <td>13600.0</td>
      <td>7451.0</td>
      <td>8552.0</td>
      <td>11597.0</td>
      <td>12409.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>21973</td>
      <td>33619</td>
      <td>FL</td>
      <td>7100.0</td>
      <td>0</td>
      <td>1113</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>0</td>
      <td>12/7/2009</td>
      <td>ADESA</td>
      <td>2004</td>
      <td>5</td>
      <td>DODGE</td>
      <td>1500 RAM PICKUP 2WD</td>
      <td>ST</td>
      <td>QUAD CAB 4.7L SLT</td>
      <td>WHITE</td>
      <td>AUTO</td>
      <td>1.0</td>
      <td>Alloy</td>
      <td>93593</td>
      <td>AMERICAN</td>
      <td>LARGE TRUCK</td>
      <td>CHRYSLER</td>
      <td>6854.0</td>
      <td>8383.0</td>
      <td>10897.0</td>
      <td>12572.0</td>
      <td>7456.0</td>
      <td>9222.0</td>
      <td>11374.0</td>
      <td>12791.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>19638</td>
      <td>33619</td>
      <td>FL</td>
      <td>7600.0</td>
      <td>0</td>
      <td>1053</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>0</td>
      <td>12/7/2009</td>
      <td>ADESA</td>
      <td>2005</td>
      <td>4</td>
      <td>DODGE</td>
      <td>STRATUS V6</td>
      <td>SXT</td>
      <td>4D SEDAN SXT FFV</td>
      <td>MAROON</td>
      <td>AUTO</td>
      <td>2.0</td>
      <td>Covers</td>
      <td>73807</td>
      <td>AMERICAN</td>
      <td>MEDIUM</td>
      <td>CHRYSLER</td>
      <td>3202.0</td>
      <td>4760.0</td>
      <td>6943.0</td>
      <td>8457.0</td>
      <td>4035.0</td>
      <td>5557.0</td>
      <td>7146.0</td>
      <td>8702.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>19638</td>
      <td>33619</td>
      <td>FL</td>
      <td>4900.0</td>
      <td>0</td>
      <td>1389</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>0</td>
      <td>12/7/2009</td>
      <td>ADESA</td>
      <td>2004</td>
      <td>5</td>
      <td>DODGE</td>
      <td>NEON</td>
      <td>SXT</td>
      <td>4D SEDAN</td>
      <td>SILVER</td>
      <td>AUTO</td>
      <td>1.0</td>
      <td>Alloy</td>
      <td>65617</td>
      <td>AMERICAN</td>
      <td>COMPACT</td>
      <td>CHRYSLER</td>
      <td>1893.0</td>
      <td>2675.0</td>
      <td>4658.0</td>
      <td>5690.0</td>
      <td>1844.0</td>
      <td>2646.0</td>
      <td>4375.0</td>
      <td>5518.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>19638</td>
      <td>33619</td>
      <td>FL</td>
      <td>4100.0</td>
      <td>0</td>
      <td>630</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>0</td>
      <td>12/7/2009</td>
      <td>ADESA</td>
      <td>2005</td>
      <td>4</td>
      <td>FORD</td>
      <td>FOCUS</td>
      <td>ZX3</td>
      <td>2D COUPE ZX3</td>
      <td>SILVER</td>
      <td>MANUAL</td>
      <td>2.0</td>
      <td>Covers</td>
      <td>69367</td>
      <td>AMERICAN</td>
      <td>COMPACT</td>
      <td>FORD</td>
      <td>3913.0</td>
      <td>5054.0</td>
      <td>7723.0</td>
      <td>8707.0</td>
      <td>3247.0</td>
      <td>4384.0</td>
      <td>6739.0</td>
      <td>7911.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>19638</td>
      <td>33619</td>
      <td>FL</td>
      <td>4000.0</td>
      <td>0</td>
      <td>1020</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>72978</th>
      <td>73010</td>
      <td>1</td>
      <td>12/2/2009</td>
      <td>ADESA</td>
      <td>2001</td>
      <td>8</td>
      <td>MERCURY</td>
      <td>SABLE</td>
      <td>GS</td>
      <td>4D SEDAN GS</td>
      <td>BLACK</td>
      <td>AUTO</td>
      <td>1.0</td>
      <td>Alloy</td>
      <td>45234</td>
      <td>AMERICAN</td>
      <td>MEDIUM</td>
      <td>FORD</td>
      <td>1996.0</td>
      <td>2993.0</td>
      <td>2656.0</td>
      <td>3732.0</td>
      <td>2190.0</td>
      <td>3055.0</td>
      <td>4836.0</td>
      <td>5937.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18111</td>
      <td>30212</td>
      <td>GA</td>
      <td>4200.0</td>
      <td>0</td>
      <td>993</td>
    </tr>
    <tr>
      <th>72979</th>
      <td>73011</td>
      <td>0</td>
      <td>12/2/2009</td>
      <td>ADESA</td>
      <td>2007</td>
      <td>2</td>
      <td>CHEVROLET</td>
      <td>MALIBU 4C</td>
      <td>LS</td>
      <td>4D SEDAN LS</td>
      <td>SILVER</td>
      <td>AUTO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>71759</td>
      <td>AMERICAN</td>
      <td>MEDIUM</td>
      <td>GM</td>
      <td>6418.0</td>
      <td>7325.0</td>
      <td>7431.0</td>
      <td>8411.0</td>
      <td>6785.0</td>
      <td>8132.0</td>
      <td>10151.0</td>
      <td>11652.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18881</td>
      <td>30212</td>
      <td>GA</td>
      <td>6200.0</td>
      <td>0</td>
      <td>1038</td>
    </tr>
    <tr>
      <th>72980</th>
      <td>73012</td>
      <td>0</td>
      <td>12/2/2009</td>
      <td>ADESA</td>
      <td>2005</td>
      <td>4</td>
      <td>JEEP</td>
      <td>GRAND CHEROKEE 2WD V</td>
      <td>Lar</td>
      <td>4D WAGON LAREDO</td>
      <td>SILVER</td>
      <td>AUTO</td>
      <td>1.0</td>
      <td>Alloy</td>
      <td>88500</td>
      <td>AMERICAN</td>
      <td>MEDIUM SUV</td>
      <td>CHRYSLER</td>
      <td>8545.0</td>
      <td>9959.0</td>
      <td>9729.0</td>
      <td>11256.0</td>
      <td>8375.0</td>
      <td>9802.0</td>
      <td>11831.0</td>
      <td>14402.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18111</td>
      <td>30212</td>
      <td>GA</td>
      <td>8200.0</td>
      <td>0</td>
      <td>1893</td>
    </tr>
    <tr>
      <th>72981</th>
      <td>73013</td>
      <td>0</td>
      <td>12/2/2009</td>
      <td>ADESA</td>
      <td>2006</td>
      <td>3</td>
      <td>CHEVROLET</td>
      <td>IMPALA</td>
      <td>LS</td>
      <td>4D SEDAN LS</td>
      <td>WHITE</td>
      <td>AUTO</td>
      <td>1.0</td>
      <td>Alloy</td>
      <td>79554</td>
      <td>AMERICAN</td>
      <td>LARGE</td>
      <td>GM</td>
      <td>6420.0</td>
      <td>7604.0</td>
      <td>7434.0</td>
      <td>8712.0</td>
      <td>6590.0</td>
      <td>7684.0</td>
      <td>10099.0</td>
      <td>11228.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18881</td>
      <td>30212</td>
      <td>GA</td>
      <td>7000.0</td>
      <td>0</td>
      <td>1974</td>
    </tr>
    <tr>
      <th>72982</th>
      <td>73014</td>
      <td>0</td>
      <td>12/2/2009</td>
      <td>ADESA</td>
      <td>2006</td>
      <td>3</td>
      <td>MAZDA</td>
      <td>MAZDA6</td>
      <td>s</td>
      <td>4D SEDAN S</td>
      <td>SILVER</td>
      <td>AUTO</td>
      <td>1.0</td>
      <td>Alloy</td>
      <td>66855</td>
      <td>OTHER ASIAN</td>
      <td>MEDIUM</td>
      <td>OTHER</td>
      <td>7535.0</td>
      <td>8771.0</td>
      <td>8638.0</td>
      <td>9973.0</td>
      <td>7730.0</td>
      <td>9102.0</td>
      <td>11954.0</td>
      <td>13246.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18111</td>
      <td>30212</td>
      <td>GA</td>
      <td>8000.0</td>
      <td>0</td>
      <td>1313</td>
    </tr>
  </tbody>
</table>
<p>72983 rows × 34 columns</p>
</div>


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>RefId</th>
      <th>PurchDate</th>
      <th>Auction</th>
      <th>VehYear</th>
      <th>VehicleAge</th>
      <th>Make</th>
      <th>Model</th>
      <th>Trim</th>
      <th>SubModel</th>
      <th>Color</th>
      <th>Transmission</th>
      <th>WheelTypeID</th>
      <th>WheelType</th>
      <th>VehOdo</th>
      <th>Nationality</th>
      <th>Size</th>
      <th>TopThreeAmericanName</th>
      <th>MMRAcquisitionAuctionAveragePrice</th>
      <th>MMRAcquisitionAuctionCleanPrice</th>
      <th>MMRAcquisitionRetailAveragePrice</th>
      <th>MMRAcquisitonRetailCleanPrice</th>
      <th>MMRCurrentAuctionAveragePrice</th>
      <th>MMRCurrentAuctionCleanPrice</th>
      <th>MMRCurrentRetailAveragePrice</th>
      <th>MMRCurrentRetailCleanPrice</th>
      <th>PRIMEUNIT</th>
      <th>AUCGUART</th>
      <th>BYRNO</th>
      <th>VNZIP1</th>
      <th>VNST</th>
      <th>VehBCost</th>
      <th>IsOnlineSale</th>
      <th>WarrantyCost</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>73015</td>
      <td>12/2/2009</td>
      <td>ADESA</td>
      <td>2005</td>
      <td>4</td>
      <td>PONTIAC</td>
      <td>GRAND PRIX</td>
      <td>Bas</td>
      <td>4D SEDAN</td>
      <td>SILVER</td>
      <td>AUTO</td>
      <td>1.0</td>
      <td>Alloy</td>
      <td>85377</td>
      <td>AMERICAN</td>
      <td>LARGE</td>
      <td>GM</td>
      <td>5032.0</td>
      <td>6386.0</td>
      <td>5935.0</td>
      <td>7397.0</td>
      <td>4905.0</td>
      <td>6181.0</td>
      <td>8557.0</td>
      <td>9752.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18881</td>
      <td>30212</td>
      <td>GA</td>
      <td>6500.0</td>
      <td>0</td>
      <td>2152</td>
    </tr>
    <tr>
      <th>1</th>
      <td>73016</td>
      <td>12/2/2009</td>
      <td>ADESA</td>
      <td>2005</td>
      <td>4</td>
      <td>CHEVROLET</td>
      <td>MALIBU V6</td>
      <td>LS</td>
      <td>4D SEDAN LS</td>
      <td>SILVER</td>
      <td>AUTO</td>
      <td>1.0</td>
      <td>Alloy</td>
      <td>61873</td>
      <td>AMERICAN</td>
      <td>MEDIUM</td>
      <td>GM</td>
      <td>4502.0</td>
      <td>5685.0</td>
      <td>5362.0</td>
      <td>6640.0</td>
      <td>4645.0</td>
      <td>5710.0</td>
      <td>7562.0</td>
      <td>9296.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18111</td>
      <td>30212</td>
      <td>GA</td>
      <td>6300.0</td>
      <td>0</td>
      <td>1118</td>
    </tr>
    <tr>
      <th>2</th>
      <td>73017</td>
      <td>12/2/2009</td>
      <td>ADESA</td>
      <td>2006</td>
      <td>3</td>
      <td>DODGE</td>
      <td>DURANGO 2WD V8</td>
      <td>Adv</td>
      <td>4D SUV 4.7L ADVENTURER</td>
      <td>SILVER</td>
      <td>AUTO</td>
      <td>1.0</td>
      <td>Alloy</td>
      <td>69283</td>
      <td>AMERICAN</td>
      <td>MEDIUM SUV</td>
      <td>CHRYSLER</td>
      <td>10244.0</td>
      <td>13041.0</td>
      <td>11564.0</td>
      <td>14584.0</td>
      <td>10883.0</td>
      <td>12166.0</td>
      <td>15340.0</td>
      <td>16512.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18111</td>
      <td>30212</td>
      <td>GA</td>
      <td>9700.0</td>
      <td>0</td>
      <td>1215</td>
    </tr>
    <tr>
      <th>3</th>
      <td>73018</td>
      <td>12/2/2009</td>
      <td>ADESA</td>
      <td>2002</td>
      <td>7</td>
      <td>SATURN</td>
      <td>L SERIES</td>
      <td>L20</td>
      <td>4D SEDAN L200</td>
      <td>GOLD</td>
      <td>AUTO</td>
      <td>1.0</td>
      <td>Alloy</td>
      <td>87889</td>
      <td>AMERICAN</td>
      <td>MEDIUM</td>
      <td>GM</td>
      <td>2558.0</td>
      <td>3542.0</td>
      <td>3263.0</td>
      <td>4325.0</td>
      <td>2928.0</td>
      <td>3607.0</td>
      <td>5725.0</td>
      <td>6398.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18881</td>
      <td>30212</td>
      <td>GA</td>
      <td>4150.0</td>
      <td>0</td>
      <td>1933</td>
    </tr>
    <tr>
      <th>4</th>
      <td>73019</td>
      <td>12/2/2009</td>
      <td>ADESA</td>
      <td>2007</td>
      <td>2</td>
      <td>HYUNDAI</td>
      <td>ACCENT</td>
      <td>GS</td>
      <td>2D COUPE GS</td>
      <td>BLUE</td>
      <td>AUTO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>73432</td>
      <td>OTHER ASIAN</td>
      <td>COMPACT</td>
      <td>OTHER</td>
      <td>5013.0</td>
      <td>6343.0</td>
      <td>5914.0</td>
      <td>7350.0</td>
      <td>5013.0</td>
      <td>6343.0</td>
      <td>5914.0</td>
      <td>7350.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18111</td>
      <td>30212</td>
      <td>GA</td>
      <td>4100.0</td>
      <td>0</td>
      <td>920</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>48702</th>
      <td>121742</td>
      <td>11/17/2010</td>
      <td>MANHEIM</td>
      <td>2005</td>
      <td>5</td>
      <td>FORD</td>
      <td>FIVE HUNDRED</td>
      <td>SEL</td>
      <td>4D SEDAN SEL</td>
      <td>BLACK</td>
      <td>AUTO</td>
      <td>1.0</td>
      <td>Alloy</td>
      <td>88645</td>
      <td>AMERICAN</td>
      <td>LARGE</td>
      <td>FORD</td>
      <td>5358.0</td>
      <td>6836.0</td>
      <td>8987.0</td>
      <td>10905.0</td>
      <td>5761.0</td>
      <td>6965.0</td>
      <td>9764.0</td>
      <td>11395.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>20928</td>
      <td>33411</td>
      <td>FL</td>
      <td>7955.0</td>
      <td>0</td>
      <td>1633</td>
    </tr>
    <tr>
      <th>48703</th>
      <td>121743</td>
      <td>11/17/2010</td>
      <td>MANHEIM</td>
      <td>2007</td>
      <td>3</td>
      <td>TOYOTA</td>
      <td>COROLLA</td>
      <td>CE</td>
      <td>4D SEDAN CE</td>
      <td>GREEN</td>
      <td>AUTO</td>
      <td>2.0</td>
      <td>Covers</td>
      <td>81862</td>
      <td>TOP LINE ASIAN</td>
      <td>COMPACT</td>
      <td>OTHER</td>
      <td>6849.0</td>
      <td>7992.0</td>
      <td>10999.0</td>
      <td>12021.0</td>
      <td>6856.0</td>
      <td>8183.0</td>
      <td>10283.0</td>
      <td>11565.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>20928</td>
      <td>33411</td>
      <td>FL</td>
      <td>7035.0</td>
      <td>0</td>
      <td>594</td>
    </tr>
    <tr>
      <th>48704</th>
      <td>121744</td>
      <td>11/17/2010</td>
      <td>MANHEIM</td>
      <td>2006</td>
      <td>4</td>
      <td>KIA</td>
      <td>SPECTRA</td>
      <td>EX</td>
      <td>4D SEDAN EX</td>
      <td>BLACK</td>
      <td>AUTO</td>
      <td>2.0</td>
      <td>Covers</td>
      <td>82451</td>
      <td>OTHER ASIAN</td>
      <td>MEDIUM</td>
      <td>OTHER</td>
      <td>4662.0</td>
      <td>5655.0</td>
      <td>7972.0</td>
      <td>9670.0</td>
      <td>4833.0</td>
      <td>5856.0</td>
      <td>7871.0</td>
      <td>9490.0</td>
      <td>NO</td>
      <td>GREEN</td>
      <td>20928</td>
      <td>33411</td>
      <td>FL</td>
      <td>6335.0</td>
      <td>0</td>
      <td>594</td>
    </tr>
    <tr>
      <th>48705</th>
      <td>121745</td>
      <td>11/17/2010</td>
      <td>MANHEIM</td>
      <td>2005</td>
      <td>5</td>
      <td>MAZDA</td>
      <td>MAZDA3</td>
      <td>s</td>
      <td>4D SEDAN GT</td>
      <td>SILVER</td>
      <td>AUTO</td>
      <td>1.0</td>
      <td>Alloy</td>
      <td>75760</td>
      <td>OTHER ASIAN</td>
      <td>MEDIUM</td>
      <td>OTHER</td>
      <td>5953.0</td>
      <td>8166.0</td>
      <td>9137.0</td>
      <td>11949.0</td>
      <td>5092.0</td>
      <td>6853.0</td>
      <td>8576.0</td>
      <td>9937.0</td>
      <td>NO</td>
      <td>GREEN</td>
      <td>20928</td>
      <td>33411</td>
      <td>FL</td>
      <td>8055.0</td>
      <td>0</td>
      <td>1038</td>
    </tr>
    <tr>
      <th>48706</th>
      <td>121746</td>
      <td>11/17/2010</td>
      <td>MANHEIM</td>
      <td>2003</td>
      <td>7</td>
      <td>BUICK</td>
      <td>RENDEZVOUS AWD</td>
      <td>CX</td>
      <td>4D SUV CX</td>
      <td>GOLD</td>
      <td>AUTO</td>
      <td>2.0</td>
      <td>Covers</td>
      <td>82174</td>
      <td>AMERICAN</td>
      <td>MEDIUM SUV</td>
      <td>GM</td>
      <td>3269.0</td>
      <td>4435.0</td>
      <td>6893.0</td>
      <td>8221.0</td>
      <td>4526.0</td>
      <td>5761.0</td>
      <td>8266.0</td>
      <td>9388.0</td>
      <td>NO</td>
      <td>GREEN</td>
      <td>20928</td>
      <td>33411</td>
      <td>FL</td>
      <td>7755.0</td>
      <td>0</td>
      <td>5392</td>
    </tr>
  </tbody>
</table>
<p>48707 rows × 33 columns</p>
</div>



```python
alldata=pd.concat([train,test],axis=0)
alldata

alldata["PurchDate"]=pd.to_datetime(alldata["PurchDate"])
alldata["year"]=alldata["PurchDate"].dt.year
alldata["month"]=alldata["PurchDate"].dt.month
alldata["day"]=alldata["PurchDate"].dt.day
alldata["weekday"]=alldata["PurchDate"].dt.weekday
```

alldata에서 train 항목 대상 칼럼을 정하기 위해, countplot으로 target columns "IsBadBuy"와의 상관성을 분석합니다



```python
import matplotlib.pyplot as plt
import seaborn as sns
plt.figure(figsize=(16,8))
sns.countplot(alldata["weekday"],hue=alldata["IsBadBuy"])
```

<pre>
/opt/conda/lib/python3.7/site-packages/seaborn/_decorators.py:43: FutureWarning: Pass the following variable as a keyword arg: x. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
  FutureWarning
</pre>
<pre>
<AxesSubplot:xlabel='weekday', ylabel='count'>
</pre>
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA78AAAHgCAYAAABtp9qRAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjUuMSwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/YYfK9AAAACXBIWXMAAAsTAAALEwEAmpwYAAAp9klEQVR4nO3dfbRedXkn/O8lgVLFF8CUhyZQqIAVUKOEF0elqFWQdsB2WYXVCihKfWFsO1NbOs8spbSuxYxtnaH1sQ+tATK1ImItPF1Yi4yKOoImGOTFl6SiJWkEDK1UOyjg9fxxdvAOJBj1nHPn7Hw+a93r7H3t39772uteLvxm7/27q7sDAAAAY/aoaTcAAAAAc034BQAAYPSEXwAAAEZP+AUAAGD0hF8AAABGT/gFAABg9BZNu4H59sQnPrEPOOCAabcBAADAHFi9evXXu3vxQ+s7Xfg94IADsmrVqmm3AQAAwByoqq9ure6xZwAAAEZP+AUAAGD0hF8AAABGb6d75xcAAGBnct9992X9+vW59957p93KrNp9992zdOnS7Lrrrts1XvgFAAAYsfXr1+exj31sDjjggFTVtNuZFd2dTZs2Zf369TnwwAO3ax+PPQMAAIzYvffem7333ns0wTdJqip77733D3Q3W/gFAAAYuTEF381+0GsSfgEAAHYye+yxxyNuP+CAA/LUpz41y5Yty1Of+tRcccUVP9DxL7744px99tlJknPPPTdLlizJsmXL8jM/8zN53etel+9+97s/dO8/LOEXAACAh/nIRz6SNWvW5PLLL88b3/jGH+lYv/mbv5k1a9bk1ltvzU033ZSPfexjs9Tl9hN+AQAAdlIbN27Msccem2XLluXwww/Pxz/+8YeNueeee7Lnnns+uP6Sl7wkRxxxRA477LBceOGFD9YvuuiiHHLIITnqqKPyyU9+cqvn+853vpN77733weMdd9xxWbVqVZLk61//eg444IAkybHHHps1a9Y8uN9znvOc3HjjjT/StQq/AAAAO6m/+qu/yvHHH581a9bkxhtvzLJlyx7c9rznPS+HH354fvZnfzZ/8Ad/8GB9xYoVWb16dVatWpULLrggmzZtysaNG/OWt7wln/zkJ/OJT3wit9566xbnefvb355ly5Zl3333zSGHHLLFebbmzDPPzMUXX5wk+dKXvpR77703T3/603+kaxV+AQAAdlJHHnlkLrroopx77rm56aab8tjHPvbBbR/5yEdy880356abbsrZZ5+db37zm0mSCy64IE9/+tNzzDHH5Pbbb8/atWtz/fXX57jjjsvixYuz22675eUvf/kW59n82POdd96Zb33rW7n00ksfsa9f/uVfzt/+7d/mvvvuy4oVK3LGGWf8yNcq/AIAAOykjj322Fx77bVZsmRJzjjjjKxcufJhY570pCdln332ya233pqPfvSj+fCHP5xPfepTufHGG/OMZzzjB/q5oV133TUnnHBCrr322iTJokWLHpz8avI4j370o/PCF74wV1xxRS677LL8yq/8yo94pcIvAADATuurX/1q9tlnn7zmNa/Jq1/96txwww0PG3PnnXfmtttuy0/91E/lG9/4Rvbcc888+tGPzhe+8IVcd911SZKjjz46H/vYx7Jp06bcd999ed/73rfV83V3PvnJT+ZJT3pSkplZpVevXp0kufzyy7cY++pXvzpvfOMbc+SRR27xzvEPa9GPfAQAAAAWpI9+9KN529vell133TV77LHHFnd+n/e852WXXXbJfffdl/PPPz/77LNPTjjhhPzZn/1ZnvKUp+TJT35yjjnmmCTJvvvum3PPPTfPetaz8oQnPOFh7/S+/e1vz1/+5V/mvvvuy9Oe9rS8/vWvT5L81m/9Vl72spflwgsvzM///M9vsc8RRxyRxz3ucXnlK185K9da3T0rB1ooli9f3ptnEwMAABi7z3/+83nKU54y7TZ+YP/0T/+U4447Ll/4whfyqEdt/aHlrV1bVa3u7uUPHeuxZwAAAHYoK1euzNFHH523vvWt2wy+PyiPPQMAALBDOe2003LaaafN6jHd+QUAAGD03PkF2IYj3vTwqf4XqtVvm91/OQUAWGjc+QUAAGD0hF8AAABGT/gFAABgXvzd3/1dnvzkJ+eggw7K+eef/7Dt3/72t/Pyl788Bx10UI4++uh85StfmbVze+cXAABgJzPbc5tsz/wiDzzwQN7whjfk6quvztKlS3PkkUfmpJNOyqGHHvrgmHe9613Zc889s27dulx66aX5nd/5nbz3ve+dlR7d+QUAAGDOffrTn85BBx2Un/7pn85uu+2WU045JVdcccUWY6644oqcfvrpSZKXvvSlueaaa9Lds3J+4RcAAIA5t2HDhuy3334Pri9dujQbNmzY5phF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"/>


```python
plt.figure(figsize=(16,8))
sns.countplot(alldata["Auction"],hue=alldata["IsBadBuy"])
```

<pre>
/opt/conda/lib/python3.7/site-packages/seaborn/_decorators.py:43: FutureWarning: Pass the following variable as a keyword arg: x. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
  FutureWarning
</pre>
<pre>
<AxesSubplot:xlabel='Auction', ylabel='count'>
</pre>
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA78AAAHgCAYAAABtp9qRAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjUuMSwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/YYfK9AAAACXBIWXMAAAsTAAALEwEAmpwYAAApq0lEQVR4nO3de7ReZX0v+u9PAiIHlFtk0wQMJXhB0FDCpXt7KGKVSM8G2oECw21AUVqFo3W3HdqeM4RSGdsOaxmlWnvoMVzaakR6CXWgHMrG6y6XYAMBvCQFLUmpYBCsWq4+5481Q9+ElRBgvVlZD5/PGHOsOX/zmfN5psPx8n4z53zeaq0FAAAAeva86R4AAAAAjJvwCwAAQPeEXwAAALon/AIAANA94RcAAIDuCb8AAAB0b9Z0D2Br23PPPdu8efOmexgAAABMsT333DNXX3311a21RRvve86F33nz5mX58uXTPQwAAADGoKr2nKzusWcAAAC6J/wCAADQPeEXAACA7j3n3vkFAAB4Lnn00UezZs2aPPTQQ9M9lCm14447Zu7cudl+++23qL3wCwAA0LE1a9Zkl112ybx581JV0z2cKdFay7p167JmzZrst99+W3SMx54BAAA69tBDD2WPPfboJvgmSVVljz32eFp3s4VfAACAzvUUfNd7utck/AIAADzH7LzzzpvdP2/evBx88MFZsGBBDj744Cxbtuxpnf+SSy7J2WefnSQ599xzM2fOnCxYsCAvf/nL8653vSs//elPn/HYnynhFwAAgCe57rrrsmLFilxxxRV5z3ve86zO9b73vS8rVqzIHXfckZUrV+ZLX/rSFI1yywm/AAAAz1H33HNPjjrqqCxYsCAHHXRQvvKVrzypzQ9/+MPstttuT2yfeOKJOfTQQ/PKV74yF1100RP1iy++OC996Utz+OGH52tf+9qk/T3yyCN56KGHnjjf0UcfneXLlydJvv/972fevHlJkqOOOiorVqx44rjXvOY1ueWWW57VtQq/AAAAz1Gf+tSncuyxx2bFihW55ZZbsmDBgif2vfa1r81BBx2UX/iFX8iHPvShJ+pLlizJzTffnOXLl+fCCy/MunXrcs899+Scc87J1772tXz1q1/NHXfcsUE/F1xwQRYsWJC99947L33pSzfoZzJnnHFGLrnkkiTJt7/97Tz00EN59atf/ayuVfgFAAB4jjrssMNy8cUX59xzz83KlSuzyy67PLHvuuuuy2233ZaVK1fm7LPPzo9+9KMkyYUXXphXv/rVOfLII3P33Xdn1apVueGGG3L00Udn9uzZ2WGHHXLyySdv0M/6x57vvffe/PjHP87SpUs3O643velN+dznPpdHH300S5Ysyemnn/6sr1X4BQAAeI466qij8uUvfzlz5szJ6aefnssuu+xJbfbff//stddeueOOO/LFL34xf//3f59/+Id/yC233JJDDjnkaf3c0Pbbb59Fixbly1/+cpJk1qxZT0x+NXqenXbaKa9//euzbNmyXH755XnLW97yLK9U+AUAAHjO+u53v5u99tor73znO/OOd7wjX//615/U5t57781dd92Vl7zkJXnwwQez2267Zaeddso3v/nNXH/99UmSI444Il/60peybt26PProo/nsZz87aX+ttXzta1/L/vvvn2RiVumbb745SXLFFVds0PYd73hH3vOe9+Swww7b4J3jZ2rWsz4DAAAAM9IXv/jFfOQjH8n222+fnXfeeYM7v6997Wuz3Xbb5dFHH82HP/zh7LXXXlm0aFH+9E//NK94xSvyspe9LEceeWSSZO+99865556bn//5n8+uu+76pHd6L7jggvzFX/xFHn300bzqVa/Ku9/97iTJb/7mb+bNb35zLrroovzSL/3SBscceuiheeELX5i3ve1tU3Kt1VqbkhPNFAsXLmzrZxMDAADo3Te+8Y284hWvmO5hPG3/8i//kqOPPjrf/OY387znTf7Q8mTXVlU3t9YWbtzWY88AAABsUy677LIcccQROf/88zcZfJ8ujz0DAACwTVm8eHEWL148ped05xcAAIDuufMLAMA279DfevLPr9CHmz8ytXf3YFPc+QUAAKB7wi8AAADdE34BAADYKr7whS/kZS97WebPn58Pf/jDT9r/8MMP5+STT878+fNzxBFH5Dvf+c6U9e2dXwAAgOeYqX6Pfkve3X788cdz1lln5ZprrsncuXNz2GGH5fjjj8+BBx74RJtPfvKT2W233bJ69eosXbo073//+/OZz3xmSsbozi8AAABjd+ONN2b+/Pn52Z/92eywww455ZRTsmzZsg3aLFu2LKeddlqS5KSTTsq1116b1tqU9C/8AgAAMHZr167NPvvs88T23Llzs3bt2k22mTVrVl70ohdl3bp1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"/>


```python
plt.figure(figsize=(16,8))
sns.countplot(alldata["WheelType"],hue=alldata["IsBadBuy"])
```

<pre>
/opt/conda/lib/python3.7/site-packages/seaborn/_decorators.py:43: FutureWarning: Pass the following variable as a keyword arg: x. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
  FutureWarning
</pre>
<pre>
<AxesSubplot:xlabel='WheelType', ylabel='count'>
</pre>
<img src="data:image/png;base64,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"/>


```python
plt.figure(figsize=(16,8))
sns.countplot(alldata["Transmission"],hue=alldata["IsBadBuy"])
```

<pre>
/opt/conda/lib/python3.7/site-packages/seaborn/_decorators.py:43: FutureWarning: Pass the following variable as a keyword arg: x. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
  FutureWarning
</pre>
<pre>
<AxesSubplot:xlabel='Transmission', ylabel='count'>
</pre>
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA78AAAHgCAYAAABtp9qRAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjUuMSwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/YYfK9AAAACXBIWXMAAAsTAAALEwEAmpwYAAAoNUlEQVR4nO3dfbheZX0n+u9PAo0c5dXIoQkYNIgiSJQAsdNS1CqRToF2fGPaBhBlqlA7XmOneq5zBFFnHO0pleq0F6cGSDsalb6EcVAORdD6Aho0GsWXpKIlKQoEhaIHBLzPH3sl7oSdsA372Tu58/lc13M9a/3Wve51L/5Y7G/WWvdTrbUAAABAzx430wMAAACAURN+AQAA6J7wCwAAQPeEXwAAALon/AIAANA94RcAAIDuzZrpAUy3Jz3pSW3+/PkzPQwAAACm2M0333xXa23ORNt2u/A7f/78rFq1aqaHAQAAwBSrqu9ua5vHngEAAOie8AsAAED3hF8AAAC6t9u98wsAM+3BBx/M+vXrc//998/0UKbM7NmzM2/evOy5554zPRQAmJDwCwDTbP369XniE5+Y+fPnp6pmejiPWWstGzduzPr163PYYYfN9HAAYEIeewaAaXb//ffnwAMP7CL4JklV5cADD+zqTjYA/RF+AWAG9BJ8N+ntfADoj/ALADuBJzzhCdvdPn/+/Bx99NFZuHBhjj766KxcufLn6v/yyy/P+eefnyS58MILM3fu3CxcuDDPeMYz8trXvjY//elPd3jsALArEH4BYBdx/fXXZ/Xq1bnyyivz+te//jH19YY3vCGrV6/OLbfckjVr1uSTn/zkFI0SAHZOwi8A7ERuv/32nHjiiVm4cGGOOuqo/OM//uMj2tx7773Zf//9N6+ffvrpOfbYY/OsZz0rl1566eb6ZZddlqc//ek5/vjj85nPfGbC4/3kJz/J/fffv7m/k046KatWrUqS3HXXXZk/f36S5MQTT8zq1as37/fLv/zL+fKXv/xYTxcApo3wCwA7kQ984AM5+eSTs3r16nz5y1/OwoULN297/vOfn6OOOiq/+qu/mre//e2b68uWLcvNN9+cVatW5ZJLLsnGjRtz++2354ILLshnPvOZfPrTn84tt9yyxXEuvvjiLFy4MAcffHCe/vSnb3GciZxzzjm5/PLLkyTf+ta3cv/99+eYY46ZqtMGgJETfgFgJ3Lcccflsssuy4UXXpg1a9bkiU984uZt119/fb761a9mzZo1Of/883PfffclSS655JIcc8wxWbx4cW677basXbs2N910U0466aTMmTMne+21V17xildscZxNjz3fcccd+dGPfpQVK1Zsd1wve9nL8tGPfjQPPvhgli1blrPOOmvKzx0ARkn4BYCdyIknnphPfepTmTt3bs4666wsX778EW2e9rSn5aCDDsott9ySG264If/wD/+Qz33uc/nyl7+c5zznOT/XTw7tueeeWbJkST71qU8lSWbNmrV58qvx/ey999550YtelJUrV+bDH/5wfvu3f/sxnikATC/hFwB2It/97ndz0EEH5TWveU1e/epX54tf/OIj2txxxx259dZb85SnPCX33HNP9t9//+y99975xje+kRtvvDFJcsIJJ+STn/xkNm7cmAcffDAf+chHJjxeay2f+cxn8rSnPS3J2KzSN998c5Lkyiuv3KLtq1/96rz+9a/Pcccdt8U7xwCwK5g10wMAAH7mhhtuyLvf/e7sueeeecITnrDFnd/nP//52WOPPfLggw/mne98Zw466KAsWbIkf/EXf5FnPvOZOeKII7J48eIkycEHH5wLL7wwz3ve87Lffvs94p3eiy++OH/913+dBx98MM9+9rPzute9Lknyxje+MS9/+ctz6aWX5td//de32OfYY4/NPvvsk7PPPnu0/xEAYASqtTbTY5hWixYtaptmsQSAmfD1r389z3zmM2d6GD+3f/mXf8lJJ52Ub3zjG3nc4x758Niuel4A9KOqbm6tLZpom8eeAYBHtXz58pxwwgl5xzveMWHwBYCdnceeAYBHtXTp0ixdunSmhwEAO8w/3QIAANA9d36nwbF/+MifqaAPN7/bXRAAANgVuPMLAABA94RfAAAAuif8AsBu7OMf/3iOOOKILFiwIO985zsfsf2BBx7IK17xiixYsCAnnHBCvvOd70z/IAFgCnjnFwB2AlM9P8Rk5iR4+OGHc9555+Xaa6/NvHnzctxxx+XUU0/NkUceubnN+9///uy///5Zt25dVqxYkT/6oz/Khz70oSkdKwBMB3d+AWA39fnPfz4LFizIU5/61Oy111555StfmZUrV27RZuXKlTnzzDOTJC996Utz3XXXpbU2E8MFgMdE+AWA3dSGDRtyyCGHbF6fN29eNmzY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"/>


```python
plt.figure(figsize=(16,8))
sns.countplot(alldata["VehicleAge"],hue=alldata["IsBadBuy"])
```

<pre>
/opt/conda/lib/python3.7/site-packages/seaborn/_decorators.py:43: FutureWarning: Pass the following variable as a keyword arg: x. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
  FutureWarning
</pre>
<pre>
<AxesSubplot:xlabel='VehicleAge', ylabel='count'>
</pre>
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA78AAAHgCAYAAABtp9qRAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjUuMSwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/YYfK9AAAACXBIWXMAAAsTAAALEwEAmpwYAAAqM0lEQVR4nO3df7ReVXkv+u8jgSKi/DJyaYKGGqQiKJrww9pDUVuI2AOMHlQYrQHFcmqh2PaUqj1jiMVyrg56y5Ha2suVAGkrKaDecB0oUgpSGYImCEaBSo6oJMUSA0JtDxJw3j/2SroTEgyw936zZz6fMd6x3zXXXGs9a5FB8t1zrbmqtRYAAADo2XNGXQAAAABMNuEXAACA7gm/AAAAdE/4BQAAoHvCLwAAAN0TfgEAAOjejFEXMNVe+MIXtjlz5oy6DAAAACbB8uXLf9Bam7lp+3YXfufMmZNly5aNugwAAAAmQVV9d3PtbnsGAACge8IvAAAA3RN+AQAA6N5298wvAADA9mTdunVZtWpVHn300VGXMqF23nnnzJ49OzvuuONW9Rd+AQAAOrZq1ao8//nPz5w5c1JVoy5nQrTWsnbt2qxatSr77bffVm3jtmcAAICOPfroo9lrr726Cb5JUlXZa6+9ntZotvALAADQuZ6C73pP95yEXwAAgO3Mrrvu+pTr58yZk4MPPjiHHHJIDj744CxduvRp7f/SSy/NmWeemST54Ac/mFmzZuWQQw7Jz//8z+fd7353fvKTnzzj2p8p4RcAAIAnueGGG3L77bfnqquuyllnnfWs9vV7v/d7uf3223PnnXdmxYoV+eIXvzhBVW494RcAAGA7df/99+fII4/MIYcckoMOOij/+I//+KQ+jzzySPbYY48NyyeccELmzZuXV7ziFbnooos2tF9yySV52ctelsMOOyw333zzZo/32GOP5dFHH92wv6OOOirLli1LkvzgBz/InDlzkiRHHnlkbr/99g3b/eIv/mLuuOOOZ3Wuwi8AAMB26pOf/GSOOeaY3H777bnjjjtyyCGHbFj3+te/PgcddFB+6Zd+KX/yJ3+yoX3RokVZvnx5li1blgsvvDBr167N/fffn3POOSc333xzvvSlL+XOO+/c6DgXXHBBDjnkkOyzzz552ctettFxNue0007LpZdemiT51re+lUcffTSvetWrntW5Cr8AAADbqUMPPTSXXHJJPvjBD2bFihV5/vOfv2HdDTfckG984xtZsWJFzjzzzPzoRz9Kklx44YV51atelSOOOCL33Xdf7rnnntx666056qijMnPmzOy0005529vettFx1t/2/MADD+Tf/u3fsmTJkqes6y1veUs++9nPZt26dVm0aFFOPfXUZ32uwi8AAMB26sgjj8xNN92UWbNm5dRTT83ixYuf1OelL31p9t5779x555258cYb8/d///f58pe/nDvuuCOvfvWrn9brhnbccccsWLAgN910U5JkxowZGya/Gr+fXXbZJb/yK7+SpUuX5oorrsiv//qvP8szFX4BAAC2W9/97nez99575zd/8zfzrne9K7fddtuT+jzwwAO5995785KXvCQPP/xw9thjj+yyyy65++67c8sttyRJDj/88Hzxi1/M2rVrs27dulx55ZWbPV5rLTfffHNe+tKXJhmbVXr58uVJkquuumqjvu9617ty1lln5dBDD93omeNnasaz3gMAAADT0o033pjzzz8/O+64Y3bdddeNRn5f//rXZ4cddsi6devy4Q9/OHvvvXcWLFiQv/qrv8rLX/7yHHDAATniiCOSJPvss08++MEP5rWvfW123333Jz3Te8EFF+Rv/uZvsm7durzyla/Mb//2bydJ/uAP/iBvfetbc9FFF+XNb37zRtvMmzcvL3jBC/KOd7xjQs61WmsTsqPpYv78+W39bGIAAAC9u+uuu/Lyl7981GU8bf/8z/+co446KnfffXee85zN37S8uXOrquWttfmb9nXbMwAAANuUxYsX5/DDD8955523xeD7dLntGQAAgG3KwoULs3Dhwgndp5FfAAAAumfkF4Bt2ryzn/zKhVFZfv7E/gYaAJg6Rn4BAADonvALAABA94RfAAAApsTnP//5HHDAAZk7d24+/OEPP2n9j3/847ztbW/L3Llzc/jhh+c73/nOhB3bM78AAADbmYmeU2Nr5sV44okncsYZZ+S6667L7Nmzc+ihh+a4447LgQceuKHPxRdfnD322CMrV67MkiVL8t73vjd/93d/NyE1GvkFAABg0n3lK1/J3Llz83M/93PZaaedctJJJ2Xp0qUb9Vm6dGlOOeWUJMmJJ56Y66+/Pq21CTm+8AsAAMCkW716dfbdd98Ny7Nnz87q1au32GfGjBnZbbfdsnbt2gk5vvALAABA94RfAAAAJt2sWbNy3333bVhetWpVZs2atcU+jz/+eB5++OHstddeE3J84RcAAIBJd+ihh+aee+7Jvffem8ceeyxLlizJcccdt1Gf4447LpdddlmS5Kqrrsob3vCGVNWEHN9szwAAAEy6GTNm5GMf+1iOOeaYPPHEE3nnO9+ZV7ziFfnABz6Q+fPn57jjjstpp52Wt7/97Zk7d2723HPPLFmyZOKOP2F7AgAAYFrYmlcTTYZjjz02xx577EZt55577obvO++8c6688spJObbbngEAAOie8AsAAED3hF8AAAC655lfgGdo3tmLR13CRkb17A4AwHRg5BcAAIDuCb8AAAB0T/gFAABg0r3zne/Mi170ohx00EGbXd9ay1lnnZW5c+fmla98ZW677bYJPb5nfgEAALYz3zv34And34s/sOKn9jn11FNz5plnZuHCzc9T8rnPfS733HNP7rnnntx6661597vfnVtvvXXCajTyCwAAwKQ78sgjs+eee25x/dKlS7Nw4cJUVY444oj88Ic/zP333z9hxxd+AQAAGLnVq1dn33333bA8e/bsrF69esL2L/wCAADQPeEXAACAkZs1a1buu+++DcurVq3KrFmzJmz/wi8AAAAjd9xxx2Xx4sVpreWWW27Jbrvtln322WfC9m+2ZwAAACbdySefnBtvvDE/+MEPMnv27PzxH/9x1q1blyT5rd/6rRx77LG55pprMnfu3Oyyyy655JJLJvT4wi8AAMB2ZmteTTTRLr/88qdcX1X5i7/4i0k7/qTd9lxVi6rqgar6xmbW/beqalX1wmG5qurCqlpZVV+vqteM63tKVd0zfE4Z1z6vqlYM21xYVTVZ5wIAAMD0NpnP/F6aZMGmjVW1b5Kjk3xvXPObkuw/fE5P8vGh755JzklyeJLDkpxTVXsM23w8yW+O2+5JxwIAAIBkEsNva+2mJA9uZtUFSf4wSRvXdnySxW3MLUl2r6p9khyT5LrW2oOttYeSXJdkwbDuBa21W1prLcniJCdM1rkAAAAwvU3pbM9VdXyS1a21OzZZNSvJfeOWVw1tT9W+ajPtAAAAbGJszLAvT/ecpiz8VtUuSf4oyQem6pjjjn16VS2rqmVr1qyZ6sMDAACMzM4775y1a9d2FYBba1m7dm123nnnrd5mKmd7fmmS/ZLcMcxNNTvJbVV1WJLVSfYd13f2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"/>

위의 그림을 통해, 자동차를 구매했을때 불량일 확률은 weekday/Auction/WheelType/Transmission/VehicleAge에 따라 영향이 있음을 예측할 수 있다.


예측 target 칼럼인 IsBadBuy, 고유값으로 예측에 사용될 수 없는 RefId는 제거하여 전처리한다.

CatBoostClassifier를 제외하고 다른 모델에서는 주로 datetime 형식을 인식할 수 없어 전처리하였다.

CatBoostClassifier에서는 datetime의 학습 여부에 따라서 점수가 향상되는지 확인할 예정이다.



```python
alldata2=alldata.drop(columns=["IsBadBuy","RefId","PurchDate"])
# alldata2=alldata.drop(columns=["IsBadBuy","RefId"])
```

Auction의 그룹별 평균 값을 보았을때 높은 순서대로 배열하여 예측의 정확성을 높일 수 있다.



RandomForestClassifier에서 score 0.23688(높을 수록 순위 향상)



순서대로 배열하여 예측하지 않은 경우 동일 조건의 score: 0.23680



```python
alldata.groupby("Auction")["IsBadBuy"].mean()
alldata2["Auction"]=alldata2["Auction"].replace({"ADESA ":2, "OTHER":1, "MANHEIM":0})
```

classifier 모델은 object 형태의 데이터를 처리할 수 없으므로 레이블 인코딩을 사용하여 숫자 형식으로 변환한다.



```python
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()

category = alldata2.columns[alldata2.dtypes == object]
category
for col in category : 
    alldata2[col] = le.fit_transform(list(alldata2[col]))
    
alldata2
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Auction</th>
      <th>VehYear</th>
      <th>VehicleAge</th>
      <th>Make</th>
      <th>Model</th>
      <th>Trim</th>
      <th>SubModel</th>
      <th>Color</th>
      <th>Transmission</th>
      <th>WheelTypeID</th>
      <th>WheelType</th>
      <th>VehOdo</th>
      <th>Nationality</th>
      <th>Size</th>
      <th>TopThreeAmericanName</th>
      <th>MMRAcquisitionAuctionAveragePrice</th>
      <th>MMRAcquisitionAuctionCleanPrice</th>
      <th>MMRAcquisitionRetailAveragePrice</th>
      <th>MMRAcquisitonRetailCleanPrice</th>
      <th>MMRCurrentAuctionAveragePrice</th>
      <th>MMRCurrentAuctionCleanPrice</th>
      <th>MMRCurrentRetailAveragePrice</th>
      <th>MMRCurrentRetailCleanPrice</th>
      <th>PRIMEUNIT</th>
      <th>AUCGUART</th>
      <th>BYRNO</th>
      <th>VNZIP1</th>
      <th>VNST</th>
      <th>VehBCost</th>
      <th>IsOnlineSale</th>
      <th>WarrantyCost</th>
      <th>year</th>
      <th>month</th>
      <th>day</th>
      <th>weekday</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>2006</td>
      <td>3</td>
      <td>17</td>
      <td>620</td>
      <td>135</td>
      <td>236</td>
      <td>13</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>89046</td>
      <td>2</td>
      <td>5</td>
      <td>3</td>
      <td>8155.0</td>
      <td>9829.0</td>
      <td>11636.0</td>
      <td>13600.0</td>
      <td>7451.0</td>
      <td>8552.0</td>
      <td>11597.0</td>
      <td>12409.0</td>
      <td>2</td>
      <td>2</td>
      <td>21973</td>
      <td>33619</td>
      <td>5</td>
      <td>7100.0</td>
      <td>0</td>
      <td>1113</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>2004</td>
      <td>5</td>
      <td>5</td>
      <td>0</td>
      <td>94</td>
      <td>826</td>
      <td>15</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>93593</td>
      <td>0</td>
      <td>4</td>
      <td>0</td>
      <td>6854.0</td>
      <td>8383.0</td>
      <td>10897.0</td>
      <td>12572.0</td>
      <td>7456.0</td>
      <td>9222.0</td>
      <td>11374.0</td>
      <td>12791.0</td>
      <td>2</td>
      <td>2</td>
      <td>19638</td>
      <td>33619</td>
      <td>5</td>
      <td>7600.0</td>
      <td>0</td>
      <td>1053</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>2005</td>
      <td>4</td>
      <td>5</td>
      <td>938</td>
      <td>99</td>
      <td>311</td>
      <td>7</td>
      <td>0</td>
      <td>2.0</td>
      <td>1</td>
      <td>73807</td>
      <td>0</td>
      <td>5</td>
      <td>0</td>
      <td>3202.0</td>
      <td>4760.0</td>
      <td>6943.0</td>
      <td>8457.0</td>
      <td>4035.0</td>
      <td>5557.0</td>
      <td>7146.0</td>
      <td>8702.0</td>
      <td>2</td>
      <td>2</td>
      <td>19638</td>
      <td>33619</td>
      <td>5</td>
      <td>4900.0</td>
      <td>0</td>
      <td>1389</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>2004</td>
      <td>5</td>
      <td>5</td>
      <td>700</td>
      <td>99</td>
      <td>165</td>
      <td>14</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>65617</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1893.0</td>
      <td>2675.0</td>
      <td>4658.0</td>
      <td>5690.0</td>
      <td>1844.0</td>
      <td>2646.0</td>
      <td>4375.0</td>
      <td>5518.0</td>
      <td>2</td>
      <td>2</td>
      <td>19638</td>
      <td>33619</td>
      <td>5</td>
      <td>4100.0</td>
      <td>0</td>
      <td>630</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>2005</td>
      <td>4</td>
      <td>6</td>
      <td>389</td>
      <td>129</td>
      <td>55</td>
      <td>14</td>
      <td>1</td>
      <td>2.0</td>
      <td>1</td>
      <td>69367</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>3913.0</td>
      <td>5054.0</td>
      <td>7723.0</td>
      <td>8707.0</td>
      <td>3247.0</td>
      <td>4384.0</td>
      <td>6739.0</td>
      <td>7911.0</td>
      <td>2</td>
      <td>2</td>
      <td>19638</td>
      <td>33619</td>
      <td>5</td>
      <td>4000.0</td>
      <td>0</td>
      <td>1020</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>48702</th>
      <td>0</td>
      <td>2005</td>
      <td>5</td>
      <td>6</td>
      <td>386</td>
      <td>85</td>
      <td>292</td>
      <td>1</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>88645</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
      <td>5358.0</td>
      <td>6836.0</td>
      <td>8987.0</td>
      <td>10905.0</td>
      <td>5761.0</td>
      <td>6965.0</td>
      <td>9764.0</td>
      <td>11395.0</td>
      <td>2</td>
      <td>2</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>7955.0</td>
      <td>0</td>
      <td>1633</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
    <tr>
      <th>48703</th>
      <td>0</td>
      <td>2007</td>
      <td>3</td>
      <td>29</td>
      <td>241</td>
      <td>9</td>
      <td>198</td>
      <td>5</td>
      <td>0</td>
      <td>2.0</td>
      <td>1</td>
      <td>81862</td>
      <td>3</td>
      <td>0</td>
      <td>3</td>
      <td>6849.0</td>
      <td>7992.0</td>
      <td>10999.0</td>
      <td>12021.0</td>
      <td>6856.0</td>
      <td>8183.0</td>
      <td>10283.0</td>
      <td>11565.0</td>
      <td>2</td>
      <td>2</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>7035.0</td>
      <td>0</td>
      <td>594</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
    <tr>
      <th>48704</th>
      <td>0</td>
      <td>2006</td>
      <td>4</td>
      <td>14</td>
      <td>912</td>
      <td>23</td>
      <td>210</td>
      <td>1</td>
      <td>0</td>
      <td>2.0</td>
      <td>1</td>
      <td>82451</td>
      <td>2</td>
      <td>5</td>
      <td>3</td>
      <td>4662.0</td>
      <td>5655.0</td>
      <td>7972.0</td>
      <td>9670.0</td>
      <td>4833.0</td>
      <td>5856.0</td>
      <td>7871.0</td>
      <td>9490.0</td>
      <td>0</td>
      <td>0</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>6335.0</td>
      <td>0</td>
      <td>594</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
    <tr>
      <th>48705</th>
      <td>0</td>
      <td>2005</td>
      <td>5</td>
      <td>17</td>
      <td>620</td>
      <td>137</td>
      <td>223</td>
      <td>14</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>75760</td>
      <td>2</td>
      <td>5</td>
      <td>3</td>
      <td>5953.0</td>
      <td>8166.0</td>
      <td>9137.0</td>
      <td>11949.0</td>
      <td>5092.0</td>
      <td>6853.0</td>
      <td>8576.0</td>
      <td>9937.0</td>
      <td>0</td>
      <td>0</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>8055.0</td>
      <td>0</td>
      <td>1038</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
    <tr>
      <th>48706</th>
      <td>0</td>
      <td>2003</td>
      <td>7</td>
      <td>1</td>
      <td>799</td>
      <td>10</td>
      <td>479</td>
      <td>4</td>
      <td>0</td>
      <td>2.0</td>
      <td>1</td>
      <td>82174</td>
      <td>0</td>
      <td>6</td>
      <td>2</td>
      <td>3269.0</td>
      <td>4435.0</td>
      <td>6893.0</td>
      <td>8221.0</td>
      <td>4526.0</td>
      <td>5761.0</td>
      <td>8266.0</td>
      <td>9388.0</td>
      <td>0</td>
      <td>0</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>7755.0</td>
      <td>0</td>
      <td>5392</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>121690 rows × 35 columns</p>
</div>



```python
alldata2=alldata2.fillna(-1)
alldata2
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Auction</th>
      <th>VehYear</th>
      <th>VehicleAge</th>
      <th>Make</th>
      <th>Model</th>
      <th>Trim</th>
      <th>SubModel</th>
      <th>Color</th>
      <th>Transmission</th>
      <th>WheelTypeID</th>
      <th>WheelType</th>
      <th>VehOdo</th>
      <th>Nationality</th>
      <th>Size</th>
      <th>TopThreeAmericanName</th>
      <th>MMRAcquisitionAuctionAveragePrice</th>
      <th>MMRAcquisitionAuctionCleanPrice</th>
      <th>MMRAcquisitionRetailAveragePrice</th>
      <th>MMRAcquisitonRetailCleanPrice</th>
      <th>MMRCurrentAuctionAveragePrice</th>
      <th>MMRCurrentAuctionCleanPrice</th>
      <th>MMRCurrentRetailAveragePrice</th>
      <th>MMRCurrentRetailCleanPrice</th>
      <th>PRIMEUNIT</th>
      <th>AUCGUART</th>
      <th>BYRNO</th>
      <th>VNZIP1</th>
      <th>VNST</th>
      <th>VehBCost</th>
      <th>IsOnlineSale</th>
      <th>WarrantyCost</th>
      <th>year</th>
      <th>month</th>
      <th>day</th>
      <th>weekday</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>2006</td>
      <td>3</td>
      <td>17</td>
      <td>620</td>
      <td>135</td>
      <td>236</td>
      <td>13</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>89046</td>
      <td>2</td>
      <td>5</td>
      <td>3</td>
      <td>8155.0</td>
      <td>9829.0</td>
      <td>11636.0</td>
      <td>13600.0</td>
      <td>7451.0</td>
      <td>8552.0</td>
      <td>11597.0</td>
      <td>12409.0</td>
      <td>2</td>
      <td>2</td>
      <td>21973</td>
      <td>33619</td>
      <td>5</td>
      <td>7100.0</td>
      <td>0</td>
      <td>1113</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>2004</td>
      <td>5</td>
      <td>5</td>
      <td>0</td>
      <td>94</td>
      <td>826</td>
      <td>15</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>93593</td>
      <td>0</td>
      <td>4</td>
      <td>0</td>
      <td>6854.0</td>
      <td>8383.0</td>
      <td>10897.0</td>
      <td>12572.0</td>
      <td>7456.0</td>
      <td>9222.0</td>
      <td>11374.0</td>
      <td>12791.0</td>
      <td>2</td>
      <td>2</td>
      <td>19638</td>
      <td>33619</td>
      <td>5</td>
      <td>7600.0</td>
      <td>0</td>
      <td>1053</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>2005</td>
      <td>4</td>
      <td>5</td>
      <td>938</td>
      <td>99</td>
      <td>311</td>
      <td>7</td>
      <td>0</td>
      <td>2.0</td>
      <td>1</td>
      <td>73807</td>
      <td>0</td>
      <td>5</td>
      <td>0</td>
      <td>3202.0</td>
      <td>4760.0</td>
      <td>6943.0</td>
      <td>8457.0</td>
      <td>4035.0</td>
      <td>5557.0</td>
      <td>7146.0</td>
      <td>8702.0</td>
      <td>2</td>
      <td>2</td>
      <td>19638</td>
      <td>33619</td>
      <td>5</td>
      <td>4900.0</td>
      <td>0</td>
      <td>1389</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>2004</td>
      <td>5</td>
      <td>5</td>
      <td>700</td>
      <td>99</td>
      <td>165</td>
      <td>14</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>65617</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1893.0</td>
      <td>2675.0</td>
      <td>4658.0</td>
      <td>5690.0</td>
      <td>1844.0</td>
      <td>2646.0</td>
      <td>4375.0</td>
      <td>5518.0</td>
      <td>2</td>
      <td>2</td>
      <td>19638</td>
      <td>33619</td>
      <td>5</td>
      <td>4100.0</td>
      <td>0</td>
      <td>630</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>2005</td>
      <td>4</td>
      <td>6</td>
      <td>389</td>
      <td>129</td>
      <td>55</td>
      <td>14</td>
      <td>1</td>
      <td>2.0</td>
      <td>1</td>
      <td>69367</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>3913.0</td>
      <td>5054.0</td>
      <td>7723.0</td>
      <td>8707.0</td>
      <td>3247.0</td>
      <td>4384.0</td>
      <td>6739.0</td>
      <td>7911.0</td>
      <td>2</td>
      <td>2</td>
      <td>19638</td>
      <td>33619</td>
      <td>5</td>
      <td>4000.0</td>
      <td>0</td>
      <td>1020</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>48702</th>
      <td>0</td>
      <td>2005</td>
      <td>5</td>
      <td>6</td>
      <td>386</td>
      <td>85</td>
      <td>292</td>
      <td>1</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>88645</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
      <td>5358.0</td>
      <td>6836.0</td>
      <td>8987.0</td>
      <td>10905.0</td>
      <td>5761.0</td>
      <td>6965.0</td>
      <td>9764.0</td>
      <td>11395.0</td>
      <td>2</td>
      <td>2</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>7955.0</td>
      <td>0</td>
      <td>1633</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
    <tr>
      <th>48703</th>
      <td>0</td>
      <td>2007</td>
      <td>3</td>
      <td>29</td>
      <td>241</td>
      <td>9</td>
      <td>198</td>
      <td>5</td>
      <td>0</td>
      <td>2.0</td>
      <td>1</td>
      <td>81862</td>
      <td>3</td>
      <td>0</td>
      <td>3</td>
      <td>6849.0</td>
      <td>7992.0</td>
      <td>10999.0</td>
      <td>12021.0</td>
      <td>6856.0</td>
      <td>8183.0</td>
      <td>10283.0</td>
      <td>11565.0</td>
      <td>2</td>
      <td>2</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>7035.0</td>
      <td>0</td>
      <td>594</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
    <tr>
      <th>48704</th>
      <td>0</td>
      <td>2006</td>
      <td>4</td>
      <td>14</td>
      <td>912</td>
      <td>23</td>
      <td>210</td>
      <td>1</td>
      <td>0</td>
      <td>2.0</td>
      <td>1</td>
      <td>82451</td>
      <td>2</td>
      <td>5</td>
      <td>3</td>
      <td>4662.0</td>
      <td>5655.0</td>
      <td>7972.0</td>
      <td>9670.0</td>
      <td>4833.0</td>
      <td>5856.0</td>
      <td>7871.0</td>
      <td>9490.0</td>
      <td>0</td>
      <td>0</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>6335.0</td>
      <td>0</td>
      <td>594</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
    <tr>
      <th>48705</th>
      <td>0</td>
      <td>2005</td>
      <td>5</td>
      <td>17</td>
      <td>620</td>
      <td>137</td>
      <td>223</td>
      <td>14</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>75760</td>
      <td>2</td>
      <td>5</td>
      <td>3</td>
      <td>5953.0</td>
      <td>8166.0</td>
      <td>9137.0</td>
      <td>11949.0</td>
      <td>5092.0</td>
      <td>6853.0</td>
      <td>8576.0</td>
      <td>9937.0</td>
      <td>0</td>
      <td>0</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>8055.0</td>
      <td>0</td>
      <td>1038</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
    <tr>
      <th>48706</th>
      <td>0</td>
      <td>2003</td>
      <td>7</td>
      <td>1</td>
      <td>799</td>
      <td>10</td>
      <td>479</td>
      <td>4</td>
      <td>0</td>
      <td>2.0</td>
      <td>1</td>
      <td>82174</td>
      <td>0</td>
      <td>6</td>
      <td>2</td>
      <td>3269.0</td>
      <td>4435.0</td>
      <td>6893.0</td>
      <td>8221.0</td>
      <td>4526.0</td>
      <td>5761.0</td>
      <td>8266.0</td>
      <td>9388.0</td>
      <td>0</td>
      <td>0</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>7755.0</td>
      <td>0</td>
      <td>5392</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>121690 rows × 35 columns</p>
</div>



```python
train2=alldata2[:len(train)]
test2=alldata2[len(train):]
display(train2,test2)
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Auction</th>
      <th>VehYear</th>
      <th>VehicleAge</th>
      <th>Make</th>
      <th>Model</th>
      <th>Trim</th>
      <th>SubModel</th>
      <th>Color</th>
      <th>Transmission</th>
      <th>WheelTypeID</th>
      <th>WheelType</th>
      <th>VehOdo</th>
      <th>Nationality</th>
      <th>Size</th>
      <th>TopThreeAmericanName</th>
      <th>MMRAcquisitionAuctionAveragePrice</th>
      <th>MMRAcquisitionAuctionCleanPrice</th>
      <th>MMRAcquisitionRetailAveragePrice</th>
      <th>MMRAcquisitonRetailCleanPrice</th>
      <th>MMRCurrentAuctionAveragePrice</th>
      <th>MMRCurrentAuctionCleanPrice</th>
      <th>MMRCurrentRetailAveragePrice</th>
      <th>MMRCurrentRetailCleanPrice</th>
      <th>PRIMEUNIT</th>
      <th>AUCGUART</th>
      <th>BYRNO</th>
      <th>VNZIP1</th>
      <th>VNST</th>
      <th>VehBCost</th>
      <th>IsOnlineSale</th>
      <th>WarrantyCost</th>
      <th>year</th>
      <th>month</th>
      <th>day</th>
      <th>weekday</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>2006</td>
      <td>3</td>
      <td>17</td>
      <td>620</td>
      <td>135</td>
      <td>236</td>
      <td>13</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>89046</td>
      <td>2</td>
      <td>5</td>
      <td>3</td>
      <td>8155.0</td>
      <td>9829.0</td>
      <td>11636.0</td>
      <td>13600.0</td>
      <td>7451.0</td>
      <td>8552.0</td>
      <td>11597.0</td>
      <td>12409.0</td>
      <td>2</td>
      <td>2</td>
      <td>21973</td>
      <td>33619</td>
      <td>5</td>
      <td>7100.0</td>
      <td>0</td>
      <td>1113</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>2004</td>
      <td>5</td>
      <td>5</td>
      <td>0</td>
      <td>94</td>
      <td>826</td>
      <td>15</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>93593</td>
      <td>0</td>
      <td>4</td>
      <td>0</td>
      <td>6854.0</td>
      <td>8383.0</td>
      <td>10897.0</td>
      <td>12572.0</td>
      <td>7456.0</td>
      <td>9222.0</td>
      <td>11374.0</td>
      <td>12791.0</td>
      <td>2</td>
      <td>2</td>
      <td>19638</td>
      <td>33619</td>
      <td>5</td>
      <td>7600.0</td>
      <td>0</td>
      <td>1053</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>2005</td>
      <td>4</td>
      <td>5</td>
      <td>938</td>
      <td>99</td>
      <td>311</td>
      <td>7</td>
      <td>0</td>
      <td>2.0</td>
      <td>1</td>
      <td>73807</td>
      <td>0</td>
      <td>5</td>
      <td>0</td>
      <td>3202.0</td>
      <td>4760.0</td>
      <td>6943.0</td>
      <td>8457.0</td>
      <td>4035.0</td>
      <td>5557.0</td>
      <td>7146.0</td>
      <td>8702.0</td>
      <td>2</td>
      <td>2</td>
      <td>19638</td>
      <td>33619</td>
      <td>5</td>
      <td>4900.0</td>
      <td>0</td>
      <td>1389</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>2004</td>
      <td>5</td>
      <td>5</td>
      <td>700</td>
      <td>99</td>
      <td>165</td>
      <td>14</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>65617</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1893.0</td>
      <td>2675.0</td>
      <td>4658.0</td>
      <td>5690.0</td>
      <td>1844.0</td>
      <td>2646.0</td>
      <td>4375.0</td>
      <td>5518.0</td>
      <td>2</td>
      <td>2</td>
      <td>19638</td>
      <td>33619</td>
      <td>5</td>
      <td>4100.0</td>
      <td>0</td>
      <td>630</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>2005</td>
      <td>4</td>
      <td>6</td>
      <td>389</td>
      <td>129</td>
      <td>55</td>
      <td>14</td>
      <td>1</td>
      <td>2.0</td>
      <td>1</td>
      <td>69367</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>3913.0</td>
      <td>5054.0</td>
      <td>7723.0</td>
      <td>8707.0</td>
      <td>3247.0</td>
      <td>4384.0</td>
      <td>6739.0</td>
      <td>7911.0</td>
      <td>2</td>
      <td>2</td>
      <td>19638</td>
      <td>33619</td>
      <td>5</td>
      <td>4000.0</td>
      <td>0</td>
      <td>1020</td>
      <td>2009</td>
      <td>12</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>72978</th>
      <td>2</td>
      <td>2001</td>
      <td>8</td>
      <td>18</td>
      <td>842</td>
      <td>33</td>
      <td>221</td>
      <td>1</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>45234</td>
      <td>0</td>
      <td>5</td>
      <td>1</td>
      <td>1996.0</td>
      <td>2993.0</td>
      <td>2656.0</td>
      <td>3732.0</td>
      <td>2190.0</td>
      <td>3055.0</td>
      <td>4836.0</td>
      <td>5937.0</td>
      <td>2</td>
      <td>2</td>
      <td>18111</td>
      <td>30212</td>
      <td>6</td>
      <td>4200.0</td>
      <td>0</td>
      <td>993</td>
      <td>2009</td>
      <td>12</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>72979</th>
      <td>2</td>
      <td>2007</td>
      <td>2</td>
      <td>3</td>
      <td>589</td>
      <td>56</td>
      <td>248</td>
      <td>14</td>
      <td>0</td>
      <td>-1.0</td>
      <td>3</td>
      <td>71759</td>
      <td>0</td>
      <td>5</td>
      <td>2</td>
      <td>6418.0</td>
      <td>7325.0</td>
      <td>7431.0</td>
      <td>8411.0</td>
      <td>6785.0</td>
      <td>8132.0</td>
      <td>10151.0</td>
      <td>11652.0</td>
      <td>2</td>
      <td>2</td>
      <td>18881</td>
      <td>30212</td>
      <td>6</td>
      <td>6200.0</td>
      <td>0</td>
      <td>1038</td>
      <td>2009</td>
      <td>12</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>72980</th>
      <td>2</td>
      <td>2005</td>
      <td>4</td>
      <td>13</td>
      <td>459</td>
      <td>63</td>
      <td>540</td>
      <td>14</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>88500</td>
      <td>0</td>
      <td>6</td>
      <td>0</td>
      <td>8545.0</td>
      <td>9959.0</td>
      <td>9729.0</td>
      <td>11256.0</td>
      <td>8375.0</td>
      <td>9802.0</td>
      <td>11831.0</td>
      <td>14402.0</td>
      <td>2</td>
      <td>2</td>
      <td>18111</td>
      <td>30212</td>
      <td>6</td>
      <td>8200.0</td>
      <td>0</td>
      <td>1893</td>
      <td>2009</td>
      <td>12</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>72981</th>
      <td>2</td>
      <td>2006</td>
      <td>3</td>
      <td>3</td>
      <td>505</td>
      <td>56</td>
      <td>248</td>
      <td>15</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>79554</td>
      <td>0</td>
      <td>2</td>
      <td>2</td>
      <td>6420.0</td>
      <td>7604.0</td>
      <td>7434.0</td>
      <td>8712.0</td>
      <td>6590.0</td>
      <td>7684.0</td>
      <td>10099.0</td>
      <td>11228.0</td>
      <td>2</td>
      <td>2</td>
      <td>18881</td>
      <td>30212</td>
      <td>6</td>
      <td>7000.0</td>
      <td>0</td>
      <td>1974</td>
      <td>2009</td>
      <td>12</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>72982</th>
      <td>2</td>
      <td>2006</td>
      <td>3</td>
      <td>17</td>
      <td>629</td>
      <td>137</td>
      <td>280</td>
      <td>14</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>66855</td>
      <td>2</td>
      <td>5</td>
      <td>3</td>
      <td>7535.0</td>
      <td>8771.0</td>
      <td>8638.0</td>
      <td>9973.0</td>
      <td>7730.0</td>
      <td>9102.0</td>
      <td>11954.0</td>
      <td>13246.0</td>
      <td>2</td>
      <td>2</td>
      <td>18111</td>
      <td>30212</td>
      <td>6</td>
      <td>8000.0</td>
      <td>0</td>
      <td>1313</td>
      <td>2009</td>
      <td>12</td>
      <td>2</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>72983 rows × 35 columns</p>
</div>


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Auction</th>
      <th>VehYear</th>
      <th>VehicleAge</th>
      <th>Make</th>
      <th>Model</th>
      <th>Trim</th>
      <th>SubModel</th>
      <th>Color</th>
      <th>Transmission</th>
      <th>WheelTypeID</th>
      <th>WheelType</th>
      <th>VehOdo</th>
      <th>Nationality</th>
      <th>Size</th>
      <th>TopThreeAmericanName</th>
      <th>MMRAcquisitionAuctionAveragePrice</th>
      <th>MMRAcquisitionAuctionCleanPrice</th>
      <th>MMRAcquisitionRetailAveragePrice</th>
      <th>MMRAcquisitonRetailCleanPrice</th>
      <th>MMRCurrentAuctionAveragePrice</th>
      <th>MMRCurrentAuctionCleanPrice</th>
      <th>MMRCurrentRetailAveragePrice</th>
      <th>MMRCurrentRetailCleanPrice</th>
      <th>PRIMEUNIT</th>
      <th>AUCGUART</th>
      <th>BYRNO</th>
      <th>VNZIP1</th>
      <th>VNST</th>
      <th>VehBCost</th>
      <th>IsOnlineSale</th>
      <th>WarrantyCost</th>
      <th>year</th>
      <th>month</th>
      <th>day</th>
      <th>weekday</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>2005</td>
      <td>4</td>
      <td>24</td>
      <td>464</td>
      <td>7</td>
      <td>165</td>
      <td>14</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>85377</td>
      <td>0</td>
      <td>2</td>
      <td>2</td>
      <td>5032.0</td>
      <td>6386.0</td>
      <td>5935.0</td>
      <td>7397.0</td>
      <td>4905.0</td>
      <td>6181.0</td>
      <td>8557.0</td>
      <td>9752.0</td>
      <td>2</td>
      <td>2</td>
      <td>18881</td>
      <td>30212</td>
      <td>6</td>
      <td>6500.0</td>
      <td>0</td>
      <td>2152</td>
      <td>2009</td>
      <td>12</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>2005</td>
      <td>4</td>
      <td>3</td>
      <td>597</td>
      <td>56</td>
      <td>248</td>
      <td>14</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>61873</td>
      <td>0</td>
      <td>5</td>
      <td>2</td>
      <td>4502.0</td>
      <td>5685.0</td>
      <td>5362.0</td>
      <td>6640.0</td>
      <td>4645.0</td>
      <td>5710.0</td>
      <td>7562.0</td>
      <td>9296.0</td>
      <td>2</td>
      <td>2</td>
      <td>18111</td>
      <td>30212</td>
      <td>6</td>
      <td>6300.0</td>
      <td>0</td>
      <td>1118</td>
      <td>2009</td>
      <td>12</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>2006</td>
      <td>3</td>
      <td>5</td>
      <td>270</td>
      <td>6</td>
      <td>438</td>
      <td>14</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>69283</td>
      <td>0</td>
      <td>6</td>
      <td>0</td>
      <td>10244.0</td>
      <td>13041.0</td>
      <td>11564.0</td>
      <td>14584.0</td>
      <td>10883.0</td>
      <td>12166.0</td>
      <td>15340.0</td>
      <td>16512.0</td>
      <td>2</td>
      <td>2</td>
      <td>18111</td>
      <td>30212</td>
      <td>6</td>
      <td>9700.0</td>
      <td>0</td>
      <td>1215</td>
      <td>2009</td>
      <td>12</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>2002</td>
      <td>7</td>
      <td>25</td>
      <td>540</td>
      <td>52</td>
      <td>239</td>
      <td>4</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>87889</td>
      <td>0</td>
      <td>5</td>
      <td>2</td>
      <td>2558.0</td>
      <td>3542.0</td>
      <td>3263.0</td>
      <td>4325.0</td>
      <td>2928.0</td>
      <td>3607.0</td>
      <td>5725.0</td>
      <td>6398.0</td>
      <td>2</td>
      <td>2</td>
      <td>18881</td>
      <td>30212</td>
      <td>6</td>
      <td>4150.0</td>
      <td>0</td>
      <td>1933</td>
      <td>2009</td>
      <td>12</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>2007</td>
      <td>2</td>
      <td>10</td>
      <td>42</td>
      <td>33</td>
      <td>27</td>
      <td>2</td>
      <td>0</td>
      <td>-1.0</td>
      <td>3</td>
      <td>73432</td>
      <td>2</td>
      <td>0</td>
      <td>3</td>
      <td>5013.0</td>
      <td>6343.0</td>
      <td>5914.0</td>
      <td>7350.0</td>
      <td>5013.0</td>
      <td>6343.0</td>
      <td>5914.0</td>
      <td>7350.0</td>
      <td>2</td>
      <td>2</td>
      <td>18111</td>
      <td>30212</td>
      <td>6</td>
      <td>4100.0</td>
      <td>0</td>
      <td>920</td>
      <td>2009</td>
      <td>12</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>48702</th>
      <td>0</td>
      <td>2005</td>
      <td>5</td>
      <td>6</td>
      <td>386</td>
      <td>85</td>
      <td>292</td>
      <td>1</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>88645</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
      <td>5358.0</td>
      <td>6836.0</td>
      <td>8987.0</td>
      <td>10905.0</td>
      <td>5761.0</td>
      <td>6965.0</td>
      <td>9764.0</td>
      <td>11395.0</td>
      <td>2</td>
      <td>2</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>7955.0</td>
      <td>0</td>
      <td>1633</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
    <tr>
      <th>48703</th>
      <td>0</td>
      <td>2007</td>
      <td>3</td>
      <td>29</td>
      <td>241</td>
      <td>9</td>
      <td>198</td>
      <td>5</td>
      <td>0</td>
      <td>2.0</td>
      <td>1</td>
      <td>81862</td>
      <td>3</td>
      <td>0</td>
      <td>3</td>
      <td>6849.0</td>
      <td>7992.0</td>
      <td>10999.0</td>
      <td>12021.0</td>
      <td>6856.0</td>
      <td>8183.0</td>
      <td>10283.0</td>
      <td>11565.0</td>
      <td>2</td>
      <td>2</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>7035.0</td>
      <td>0</td>
      <td>594</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
    <tr>
      <th>48704</th>
      <td>0</td>
      <td>2006</td>
      <td>4</td>
      <td>14</td>
      <td>912</td>
      <td>23</td>
      <td>210</td>
      <td>1</td>
      <td>0</td>
      <td>2.0</td>
      <td>1</td>
      <td>82451</td>
      <td>2</td>
      <td>5</td>
      <td>3</td>
      <td>4662.0</td>
      <td>5655.0</td>
      <td>7972.0</td>
      <td>9670.0</td>
      <td>4833.0</td>
      <td>5856.0</td>
      <td>7871.0</td>
      <td>9490.0</td>
      <td>0</td>
      <td>0</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>6335.0</td>
      <td>0</td>
      <td>594</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
    <tr>
      <th>48705</th>
      <td>0</td>
      <td>2005</td>
      <td>5</td>
      <td>17</td>
      <td>620</td>
      <td>137</td>
      <td>223</td>
      <td>14</td>
      <td>0</td>
      <td>1.0</td>
      <td>0</td>
      <td>75760</td>
      <td>2</td>
      <td>5</td>
      <td>3</td>
      <td>5953.0</td>
      <td>8166.0</td>
      <td>9137.0</td>
      <td>11949.0</td>
      <td>5092.0</td>
      <td>6853.0</td>
      <td>8576.0</td>
      <td>9937.0</td>
      <td>0</td>
      <td>0</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>8055.0</td>
      <td>0</td>
      <td>1038</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
    <tr>
      <th>48706</th>
      <td>0</td>
      <td>2003</td>
      <td>7</td>
      <td>1</td>
      <td>799</td>
      <td>10</td>
      <td>479</td>
      <td>4</td>
      <td>0</td>
      <td>2.0</td>
      <td>1</td>
      <td>82174</td>
      <td>0</td>
      <td>6</td>
      <td>2</td>
      <td>3269.0</td>
      <td>4435.0</td>
      <td>6893.0</td>
      <td>8221.0</td>
      <td>4526.0</td>
      <td>5761.0</td>
      <td>8266.0</td>
      <td>9388.0</td>
      <td>0</td>
      <td>0</td>
      <td>20928</td>
      <td>33411</td>
      <td>5</td>
      <td>7755.0</td>
      <td>0</td>
      <td>5392</td>
      <td>2010</td>
      <td>11</td>
      <td>17</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>48707 rows × 35 columns</p>
</div>


RandomForestClassifier score 0.23688(점수 높을수록 순위 향상)



CatBoostClassifier score 0.25621 / DATETIME 형식의 PurchDate추가하였을때 score 0.25750



GradientBoostingClassifier score 0.24779



XGBClassifier score 0.24431



LGBMClassifier 0.25392



CatBoostClassifier > LGBMClassifier > GradientBoostingClassifier > XGBClassifier > RandomForestClassifier



CatBoostClassifier의 경우 오류를 보정하면서 date time 형식의 데이터를 추가로 학습할 수 있어 가장 적합한 모델로 선정되었다.



```python
from sklearn.ensemble import RandomForestClassifier
rfc=RandomForestClassifier()
rfc.fit(train2,train["IsBadBuy"])
result=rfc.predict_proba(test2)
result
```

<pre>
array([[0.93, 0.07],
       [0.94, 0.06],
       [0.98, 0.02],
       ...,
       [0.97, 0.03],
       [0.88, 0.12],
       [0.93, 0.07]])
</pre>

```python
from sklearn.ensemble import GradientBoostingClassifier
gbc=GradientBoostingClassifier()
gbc.fit(train2,train["IsBadBuy"])
result=gbc.predict_proba(test2)
result
```

<pre>
array([[0.93534645, 0.06465355],
       [0.94635939, 0.05364061],
       [0.95021494, 0.04978506],
       ...,
       [0.96491573, 0.03508427],
       [0.94898903, 0.05101097],
       [0.94792384, 0.05207616]])
</pre>

```python
from xgboost import XGBClassifier
xgbc=XGBClassifier()
xgbc.fit(train2,train["IsBadBuy"])
result=xgbc.predict_proba(test2)
result
```

<pre>
/opt/conda/lib/python3.7/site-packages/xgboost/sklearn.py:1224: UserWarning: The use of label encoder in XGBClassifier is deprecated and will be removed in a future release. To remove this warning, do the following: 1) Pass option use_label_encoder=False when constructing XGBClassifier object; and 2) Encode your labels (y) as integers starting with 0, i.e. 0, 1, 2, ..., [num_class - 1].
  warnings.warn(label_encoder_deprecation_msg, UserWarning)
</pre>
<pre>
[07:29:37] WARNING: ../src/learner.cc:1115: Starting in XGBoost 1.3.0, the default evaluation metric used with the objective 'binary:logistic' was changed from 'error' to 'logloss'. Explicitly set eval_metric if you'd like to restore the old behavior.
</pre>
<pre>
array([[0.9634486 , 0.03655142],
       [0.95317996, 0.04682005],
       [0.9588968 , 0.04110317],
       ...,
       [0.9913116 , 0.00868841],
       [0.9735207 , 0.02647929],
       [0.9904574 , 0.00954259]], dtype=float32)
</pre>

```python
from lightgbm import LGBMClassifier
lgbmc=LGBMClassifier()
lgbmc.fit(train2,train["IsBadBuy"])
result=lgbmc.predict_proba(test2)
result
```

<style type='text/css'>
.datatable table.frame { margin-bottom: 0; }
.datatable table.frame thead { border-bottom: none; }
.datatable table.frame tr.coltypes td {  color: #FFFFFF;  line-height: 6px;  padding: 0 0.5em;}
.datatable .bool    { background: #DDDD99; }
.datatable .object  { background: #565656; }
.datatable .int     { background: #5D9E5D; }
.datatable .float   { background: #4040CC; }
.datatable .str     { background: #CC4040; }
.datatable .time    { background: #40CC40; }
.datatable .row_index {  background: var(--jp-border-color3);  border-right: 1px solid var(--jp-border-color0);  color: var(--jp-ui-font-color3);  font-size: 9px;}
.datatable .frame tbody td { text-align: left; }
.datatable .frame tr.coltypes .row_index {  background: var(--jp-border-color0);}
.datatable th:nth-child(2) { padding-left: 12px; }
.datatable .hellipsis {  color: var(--jp-cell-editor-border-color);}
.datatable .vellipsis {  background: var(--jp-layout-color0);  color: var(--jp-cell-editor-border-color);}
.datatable .na {  color: var(--jp-cell-editor-border-color);  font-size: 80%;}
.datatable .sp {  opacity: 0.25;}
.datatable .footer { font-size: 9px; }
.datatable .frame_dimensions {  background: var(--jp-border-color3);  border-top: 1px solid var(--jp-border-color0);  color: var(--jp-ui-font-color3);  display: inline-block;  opacity: 0.6;  padding: 1px 10px 1px 5px;}
</style>


<pre>
array([[0.93183565, 0.06816435],
       [0.94422586, 0.05577414],
       [0.94985675, 0.05014325],
       ...,
       [0.98243161, 0.01756839],
       [0.96154284, 0.03845716],
       [0.96159952, 0.03840048]])
</pre>

```python
from catboost import CatBoostClassifier
cbc=CatBoostClassifier()
cbc.fit(train2,train["IsBadBuy"])
result=cbc.predict_proba(test2)
result
```

<pre>
Learning rate set to 0.064347
0:	learn: 0.6367740	total: 73.6ms	remaining: 1m 13s
1:	learn: 0.5871637	total: 89.9ms	remaining: 44.9s
2:	learn: 0.5455366	total: 105ms	remaining: 34.9s
3:	learn: 0.5101862	total: 120ms	remaining: 29.8s
4:	learn: 0.4815592	total: 137ms	remaining: 27.3s
5:	learn: 0.4568368	total: 152ms	remaining: 25.2s
6:	learn: 0.4357139	total: 169ms	remaining: 23.9s
7:	learn: 0.4175360	total: 186ms	remaining: 23s
8:	learn: 0.4021033	total: 202ms	remaining: 22.2s
9:	learn: 0.3887958	total: 216ms	remaining: 21.4s
10:	learn: 0.3775924	total: 232ms	remaining: 20.9s
11:	learn: 0.3678313	total: 248ms	remaining: 20.4s
12:	learn: 0.3591310	total: 265ms	remaining: 20.1s
13:	learn: 0.3518135	total: 281ms	remaining: 19.8s
14:	learn: 0.3455239	total: 297ms	remaining: 19.5s
15:	learn: 0.3403132	total: 311ms	remaining: 19.1s
16:	learn: 0.3360562	total: 327ms	remaining: 18.9s
17:	learn: 0.3317907	total: 343ms	remaining: 18.7s
18:	learn: 0.3281779	total: 358ms	remaining: 18.5s
19:	learn: 0.3253243	total: 372ms	remaining: 18.2s
20:	learn: 0.3227786	total: 387ms	remaining: 18.1s
21:	learn: 0.3203031	total: 405ms	remaining: 18s
22:	learn: 0.3181859	total: 421ms	remaining: 17.9s
23:	learn: 0.3163842	total: 437ms	remaining: 17.8s
24:	learn: 0.3148317	total: 454ms	remaining: 17.7s
25:	learn: 0.3132855	total: 469ms	remaining: 17.6s
26:	learn: 0.3123041	total: 481ms	remaining: 17.3s
27:	learn: 0.3110773	total: 496ms	remaining: 17.2s
28:	learn: 0.3101248	total: 513ms	remaining: 17.2s
29:	learn: 0.3092637	total: 528ms	remaining: 17.1s
30:	learn: 0.3083961	total: 544ms	remaining: 17s
31:	learn: 0.3077676	total: 560ms	remaining: 16.9s
32:	learn: 0.3070091	total: 577ms	remaining: 16.9s
33:	learn: 0.3063640	total: 593ms	remaining: 16.9s
34:	learn: 0.3057072	total: 611ms	remaining: 16.8s
35:	learn: 0.3050594	total: 627ms	remaining: 16.8s
36:	learn: 0.3044674	total: 643ms	remaining: 16.7s
37:	learn: 0.3039817	total: 660ms	remaining: 16.7s
38:	learn: 0.3036108	total: 676ms	remaining: 16.6s
39:	learn: 0.3031893	total: 693ms	remaining: 16.6s
40:	learn: 0.3027597	total: 709ms	remaining: 16.6s
41:	learn: 0.3023441	total: 726ms	remaining: 16.6s
42:	learn: 0.3019870	total: 742ms	remaining: 16.5s
43:	learn: 0.3015131	total: 758ms	remaining: 16.5s
44:	learn: 0.3012178	total: 775ms	remaining: 16.4s
45:	learn: 0.3009638	total: 791ms	remaining: 16.4s
46:	learn: 0.3004240	total: 810ms	remaining: 16.4s
47:	learn: 0.3001790	total: 826ms	remaining: 16.4s
48:	learn: 0.3000047	total: 840ms	remaining: 16.3s
49:	learn: 0.2996691	total: 857ms	remaining: 16.3s
50:	learn: 0.2994075	total: 873ms	remaining: 16.2s
51:	learn: 0.2992016	total: 890ms	remaining: 16.2s
52:	learn: 0.2989059	total: 903ms	remaining: 16.1s
53:	learn: 0.2987013	total: 919ms	remaining: 16.1s
54:	learn: 0.2984314	total: 935ms	remaining: 16.1s
55:	learn: 0.2982180	total: 951ms	remaining: 16s
56:	learn: 0.2980054	total: 968ms	remaining: 16s
57:	learn: 0.2978419	total: 985ms	remaining: 16s
58:	learn: 0.2977514	total: 1s	remaining: 16s
59:	learn: 0.2975154	total: 1.02s	remaining: 16s
60:	learn: 0.2972854	total: 1.04s	remaining: 16s
61:	learn: 0.2970779	total: 1.05s	remaining: 16s
62:	learn: 0.2968093	total: 1.07s	remaining: 15.9s
63:	learn: 0.2966240	total: 1.09s	remaining: 15.9s
64:	learn: 0.2965185	total: 1.1s	remaining: 15.8s
65:	learn: 0.2963564	total: 1.12s	remaining: 15.8s
66:	learn: 0.2961868	total: 1.13s	remaining: 15.8s
67:	learn: 0.2960255	total: 1.15s	remaining: 15.7s
68:	learn: 0.2958888	total: 1.17s	remaining: 15.7s
69:	learn: 0.2957561	total: 1.18s	remaining: 15.7s
70:	learn: 0.2956086	total: 1.2s	remaining: 15.7s
71:	learn: 0.2954820	total: 1.21s	remaining: 15.6s
72:	learn: 0.2953245	total: 1.23s	remaining: 15.6s
73:	learn: 0.2952357	total: 1.25s	remaining: 15.6s
74:	learn: 0.2951332	total: 1.26s	remaining: 15.6s
75:	learn: 0.2950303	total: 1.28s	remaining: 15.6s
76:	learn: 0.2949016	total: 1.3s	remaining: 15.5s
77:	learn: 0.2947430	total: 1.31s	remaining: 15.5s
78:	learn: 0.2946132	total: 1.33s	remaining: 15.5s
79:	learn: 0.2944816	total: 1.34s	remaining: 15.4s
80:	learn: 0.2943596	total: 1.35s	remaining: 15.4s
81:	learn: 0.2942446	total: 1.37s	remaining: 15.4s
82:	learn: 0.2941738	total: 1.39s	remaining: 15.3s
83:	learn: 0.2940342	total: 1.4s	remaining: 15.3s
84:	learn: 0.2939757	total: 1.42s	remaining: 15.3s
85:	learn: 0.2938679	total: 1.44s	remaining: 15.3s
86:	learn: 0.2936859	total: 1.45s	remaining: 15.3s
87:	learn: 0.2935973	total: 1.47s	remaining: 15.2s
88:	learn: 0.2934745	total: 1.49s	remaining: 15.2s
89:	learn: 0.2932761	total: 1.5s	remaining: 15.2s
90:	learn: 0.2931454	total: 1.52s	remaining: 15.2s
91:	learn: 0.2930547	total: 1.54s	remaining: 15.2s
92:	learn: 0.2929536	total: 1.55s	remaining: 15.1s
93:	learn: 0.2926903	total: 1.57s	remaining: 15.1s
94:	learn: 0.2925208	total: 1.58s	remaining: 15.1s
95:	learn: 0.2924756	total: 1.6s	remaining: 15.1s
96:	learn: 0.2923743	total: 1.61s	remaining: 15s
97:	learn: 0.2922919	total: 1.63s	remaining: 15s
98:	learn: 0.2921961	total: 1.65s	remaining: 15s
99:	learn: 0.2919096	total: 1.66s	remaining: 15s
100:	learn: 0.2917720	total: 1.68s	remaining: 14.9s
101:	learn: 0.2916888	total: 1.69s	remaining: 14.9s
102:	learn: 0.2915618	total: 1.71s	remaining: 14.9s
103:	learn: 0.2914690	total: 1.73s	remaining: 14.9s
104:	learn: 0.2913296	total: 1.74s	remaining: 14.8s
105:	learn: 0.2912246	total: 1.76s	remaining: 14.8s
106:	learn: 0.2911250	total: 1.77s	remaining: 14.8s
107:	learn: 0.2910302	total: 1.79s	remaining: 14.8s
108:	learn: 0.2909069	total: 1.8s	remaining: 14.7s
109:	learn: 0.2907113	total: 1.82s	remaining: 14.7s
110:	learn: 0.2905524	total: 1.84s	remaining: 14.7s
111:	learn: 0.2904276	total: 1.85s	remaining: 14.7s
112:	learn: 0.2903334	total: 1.87s	remaining: 14.7s
113:	learn: 0.2902263	total: 1.89s	remaining: 14.7s
114:	learn: 0.2900877	total: 1.9s	remaining: 14.7s
115:	learn: 0.2899951	total: 1.92s	remaining: 14.6s
116:	learn: 0.2898966	total: 1.94s	remaining: 14.6s
117:	learn: 0.2897453	total: 1.95s	remaining: 14.6s
118:	learn: 0.2896347	total: 1.97s	remaining: 14.6s
119:	learn: 0.2895645	total: 1.99s	remaining: 14.6s
120:	learn: 0.2894453	total: 2s	remaining: 14.5s
121:	learn: 0.2893676	total: 2.02s	remaining: 14.5s
122:	learn: 0.2892071	total: 2.03s	remaining: 14.5s
123:	learn: 0.2891154	total: 2.05s	remaining: 14.5s
124:	learn: 0.2890169	total: 2.07s	remaining: 14.5s
125:	learn: 0.2888748	total: 2.08s	remaining: 14.4s
126:	learn: 0.2887713	total: 2.1s	remaining: 14.4s
127:	learn: 0.2886907	total: 2.11s	remaining: 14.4s
128:	learn: 0.2886069	total: 2.13s	remaining: 14.4s
129:	learn: 0.2884777	total: 2.15s	remaining: 14.4s
130:	learn: 0.2883427	total: 2.16s	remaining: 14.3s
131:	learn: 0.2882574	total: 2.18s	remaining: 14.3s
132:	learn: 0.2881594	total: 2.19s	remaining: 14.3s
133:	learn: 0.2880363	total: 2.21s	remaining: 14.3s
134:	learn: 0.2879930	total: 2.22s	remaining: 14.3s
135:	learn: 0.2879283	total: 2.24s	remaining: 14.2s
136:	learn: 0.2878263	total: 2.25s	remaining: 14.2s
137:	learn: 0.2877293	total: 2.27s	remaining: 14.2s
138:	learn: 0.2875863	total: 2.29s	remaining: 14.2s
139:	learn: 0.2875219	total: 2.31s	remaining: 14.2s
140:	learn: 0.2874079	total: 2.32s	remaining: 14.2s
141:	learn: 0.2873319	total: 2.34s	remaining: 14.1s
142:	learn: 0.2872615	total: 2.36s	remaining: 14.1s
143:	learn: 0.2871720	total: 2.37s	remaining: 14.1s
144:	learn: 0.2870929	total: 2.39s	remaining: 14.1s
145:	learn: 0.2870061	total: 2.41s	remaining: 14.1s
146:	learn: 0.2869414	total: 2.42s	remaining: 14.1s
147:	learn: 0.2868519	total: 2.44s	remaining: 14.1s
148:	learn: 0.2867462	total: 2.46s	remaining: 14s
149:	learn: 0.2866485	total: 2.47s	remaining: 14s
150:	learn: 0.2866025	total: 2.49s	remaining: 14s
151:	learn: 0.2865056	total: 2.5s	remaining: 14s
152:	learn: 0.2864071	total: 2.52s	remaining: 13.9s
153:	learn: 0.2863169	total: 2.53s	remaining: 13.9s
154:	learn: 0.2861996	total: 2.55s	remaining: 13.9s
155:	learn: 0.2860403	total: 2.57s	remaining: 13.9s
156:	learn: 0.2859220	total: 2.59s	remaining: 13.9s
157:	learn: 0.2857999	total: 2.6s	remaining: 13.9s
158:	learn: 0.2857177	total: 2.62s	remaining: 13.8s
159:	learn: 0.2856568	total: 2.63s	remaining: 13.8s
160:	learn: 0.2855463	total: 2.65s	remaining: 13.8s
161:	learn: 0.2854722	total: 2.67s	remaining: 13.8s
162:	learn: 0.2853894	total: 2.68s	remaining: 13.8s
163:	learn: 0.2852839	total: 2.7s	remaining: 13.8s
164:	learn: 0.2852266	total: 2.71s	remaining: 13.7s
165:	learn: 0.2851337	total: 2.73s	remaining: 13.7s
166:	learn: 0.2850722	total: 2.75s	remaining: 13.7s
167:	learn: 0.2850164	total: 2.76s	remaining: 13.7s
168:	learn: 0.2849418	total: 2.77s	remaining: 13.6s
169:	learn: 0.2848289	total: 2.79s	remaining: 13.6s
170:	learn: 0.2847026	total: 2.81s	remaining: 13.6s
171:	learn: 0.2845557	total: 2.82s	remaining: 13.6s
172:	learn: 0.2843939	total: 2.84s	remaining: 13.6s
173:	learn: 0.2843159	total: 2.86s	remaining: 13.6s
174:	learn: 0.2842261	total: 2.87s	remaining: 13.5s
175:	learn: 0.2841492	total: 2.89s	remaining: 13.5s
176:	learn: 0.2840947	total: 2.9s	remaining: 13.5s
177:	learn: 0.2839587	total: 2.92s	remaining: 13.5s
178:	learn: 0.2838827	total: 2.94s	remaining: 13.5s
179:	learn: 0.2838191	total: 2.95s	remaining: 13.4s
180:	learn: 0.2837607	total: 2.96s	remaining: 13.4s
181:	learn: 0.2836664	total: 2.98s	remaining: 13.4s
182:	learn: 0.2835530	total: 3s	remaining: 13.4s
183:	learn: 0.2835033	total: 3.01s	remaining: 13.4s
184:	learn: 0.2834562	total: 3.03s	remaining: 13.3s
185:	learn: 0.2833630	total: 3.04s	remaining: 13.3s
186:	learn: 0.2832499	total: 3.06s	remaining: 13.3s
187:	learn: 0.2831505	total: 3.07s	remaining: 13.3s
188:	learn: 0.2830464	total: 3.09s	remaining: 13.3s
189:	learn: 0.2829427	total: 3.11s	remaining: 13.2s
190:	learn: 0.2828629	total: 3.12s	remaining: 13.2s
191:	learn: 0.2827666	total: 3.14s	remaining: 13.2s
192:	learn: 0.2827031	total: 3.15s	remaining: 13.2s
193:	learn: 0.2826266	total: 3.17s	remaining: 13.2s
194:	learn: 0.2825255	total: 3.18s	remaining: 13.1s
195:	learn: 0.2824368	total: 3.2s	remaining: 13.1s
196:	learn: 0.2823582	total: 3.21s	remaining: 13.1s
197:	learn: 0.2822642	total: 3.23s	remaining: 13.1s
198:	learn: 0.2821969	total: 3.25s	remaining: 13.1s
199:	learn: 0.2821304	total: 3.26s	remaining: 13s
200:	learn: 0.2820762	total: 3.27s	remaining: 13s
201:	learn: 0.2819979	total: 3.29s	remaining: 13s
202:	learn: 0.2819116	total: 3.31s	remaining: 13s
203:	learn: 0.2818417	total: 3.32s	remaining: 13s
204:	learn: 0.2817297	total: 3.34s	remaining: 13s
205:	learn: 0.2816361	total: 3.35s	remaining: 12.9s
206:	learn: 0.2815351	total: 3.37s	remaining: 12.9s
207:	learn: 0.2814404	total: 3.39s	remaining: 12.9s
208:	learn: 0.2813468	total: 3.4s	remaining: 12.9s
209:	learn: 0.2812763	total: 3.42s	remaining: 12.9s
210:	learn: 0.2812133	total: 3.45s	remaining: 12.9s
211:	learn: 0.2810693	total: 3.47s	remaining: 12.9s
212:	learn: 0.2809837	total: 3.5s	remaining: 12.9s
213:	learn: 0.2808954	total: 3.52s	remaining: 12.9s
214:	learn: 0.2807696	total: 3.55s	remaining: 13s
215:	learn: 0.2806858	total: 3.58s	remaining: 13s
216:	learn: 0.2806084	total: 3.59s	remaining: 13s
217:	learn: 0.2805335	total: 3.61s	remaining: 12.9s
218:	learn: 0.2804477	total: 3.62s	remaining: 12.9s
219:	learn: 0.2803604	total: 3.64s	remaining: 12.9s
220:	learn: 0.2802881	total: 3.65s	remaining: 12.9s
221:	learn: 0.2802086	total: 3.67s	remaining: 12.9s
222:	learn: 0.2801245	total: 3.68s	remaining: 12.8s
223:	learn: 0.2800425	total: 3.7s	remaining: 12.8s
224:	learn: 0.2799789	total: 3.71s	remaining: 12.8s
225:	learn: 0.2798982	total: 3.73s	remaining: 12.8s
226:	learn: 0.2798281	total: 3.75s	remaining: 12.8s
227:	learn: 0.2797343	total: 3.76s	remaining: 12.7s
228:	learn: 0.2796709	total: 3.77s	remaining: 12.7s
229:	learn: 0.2795983	total: 3.79s	remaining: 12.7s
230:	learn: 0.2795424	total: 3.81s	remaining: 12.7s
231:	learn: 0.2794466	total: 3.82s	remaining: 12.6s
232:	learn: 0.2793515	total: 3.83s	remaining: 12.6s
233:	learn: 0.2792748	total: 3.85s	remaining: 12.6s
234:	learn: 0.2791736	total: 3.87s	remaining: 12.6s
235:	learn: 0.2790849	total: 3.88s	remaining: 12.6s
236:	learn: 0.2790105	total: 3.9s	remaining: 12.5s
237:	learn: 0.2789003	total: 3.91s	remaining: 12.5s
238:	learn: 0.2788288	total: 3.93s	remaining: 12.5s
239:	learn: 0.2787678	total: 3.94s	remaining: 12.5s
240:	learn: 0.2786446	total: 3.96s	remaining: 12.5s
241:	learn: 0.2785355	total: 3.98s	remaining: 12.5s
242:	learn: 0.2784385	total: 3.99s	remaining: 12.4s
243:	learn: 0.2783510	total: 4.01s	remaining: 12.4s
244:	learn: 0.2782716	total: 4.02s	remaining: 12.4s
245:	learn: 0.2781931	total: 4.04s	remaining: 12.4s
246:	learn: 0.2781043	total: 4.05s	remaining: 12.4s
247:	learn: 0.2780329	total: 4.07s	remaining: 12.3s
248:	learn: 0.2779421	total: 4.08s	remaining: 12.3s
249:	learn: 0.2778281	total: 4.1s	remaining: 12.3s
250:	learn: 0.2777536	total: 4.12s	remaining: 12.3s
251:	learn: 0.2776287	total: 4.13s	remaining: 12.3s
252:	learn: 0.2775453	total: 4.15s	remaining: 12.3s
253:	learn: 0.2774786	total: 4.16s	remaining: 12.2s
254:	learn: 0.2773995	total: 4.18s	remaining: 12.2s
255:	learn: 0.2773099	total: 4.2s	remaining: 12.2s
256:	learn: 0.2772094	total: 4.21s	remaining: 12.2s
257:	learn: 0.2771549	total: 4.23s	remaining: 12.2s
258:	learn: 0.2770514	total: 4.25s	remaining: 12.1s
259:	learn: 0.2769360	total: 4.26s	remaining: 12.1s
260:	learn: 0.2768463	total: 4.28s	remaining: 12.1s
261:	learn: 0.2767520	total: 4.29s	remaining: 12.1s
262:	learn: 0.2766458	total: 4.31s	remaining: 12.1s
263:	learn: 0.2765751	total: 4.33s	remaining: 12.1s
264:	learn: 0.2764089	total: 4.34s	remaining: 12s
265:	learn: 0.2763166	total: 4.36s	remaining: 12s
266:	learn: 0.2761943	total: 4.37s	remaining: 12s
267:	learn: 0.2761292	total: 4.39s	remaining: 12s
268:	learn: 0.2760539	total: 4.4s	remaining: 12s
269:	learn: 0.2759867	total: 4.42s	remaining: 11.9s
270:	learn: 0.2758862	total: 4.43s	remaining: 11.9s
271:	learn: 0.2758349	total: 4.45s	remaining: 11.9s
272:	learn: 0.2757401	total: 4.47s	remaining: 11.9s
273:	learn: 0.2756792	total: 4.48s	remaining: 11.9s
274:	learn: 0.2756160	total: 4.5s	remaining: 11.9s
275:	learn: 0.2754996	total: 4.51s	remaining: 11.8s
276:	learn: 0.2754050	total: 4.53s	remaining: 11.8s
277:	learn: 0.2753478	total: 4.54s	remaining: 11.8s
278:	learn: 0.2752844	total: 4.56s	remaining: 11.8s
279:	learn: 0.2751984	total: 4.57s	remaining: 11.8s
280:	learn: 0.2751149	total: 4.59s	remaining: 11.7s
281:	learn: 0.2750399	total: 4.6s	remaining: 11.7s
282:	learn: 0.2749680	total: 4.62s	remaining: 11.7s
283:	learn: 0.2749063	total: 4.63s	remaining: 11.7s
284:	learn: 0.2748506	total: 4.65s	remaining: 11.7s
285:	learn: 0.2747742	total: 4.67s	remaining: 11.6s
286:	learn: 0.2747131	total: 4.68s	remaining: 11.6s
287:	learn: 0.2746246	total: 4.69s	remaining: 11.6s
288:	learn: 0.2745668	total: 4.71s	remaining: 11.6s
289:	learn: 0.2744973	total: 4.72s	remaining: 11.6s
290:	learn: 0.2744224	total: 4.74s	remaining: 11.6s
291:	learn: 0.2743655	total: 4.75s	remaining: 11.5s
292:	learn: 0.2742939	total: 4.77s	remaining: 11.5s
293:	learn: 0.2742129	total: 4.79s	remaining: 11.5s
294:	learn: 0.2741448	total: 4.8s	remaining: 11.5s
295:	learn: 0.2740707	total: 4.82s	remaining: 11.5s
296:	learn: 0.2739887	total: 4.83s	remaining: 11.4s
297:	learn: 0.2739269	total: 4.85s	remaining: 11.4s
298:	learn: 0.2738713	total: 4.86s	remaining: 11.4s
299:	learn: 0.2738133	total: 4.88s	remaining: 11.4s
300:	learn: 0.2737403	total: 4.89s	remaining: 11.4s
301:	learn: 0.2736643	total: 4.91s	remaining: 11.3s
302:	learn: 0.2735894	total: 4.92s	remaining: 11.3s
303:	learn: 0.2735095	total: 4.94s	remaining: 11.3s
304:	learn: 0.2734553	total: 4.96s	remaining: 11.3s
305:	learn: 0.2733726	total: 4.97s	remaining: 11.3s
306:	learn: 0.2732678	total: 4.99s	remaining: 11.3s
307:	learn: 0.2731787	total: 5.01s	remaining: 11.2s
308:	learn: 0.2730568	total: 5.02s	remaining: 11.2s
309:	learn: 0.2729750	total: 5.04s	remaining: 11.2s
310:	learn: 0.2729081	total: 5.06s	remaining: 11.2s
311:	learn: 0.2728186	total: 5.07s	remaining: 11.2s
312:	learn: 0.2727324	total: 5.09s	remaining: 11.2s
313:	learn: 0.2726531	total: 5.1s	remaining: 11.2s
314:	learn: 0.2725783	total: 5.12s	remaining: 11.1s
315:	learn: 0.2724999	total: 5.14s	remaining: 11.1s
316:	learn: 0.2724337	total: 5.15s	remaining: 11.1s
317:	learn: 0.2723379	total: 5.17s	remaining: 11.1s
318:	learn: 0.2722708	total: 5.19s	remaining: 11.1s
319:	learn: 0.2722093	total: 5.2s	remaining: 11.1s
320:	learn: 0.2721523	total: 5.22s	remaining: 11s
321:	learn: 0.2720796	total: 5.24s	remaining: 11s
322:	learn: 0.2720204	total: 5.25s	remaining: 11s
323:	learn: 0.2719472	total: 5.27s	remaining: 11s
324:	learn: 0.2718842	total: 5.28s	remaining: 11s
325:	learn: 0.2718088	total: 5.3s	remaining: 11s
326:	learn: 0.2717284	total: 5.31s	remaining: 10.9s
327:	learn: 0.2716705	total: 5.33s	remaining: 10.9s
328:	learn: 0.2716123	total: 5.34s	remaining: 10.9s
329:	learn: 0.2715490	total: 5.36s	remaining: 10.9s
330:	learn: 0.2714682	total: 5.38s	remaining: 10.9s
331:	learn: 0.2714121	total: 5.39s	remaining: 10.8s
332:	learn: 0.2713650	total: 5.41s	remaining: 10.8s
333:	learn: 0.2713088	total: 5.42s	remaining: 10.8s
334:	learn: 0.2712514	total: 5.44s	remaining: 10.8s
335:	learn: 0.2711752	total: 5.45s	remaining: 10.8s
336:	learn: 0.2710750	total: 5.47s	remaining: 10.8s
337:	learn: 0.2710196	total: 5.48s	remaining: 10.7s
338:	learn: 0.2709518	total: 5.5s	remaining: 10.7s
339:	learn: 0.2708802	total: 5.52s	remaining: 10.7s
340:	learn: 0.2707964	total: 5.53s	remaining: 10.7s
341:	learn: 0.2707310	total: 5.55s	remaining: 10.7s
342:	learn: 0.2706615	total: 5.56s	remaining: 10.7s
343:	learn: 0.2705928	total: 5.58s	remaining: 10.6s
344:	learn: 0.2705353	total: 5.59s	remaining: 10.6s
345:	learn: 0.2704465	total: 5.61s	remaining: 10.6s
346:	learn: 0.2704120	total: 5.62s	remaining: 10.6s
347:	learn: 0.2703193	total: 5.64s	remaining: 10.6s
348:	learn: 0.2702112	total: 5.66s	remaining: 10.5s
349:	learn: 0.2701318	total: 5.67s	remaining: 10.5s
350:	learn: 0.2700764	total: 5.69s	remaining: 10.5s
351:	learn: 0.2700397	total: 5.7s	remaining: 10.5s
352:	learn: 0.2699798	total: 5.72s	remaining: 10.5s
353:	learn: 0.2699065	total: 5.73s	remaining: 10.5s
354:	learn: 0.2698586	total: 5.75s	remaining: 10.4s
355:	learn: 0.2697941	total: 5.76s	remaining: 10.4s
356:	learn: 0.2697302	total: 5.78s	remaining: 10.4s
357:	learn: 0.2696913	total: 5.79s	remaining: 10.4s
358:	learn: 0.2696055	total: 5.81s	remaining: 10.4s
359:	learn: 0.2695426	total: 5.83s	remaining: 10.4s
360:	learn: 0.2694735	total: 5.84s	remaining: 10.3s
361:	learn: 0.2693959	total: 5.86s	remaining: 10.3s
362:	learn: 0.2693380	total: 5.87s	remaining: 10.3s
363:	learn: 0.2692876	total: 5.89s	remaining: 10.3s
364:	learn: 0.2691841	total: 5.9s	remaining: 10.3s
365:	learn: 0.2690857	total: 5.92s	remaining: 10.2s
366:	learn: 0.2690517	total: 5.93s	remaining: 10.2s
367:	learn: 0.2689755	total: 5.94s	remaining: 10.2s
368:	learn: 0.2689208	total: 5.96s	remaining: 10.2s
369:	learn: 0.2688347	total: 5.98s	remaining: 10.2s
370:	learn: 0.2687486	total: 5.99s	remaining: 10.2s
371:	learn: 0.2686779	total: 6.01s	remaining: 10.1s
372:	learn: 0.2686239	total: 6.02s	remaining: 10.1s
373:	learn: 0.2685302	total: 6.04s	remaining: 10.1s
374:	learn: 0.2684523	total: 6.05s	remaining: 10.1s
375:	learn: 0.2683561	total: 6.07s	remaining: 10.1s
376:	learn: 0.2683142	total: 6.08s	remaining: 10.1s
377:	learn: 0.2682465	total: 6.1s	remaining: 10s
378:	learn: 0.2681911	total: 6.12s	remaining: 10s
379:	learn: 0.2681350	total: 6.13s	remaining: 10s
380:	learn: 0.2680711	total: 6.15s	remaining: 9.99s
381:	learn: 0.2680322	total: 6.17s	remaining: 9.97s
382:	learn: 0.2679882	total: 6.18s	remaining: 9.96s
383:	learn: 0.2679125	total: 6.2s	remaining: 9.94s
384:	learn: 0.2678654	total: 6.21s	remaining: 9.92s
385:	learn: 0.2677973	total: 6.23s	remaining: 9.91s
386:	learn: 0.2677504	total: 6.25s	remaining: 9.89s
387:	learn: 0.2676374	total: 6.26s	remaining: 9.88s
388:	learn: 0.2675774	total: 6.28s	remaining: 9.86s
389:	learn: 0.2674779	total: 6.29s	remaining: 9.84s
390:	learn: 0.2674085	total: 6.31s	remaining: 9.83s
391:	learn: 0.2673457	total: 6.33s	remaining: 9.81s
392:	learn: 0.2672438	total: 6.34s	remaining: 9.79s
393:	learn: 0.2671695	total: 6.36s	remaining: 9.78s
394:	learn: 0.2671008	total: 6.37s	remaining: 9.76s
395:	learn: 0.2670526	total: 6.39s	remaining: 9.75s
396:	learn: 0.2669889	total: 6.41s	remaining: 9.73s
397:	learn: 0.2669222	total: 6.42s	remaining: 9.71s
398:	learn: 0.2668539	total: 6.44s	remaining: 9.7s
399:	learn: 0.2667903	total: 6.45s	remaining: 9.68s
400:	learn: 0.2666868	total: 6.47s	remaining: 9.67s
401:	learn: 0.2666365	total: 6.49s	remaining: 9.65s
402:	learn: 0.2665676	total: 6.5s	remaining: 9.63s
403:	learn: 0.2664609	total: 6.52s	remaining: 9.62s
404:	learn: 0.2664024	total: 6.54s	remaining: 9.6s
405:	learn: 0.2663612	total: 6.55s	remaining: 9.58s
406:	learn: 0.2662998	total: 6.57s	remaining: 9.57s
407:	learn: 0.2662481	total: 6.58s	remaining: 9.55s
408:	learn: 0.2661919	total: 6.6s	remaining: 9.54s
409:	learn: 0.2661165	total: 6.62s	remaining: 9.52s
410:	learn: 0.2660725	total: 6.63s	remaining: 9.5s
411:	learn: 0.2660039	total: 6.64s	remaining: 9.48s
412:	learn: 0.2659110	total: 6.66s	remaining: 9.47s
413:	learn: 0.2658280	total: 6.68s	remaining: 9.45s
414:	learn: 0.2657535	total: 6.7s	remaining: 9.44s
415:	learn: 0.2656980	total: 6.71s	remaining: 9.42s
416:	learn: 0.2655933	total: 6.73s	remaining: 9.41s
417:	learn: 0.2655010	total: 6.74s	remaining: 9.39s
418:	learn: 0.2654414	total: 6.76s	remaining: 9.38s
419:	learn: 0.2653452	total: 6.78s	remaining: 9.36s
420:	learn: 0.2652406	total: 6.79s	remaining: 9.35s
421:	learn: 0.2651907	total: 6.81s	remaining: 9.33s
422:	learn: 0.2651238	total: 6.83s	remaining: 9.31s
423:	learn: 0.2650505	total: 6.84s	remaining: 9.3s
424:	learn: 0.2649976	total: 6.86s	remaining: 9.28s
425:	learn: 0.2649306	total: 6.88s	remaining: 9.26s
426:	learn: 0.2648726	total: 6.89s	remaining: 9.25s
427:	learn: 0.2648103	total: 6.91s	remaining: 9.23s
428:	learn: 0.2647418	total: 6.92s	remaining: 9.21s
429:	learn: 0.2646156	total: 6.94s	remaining: 9.2s
430:	learn: 0.2645422	total: 6.96s	remaining: 9.18s
431:	learn: 0.2644924	total: 6.97s	remaining: 9.16s
432:	learn: 0.2644238	total: 6.99s	remaining: 9.15s
433:	learn: 0.2643715	total: 7s	remaining: 9.13s
434:	learn: 0.2643091	total: 7.02s	remaining: 9.11s
435:	learn: 0.2642284	total: 7.03s	remaining: 9.1s
436:	learn: 0.2641529	total: 7.05s	remaining: 9.08s
437:	learn: 0.2640620	total: 7.06s	remaining: 9.06s
438:	learn: 0.2639762	total: 7.08s	remaining: 9.05s
439:	learn: 0.2639231	total: 7.1s	remaining: 9.03s
440:	learn: 0.2638622	total: 7.11s	remaining: 9.01s
441:	learn: 0.2637926	total: 7.13s	remaining: 9s
442:	learn: 0.2637129	total: 7.14s	remaining: 8.98s
443:	learn: 0.2636744	total: 7.16s	remaining: 8.97s
444:	learn: 0.2636070	total: 7.18s	remaining: 8.95s
445:	learn: 0.2635248	total: 7.19s	remaining: 8.93s
446:	learn: 0.2634796	total: 7.21s	remaining: 8.92s
447:	learn: 0.2634187	total: 7.22s	remaining: 8.9s
448:	learn: 0.2633428	total: 7.24s	remaining: 8.88s
449:	learn: 0.2632875	total: 7.26s	remaining: 8.87s
450:	learn: 0.2632211	total: 7.27s	remaining: 8.85s
451:	learn: 0.2631740	total: 7.29s	remaining: 8.84s
452:	learn: 0.2631097	total: 7.3s	remaining: 8.82s
453:	learn: 0.2630652	total: 7.32s	remaining: 8.8s
454:	learn: 0.2630253	total: 7.33s	remaining: 8.79s
455:	learn: 0.2629455	total: 7.35s	remaining: 8.77s
456:	learn: 0.2629033	total: 7.36s	remaining: 8.75s
457:	learn: 0.2628236	total: 7.38s	remaining: 8.73s
458:	learn: 0.2627803	total: 7.39s	remaining: 8.72s
459:	learn: 0.2627242	total: 7.41s	remaining: 8.7s
460:	learn: 0.2626654	total: 7.43s	remaining: 8.68s
461:	learn: 0.2625959	total: 7.44s	remaining: 8.67s
462:	learn: 0.2625441	total: 7.46s	remaining: 8.65s
463:	learn: 0.2624894	total: 7.47s	remaining: 8.63s
464:	learn: 0.2624505	total: 7.49s	remaining: 8.62s
465:	learn: 0.2623811	total: 7.5s	remaining: 8.6s
466:	learn: 0.2623134	total: 7.52s	remaining: 8.58s
467:	learn: 0.2622515	total: 7.53s	remaining: 8.56s
468:	learn: 0.2621890	total: 7.55s	remaining: 8.55s
469:	learn: 0.2621393	total: 7.56s	remaining: 8.53s
470:	learn: 0.2620324	total: 7.58s	remaining: 8.52s
471:	learn: 0.2619843	total: 7.6s	remaining: 8.5s
472:	learn: 0.2619138	total: 7.61s	remaining: 8.48s
473:	learn: 0.2618525	total: 7.63s	remaining: 8.46s
474:	learn: 0.2618113	total: 7.64s	remaining: 8.45s
475:	learn: 0.2617414	total: 7.66s	remaining: 8.43s
476:	learn: 0.2616810	total: 7.67s	remaining: 8.41s
477:	learn: 0.2616278	total: 7.69s	remaining: 8.4s
478:	learn: 0.2615514	total: 7.71s	remaining: 8.38s
479:	learn: 0.2614888	total: 7.72s	remaining: 8.36s
480:	learn: 0.2614208	total: 7.73s	remaining: 8.35s
481:	learn: 0.2613491	total: 7.75s	remaining: 8.33s
482:	learn: 0.2612725	total: 7.77s	remaining: 8.31s
483:	learn: 0.2611978	total: 7.78s	remaining: 8.3s
484:	learn: 0.2611483	total: 7.8s	remaining: 8.28s
485:	learn: 0.2610895	total: 7.81s	remaining: 8.27s
486:	learn: 0.2610188	total: 7.83s	remaining: 8.25s
487:	learn: 0.2609513	total: 7.85s	remaining: 8.23s
488:	learn: 0.2608849	total: 7.86s	remaining: 8.22s
489:	learn: 0.2607943	total: 7.88s	remaining: 8.2s
490:	learn: 0.2607552	total: 7.89s	remaining: 8.18s
491:	learn: 0.2606838	total: 7.91s	remaining: 8.16s
492:	learn: 0.2606334	total: 7.92s	remaining: 8.15s
493:	learn: 0.2605547	total: 7.94s	remaining: 8.13s
494:	learn: 0.2604711	total: 7.95s	remaining: 8.12s
495:	learn: 0.2603889	total: 7.97s	remaining: 8.1s
496:	learn: 0.2603036	total: 7.99s	remaining: 8.08s
497:	learn: 0.2602275	total: 8s	remaining: 8.07s
498:	learn: 0.2601639	total: 8.02s	remaining: 8.05s
499:	learn: 0.2601099	total: 8.04s	remaining: 8.04s
500:	learn: 0.2600288	total: 8.05s	remaining: 8.02s
501:	learn: 0.2599775	total: 8.07s	remaining: 8s
502:	learn: 0.2598892	total: 8.09s	remaining: 7.99s
503:	learn: 0.2598517	total: 8.1s	remaining: 7.97s
504:	learn: 0.2597946	total: 8.12s	remaining: 7.96s
505:	learn: 0.2597280	total: 8.13s	remaining: 7.94s
506:	learn: 0.2596854	total: 8.15s	remaining: 7.92s
507:	learn: 0.2596441	total: 8.16s	remaining: 7.9s
508:	learn: 0.2595815	total: 8.18s	remaining: 7.89s
509:	learn: 0.2594902	total: 8.19s	remaining: 7.87s
510:	learn: 0.2594481	total: 8.21s	remaining: 7.86s
511:	learn: 0.2593979	total: 8.22s	remaining: 7.84s
512:	learn: 0.2593503	total: 8.24s	remaining: 7.82s
513:	learn: 0.2593000	total: 8.26s	remaining: 7.81s
514:	learn: 0.2592295	total: 8.27s	remaining: 7.79s
515:	learn: 0.2591718	total: 8.29s	remaining: 7.77s
516:	learn: 0.2591291	total: 8.3s	remaining: 7.76s
517:	learn: 0.2590575	total: 8.32s	remaining: 7.74s
518:	learn: 0.2589963	total: 8.33s	remaining: 7.72s
519:	learn: 0.2589426	total: 8.35s	remaining: 7.71s
520:	learn: 0.2588663	total: 8.37s	remaining: 7.69s
521:	learn: 0.2588468	total: 8.38s	remaining: 7.67s
522:	learn: 0.2588018	total: 8.39s	remaining: 7.66s
523:	learn: 0.2587448	total: 8.41s	remaining: 7.64s
524:	learn: 0.2586667	total: 8.42s	remaining: 7.62s
525:	learn: 0.2586132	total: 8.44s	remaining: 7.61s
526:	learn: 0.2585781	total: 8.46s	remaining: 7.59s
527:	learn: 0.2584897	total: 8.47s	remaining: 7.57s
528:	learn: 0.2584036	total: 8.49s	remaining: 7.56s
529:	learn: 0.2583329	total: 8.51s	remaining: 7.54s
530:	learn: 0.2582812	total: 8.52s	remaining: 7.53s
531:	learn: 0.2582397	total: 8.54s	remaining: 7.51s
532:	learn: 0.2581866	total: 8.55s	remaining: 7.49s
533:	learn: 0.2581293	total: 8.57s	remaining: 7.48s
534:	learn: 0.2580835	total: 8.59s	remaining: 7.46s
535:	learn: 0.2580087	total: 8.6s	remaining: 7.45s
536:	learn: 0.2579528	total: 8.62s	remaining: 7.43s
537:	learn: 0.2578934	total: 8.63s	remaining: 7.42s
538:	learn: 0.2578167	total: 8.65s	remaining: 7.4s
539:	learn: 0.2577308	total: 8.67s	remaining: 7.39s
540:	learn: 0.2576821	total: 8.69s	remaining: 7.37s
541:	learn: 0.2576146	total: 8.7s	remaining: 7.35s
542:	learn: 0.2575652	total: 8.72s	remaining: 7.34s
543:	learn: 0.2575307	total: 8.73s	remaining: 7.32s
544:	learn: 0.2574773	total: 8.75s	remaining: 7.3s
545:	learn: 0.2573982	total: 8.77s	remaining: 7.29s
546:	learn: 0.2573002	total: 8.79s	remaining: 7.28s
547:	learn: 0.2572171	total: 8.8s	remaining: 7.26s
548:	learn: 0.2571440	total: 8.82s	remaining: 7.24s
549:	learn: 0.2571064	total: 8.83s	remaining: 7.23s
550:	learn: 0.2570360	total: 8.85s	remaining: 7.21s
551:	learn: 0.2569874	total: 8.87s	remaining: 7.2s
552:	learn: 0.2569337	total: 8.88s	remaining: 7.18s
553:	learn: 0.2568792	total: 8.9s	remaining: 7.16s
554:	learn: 0.2567951	total: 8.91s	remaining: 7.15s
555:	learn: 0.2567268	total: 8.93s	remaining: 7.13s
556:	learn: 0.2566784	total: 8.94s	remaining: 7.11s
557:	learn: 0.2566192	total: 8.96s	remaining: 7.1s
558:	learn: 0.2565734	total: 8.98s	remaining: 7.08s
559:	learn: 0.2565084	total: 8.99s	remaining: 7.07s
560:	learn: 0.2564582	total: 9.01s	remaining: 7.05s
561:	learn: 0.2564074	total: 9.03s	remaining: 7.04s
562:	learn: 0.2563597	total: 9.04s	remaining: 7.02s
563:	learn: 0.2562799	total: 9.06s	remaining: 7s
564:	learn: 0.2562080	total: 9.08s	remaining: 6.99s
565:	learn: 0.2561701	total: 9.09s	remaining: 6.97s
566:	learn: 0.2561329	total: 9.11s	remaining: 6.95s
567:	learn: 0.2560750	total: 9.12s	remaining: 6.94s
568:	learn: 0.2560088	total: 9.14s	remaining: 6.92s
569:	learn: 0.2559738	total: 9.15s	remaining: 6.9s
570:	learn: 0.2559419	total: 9.16s	remaining: 6.89s
571:	learn: 0.2558794	total: 9.18s	remaining: 6.87s
572:	learn: 0.2557841	total: 9.2s	remaining: 6.85s
573:	learn: 0.2556974	total: 9.21s	remaining: 6.84s
574:	learn: 0.2556349	total: 9.23s	remaining: 6.82s
575:	learn: 0.2555608	total: 9.24s	remaining: 6.8s
576:	learn: 0.2555069	total: 9.26s	remaining: 6.79s
577:	learn: 0.2554422	total: 9.28s	remaining: 6.78s
578:	learn: 0.2553754	total: 9.29s	remaining: 6.76s
579:	learn: 0.2553311	total: 9.31s	remaining: 6.74s
580:	learn: 0.2552736	total: 9.33s	remaining: 6.73s
581:	learn: 0.2551739	total: 9.35s	remaining: 6.71s
582:	learn: 0.2551338	total: 9.36s	remaining: 6.7s
583:	learn: 0.2550903	total: 9.38s	remaining: 6.68s
584:	learn: 0.2550461	total: 9.39s	remaining: 6.66s
585:	learn: 0.2549895	total: 9.41s	remaining: 6.65s
586:	learn: 0.2549471	total: 9.42s	remaining: 6.63s
587:	learn: 0.2548805	total: 9.44s	remaining: 6.62s
588:	learn: 0.2548039	total: 9.46s	remaining: 6.6s
589:	learn: 0.2547457	total: 9.47s	remaining: 6.58s
590:	learn: 0.2546835	total: 9.49s	remaining: 6.57s
591:	learn: 0.2546319	total: 9.5s	remaining: 6.55s
592:	learn: 0.2545732	total: 9.52s	remaining: 6.53s
593:	learn: 0.2545252	total: 9.53s	remaining: 6.51s
594:	learn: 0.2544835	total: 9.55s	remaining: 6.5s
595:	learn: 0.2544163	total: 9.56s	remaining: 6.48s
596:	learn: 0.2543484	total: 9.58s	remaining: 6.47s
597:	learn: 0.2542916	total: 9.59s	remaining: 6.45s
598:	learn: 0.2542190	total: 9.61s	remaining: 6.43s
599:	learn: 0.2541377	total: 9.63s	remaining: 6.42s
600:	learn: 0.2541008	total: 9.64s	remaining: 6.4s
601:	learn: 0.2540451	total: 9.66s	remaining: 6.38s
602:	learn: 0.2539586	total: 9.68s	remaining: 6.37s
603:	learn: 0.2538920	total: 9.69s	remaining: 6.35s
604:	learn: 0.2538114	total: 9.71s	remaining: 6.34s
605:	learn: 0.2537632	total: 9.72s	remaining: 6.32s
606:	learn: 0.2537179	total: 9.74s	remaining: 6.3s
607:	learn: 0.2536776	total: 9.75s	remaining: 6.29s
608:	learn: 0.2535999	total: 9.77s	remaining: 6.27s
609:	learn: 0.2535385	total: 9.78s	remaining: 6.25s
610:	learn: 0.2534839	total: 9.8s	remaining: 6.24s
611:	learn: 0.2534274	total: 9.82s	remaining: 6.22s
612:	learn: 0.2533799	total: 9.83s	remaining: 6.21s
613:	learn: 0.2532954	total: 9.85s	remaining: 6.19s
614:	learn: 0.2532539	total: 9.86s	remaining: 6.17s
615:	learn: 0.2532026	total: 9.88s	remaining: 6.16s
616:	learn: 0.2531355	total: 9.9s	remaining: 6.14s
617:	learn: 0.2531032	total: 9.91s	remaining: 6.13s
618:	learn: 0.2530587	total: 9.93s	remaining: 6.11s
619:	learn: 0.2529989	total: 9.95s	remaining: 6.09s
620:	learn: 0.2529462	total: 9.96s	remaining: 6.08s
621:	learn: 0.2528819	total: 9.97s	remaining: 6.06s
622:	learn: 0.2528399	total: 9.99s	remaining: 6.04s
623:	learn: 0.2527827	total: 10s	remaining: 6.03s
624:	learn: 0.2527181	total: 10s	remaining: 6.01s
625:	learn: 0.2526807	total: 10s	remaining: 6s
626:	learn: 0.2526191	total: 10.1s	remaining: 5.98s
627:	learn: 0.2525595	total: 10.1s	remaining: 5.96s
628:	learn: 0.2525020	total: 10.1s	remaining: 5.95s
629:	learn: 0.2524454	total: 10.1s	remaining: 5.93s
630:	learn: 0.2524044	total: 10.1s	remaining: 5.92s
631:	learn: 0.2523429	total: 10.1s	remaining: 5.9s
632:	learn: 0.2522854	total: 10.2s	remaining: 5.88s
633:	learn: 0.2522452	total: 10.2s	remaining: 5.87s
634:	learn: 0.2521845	total: 10.2s	remaining: 5.85s
635:	learn: 0.2521442	total: 10.2s	remaining: 5.83s
636:	learn: 0.2520745	total: 10.2s	remaining: 5.82s
637:	learn: 0.2520311	total: 10.2s	remaining: 5.8s
638:	learn: 0.2519930	total: 10.2s	remaining: 5.78s
639:	learn: 0.2519335	total: 10.3s	remaining: 5.77s
640:	learn: 0.2518818	total: 10.3s	remaining: 5.75s
641:	learn: 0.2518113	total: 10.3s	remaining: 5.74s
642:	learn: 0.2517254	total: 10.3s	remaining: 5.72s
643:	learn: 0.2516720	total: 10.3s	remaining: 5.71s
644:	learn: 0.2516175	total: 10.3s	remaining: 5.69s
645:	learn: 0.2515675	total: 10.4s	remaining: 5.67s
646:	learn: 0.2515196	total: 10.4s	remaining: 5.66s
647:	learn: 0.2514408	total: 10.4s	remaining: 5.64s
648:	learn: 0.2513921	total: 10.4s	remaining: 5.62s
649:	learn: 0.2513130	total: 10.4s	remaining: 5.61s
650:	learn: 0.2512639	total: 10.4s	remaining: 5.59s
651:	learn: 0.2512260	total: 10.4s	remaining: 5.58s
652:	learn: 0.2511655	total: 10.5s	remaining: 5.56s
653:	learn: 0.2511069	total: 10.5s	remaining: 5.54s
654:	learn: 0.2510465	total: 10.5s	remaining: 5.53s
655:	learn: 0.2509990	total: 10.5s	remaining: 5.51s
656:	learn: 0.2509664	total: 10.5s	remaining: 5.49s
657:	learn: 0.2509174	total: 10.5s	remaining: 5.48s
658:	learn: 0.2508354	total: 10.6s	remaining: 5.46s
659:	learn: 0.2508054	total: 10.6s	remaining: 5.45s
660:	learn: 0.2507425	total: 10.6s	remaining: 5.43s
661:	learn: 0.2506958	total: 10.6s	remaining: 5.41s
662:	learn: 0.2506435	total: 10.6s	remaining: 5.39s
663:	learn: 0.2506024	total: 10.6s	remaining: 5.38s
664:	learn: 0.2505319	total: 10.6s	remaining: 5.36s
665:	learn: 0.2504881	total: 10.7s	remaining: 5.35s
666:	learn: 0.2504219	total: 10.7s	remaining: 5.33s
667:	learn: 0.2503855	total: 10.7s	remaining: 5.31s
668:	learn: 0.2503260	total: 10.7s	remaining: 5.3s
669:	learn: 0.2502669	total: 10.7s	remaining: 5.28s
670:	learn: 0.2502101	total: 10.7s	remaining: 5.26s
671:	learn: 0.2501723	total: 10.8s	remaining: 5.25s
672:	learn: 0.2501026	total: 10.8s	remaining: 5.23s
673:	learn: 0.2500363	total: 10.8s	remaining: 5.22s
674:	learn: 0.2499842	total: 10.8s	remaining: 5.2s
675:	learn: 0.2499148	total: 10.8s	remaining: 5.18s
676:	learn: 0.2498578	total: 10.8s	remaining: 5.17s
677:	learn: 0.2498089	total: 10.9s	remaining: 5.15s
678:	learn: 0.2497597	total: 10.9s	remaining: 5.14s
679:	learn: 0.2497052	total: 10.9s	remaining: 5.12s
680:	learn: 0.2496383	total: 10.9s	remaining: 5.11s
681:	learn: 0.2495648	total: 10.9s	remaining: 5.09s
682:	learn: 0.2495031	total: 10.9s	remaining: 5.08s
683:	learn: 0.2494459	total: 11s	remaining: 5.06s
684:	learn: 0.2493850	total: 11s	remaining: 5.04s
685:	learn: 0.2493042	total: 11s	remaining: 5.03s
686:	learn: 0.2492492	total: 11s	remaining: 5.01s
687:	learn: 0.2491858	total: 11s	remaining: 5s
688:	learn: 0.2491431	total: 11s	remaining: 4.98s
689:	learn: 0.2491095	total: 11s	remaining: 4.96s
690:	learn: 0.2490897	total: 11.1s	remaining: 4.95s
691:	learn: 0.2490443	total: 11.1s	remaining: 4.93s
692:	learn: 0.2490016	total: 11.1s	remaining: 4.91s
693:	learn: 0.2489627	total: 11.1s	remaining: 4.9s
694:	learn: 0.2488904	total: 11.1s	remaining: 4.88s
695:	learn: 0.2488431	total: 11.1s	remaining: 4.86s
696:	learn: 0.2487964	total: 11.2s	remaining: 4.85s
697:	learn: 0.2487500	total: 11.2s	remaining: 4.83s
698:	learn: 0.2486964	total: 11.2s	remaining: 4.82s
699:	learn: 0.2486401	total: 11.2s	remaining: 4.8s
700:	learn: 0.2485877	total: 11.2s	remaining: 4.78s
701:	learn: 0.2485349	total: 11.2s	remaining: 4.77s
702:	learn: 0.2485110	total: 11.2s	remaining: 4.75s
703:	learn: 0.2484503	total: 11.3s	remaining: 4.74s
704:	learn: 0.2483905	total: 11.3s	remaining: 4.72s
705:	learn: 0.2483044	total: 11.3s	remaining: 4.7s
706:	learn: 0.2482655	total: 11.3s	remaining: 4.69s
707:	learn: 0.2481928	total: 11.3s	remaining: 4.67s
708:	learn: 0.2481280	total: 11.3s	remaining: 4.66s
709:	learn: 0.2480856	total: 11.4s	remaining: 4.64s
710:	learn: 0.2480236	total: 11.4s	remaining: 4.62s
711:	learn: 0.2479830	total: 11.4s	remaining: 4.61s
712:	learn: 0.2479444	total: 11.4s	remaining: 4.59s
713:	learn: 0.2478935	total: 11.4s	remaining: 4.57s
714:	learn: 0.2478273	total: 11.4s	remaining: 4.56s
715:	learn: 0.2477928	total: 11.5s	remaining: 4.54s
716:	learn: 0.2477497	total: 11.5s	remaining: 4.53s
717:	learn: 0.2477038	total: 11.5s	remaining: 4.51s
718:	learn: 0.2476627	total: 11.5s	remaining: 4.5s
719:	learn: 0.2475950	total: 11.5s	remaining: 4.48s
720:	learn: 0.2475711	total: 11.5s	remaining: 4.46s
721:	learn: 0.2475246	total: 11.5s	remaining: 4.45s
722:	learn: 0.2474813	total: 11.6s	remaining: 4.43s
723:	learn: 0.2474027	total: 11.6s	remaining: 4.42s
724:	learn: 0.2473431	total: 11.6s	remaining: 4.4s
725:	learn: 0.2472918	total: 11.6s	remaining: 4.38s
726:	learn: 0.2472656	total: 11.6s	remaining: 4.37s
727:	learn: 0.2472201	total: 11.6s	remaining: 4.35s
728:	learn: 0.2471598	total: 11.7s	remaining: 4.33s
729:	learn: 0.2471119	total: 11.7s	remaining: 4.32s
730:	learn: 0.2470805	total: 11.7s	remaining: 4.3s
731:	learn: 0.2470140	total: 11.7s	remaining: 4.29s
732:	learn: 0.2469838	total: 11.7s	remaining: 4.27s
733:	learn: 0.2469432	total: 11.7s	remaining: 4.25s
734:	learn: 0.2468687	total: 11.8s	remaining: 4.24s
735:	learn: 0.2468112	total: 11.8s	remaining: 4.22s
736:	learn: 0.2467731	total: 11.8s	remaining: 4.21s
737:	learn: 0.2467296	total: 11.8s	remaining: 4.19s
738:	learn: 0.2466982	total: 11.8s	remaining: 4.18s
739:	learn: 0.2466379	total: 11.8s	remaining: 4.16s
740:	learn: 0.2465789	total: 11.9s	remaining: 4.14s
741:	learn: 0.2465420	total: 11.9s	remaining: 4.13s
742:	learn: 0.2465030	total: 11.9s	remaining: 4.11s
743:	learn: 0.2464734	total: 11.9s	remaining: 4.09s
744:	learn: 0.2464278	total: 11.9s	remaining: 4.08s
745:	learn: 0.2463798	total: 11.9s	remaining: 4.06s
746:	learn: 0.2463249	total: 12s	remaining: 4.05s
747:	learn: 0.2462784	total: 12s	remaining: 4.03s
748:	learn: 0.2462297	total: 12s	remaining: 4.02s
749:	learn: 0.2461655	total: 12s	remaining: 4s
750:	learn: 0.2460894	total: 12s	remaining: 3.98s
751:	learn: 0.2460252	total: 12s	remaining: 3.97s
752:	learn: 0.2459703	total: 12s	remaining: 3.95s
753:	learn: 0.2459297	total: 12.1s	remaining: 3.94s
754:	learn: 0.2459022	total: 12.1s	remaining: 3.92s
755:	learn: 0.2458410	total: 12.1s	remaining: 3.9s
756:	learn: 0.2457936	total: 12.1s	remaining: 3.89s
757:	learn: 0.2457519	total: 12.1s	remaining: 3.87s
758:	learn: 0.2457081	total: 12.1s	remaining: 3.85s
759:	learn: 0.2456391	total: 12.2s	remaining: 3.84s
760:	learn: 0.2455930	total: 12.2s	remaining: 3.82s
761:	learn: 0.2455495	total: 12.2s	remaining: 3.81s
762:	learn: 0.2455142	total: 12.2s	remaining: 3.79s
763:	learn: 0.2454630	total: 12.2s	remaining: 3.77s
764:	learn: 0.2454090	total: 12.2s	remaining: 3.76s
765:	learn: 0.2453801	total: 12.3s	remaining: 3.74s
766:	learn: 0.2453406	total: 12.3s	remaining: 3.73s
767:	learn: 0.2453139	total: 12.3s	remaining: 3.71s
768:	learn: 0.2452660	total: 12.3s	remaining: 3.69s
769:	learn: 0.2452297	total: 12.3s	remaining: 3.68s
770:	learn: 0.2451948	total: 12.3s	remaining: 3.66s
771:	learn: 0.2451497	total: 12.3s	remaining: 3.65s
772:	learn: 0.2451015	total: 12.4s	remaining: 3.63s
773:	learn: 0.2450777	total: 12.4s	remaining: 3.61s
774:	learn: 0.2450296	total: 12.4s	remaining: 3.6s
775:	learn: 0.2449799	total: 12.4s	remaining: 3.58s
776:	learn: 0.2449306	total: 12.4s	remaining: 3.57s
777:	learn: 0.2448831	total: 12.4s	remaining: 3.55s
778:	learn: 0.2448349	total: 12.5s	remaining: 3.53s
779:	learn: 0.2447833	total: 12.5s	remaining: 3.52s
780:	learn: 0.2447193	total: 12.5s	remaining: 3.5s
781:	learn: 0.2446805	total: 12.5s	remaining: 3.48s
782:	learn: 0.2446256	total: 12.5s	remaining: 3.47s
783:	learn: 0.2445452	total: 12.5s	remaining: 3.45s
784:	learn: 0.2445029	total: 12.6s	remaining: 3.44s
785:	learn: 0.2444662	total: 12.6s	remaining: 3.42s
786:	learn: 0.2444287	total: 12.6s	remaining: 3.41s
787:	learn: 0.2443919	total: 12.6s	remaining: 3.39s
788:	learn: 0.2443231	total: 12.6s	remaining: 3.37s
789:	learn: 0.2442733	total: 12.6s	remaining: 3.36s
790:	learn: 0.2442152	total: 12.6s	remaining: 3.34s
791:	learn: 0.2441839	total: 12.7s	remaining: 3.33s
792:	learn: 0.2441246	total: 12.7s	remaining: 3.31s
793:	learn: 0.2440379	total: 12.7s	remaining: 3.29s
794:	learn: 0.2439484	total: 12.7s	remaining: 3.28s
795:	learn: 0.2438880	total: 12.7s	remaining: 3.26s
796:	learn: 0.2438316	total: 12.8s	remaining: 3.25s
797:	learn: 0.2437758	total: 12.8s	remaining: 3.23s
798:	learn: 0.2437285	total: 12.8s	remaining: 3.22s
799:	learn: 0.2436823	total: 12.8s	remaining: 3.2s
800:	learn: 0.2436436	total: 12.8s	remaining: 3.18s
801:	learn: 0.2435855	total: 12.8s	remaining: 3.17s
802:	learn: 0.2435374	total: 12.9s	remaining: 3.15s
803:	learn: 0.2434685	total: 12.9s	remaining: 3.14s
804:	learn: 0.2434027	total: 12.9s	remaining: 3.12s
805:	learn: 0.2433559	total: 12.9s	remaining: 3.1s
806:	learn: 0.2433083	total: 12.9s	remaining: 3.09s
807:	learn: 0.2432502	total: 12.9s	remaining: 3.07s
808:	learn: 0.2431914	total: 13s	remaining: 3.06s
809:	learn: 0.2431262	total: 13s	remaining: 3.04s
810:	learn: 0.2430658	total: 13s	remaining: 3.03s
811:	learn: 0.2430318	total: 13s	remaining: 3.01s
812:	learn: 0.2429879	total: 13s	remaining: 2.99s
813:	learn: 0.2429379	total: 13s	remaining: 2.98s
814:	learn: 0.2428843	total: 13s	remaining: 2.96s
815:	learn: 0.2428392	total: 13.1s	remaining: 2.94s
816:	learn: 0.2427927	total: 13.1s	remaining: 2.93s
817:	learn: 0.2427312	total: 13.1s	remaining: 2.91s
818:	learn: 0.2426978	total: 13.1s	remaining: 2.9s
819:	learn: 0.2426252	total: 13.1s	remaining: 2.88s
820:	learn: 0.2426031	total: 13.1s	remaining: 2.87s
821:	learn: 0.2425684	total: 13.2s	remaining: 2.85s
822:	learn: 0.2425005	total: 13.2s	remaining: 2.83s
823:	learn: 0.2424596	total: 13.2s	remaining: 2.82s
824:	learn: 0.2424090	total: 13.2s	remaining: 2.8s
825:	learn: 0.2423496	total: 13.2s	remaining: 2.79s
826:	learn: 0.2423102	total: 13.3s	remaining: 2.77s
827:	learn: 0.2422588	total: 13.3s	remaining: 2.76s
828:	learn: 0.2421883	total: 13.3s	remaining: 2.74s
829:	learn: 0.2421424	total: 13.3s	remaining: 2.73s
830:	learn: 0.2420827	total: 13.3s	remaining: 2.71s
831:	learn: 0.2420295	total: 13.3s	remaining: 2.69s
832:	learn: 0.2419868	total: 13.4s	remaining: 2.68s
833:	learn: 0.2419450	total: 13.4s	remaining: 2.66s
834:	learn: 0.2418827	total: 13.4s	remaining: 2.65s
835:	learn: 0.2418268	total: 13.4s	remaining: 2.63s
836:	learn: 0.2417818	total: 13.4s	remaining: 2.61s
837:	learn: 0.2417421	total: 13.4s	remaining: 2.6s
838:	learn: 0.2417147	total: 13.5s	remaining: 2.58s
839:	learn: 0.2416543	total: 13.5s	remaining: 2.56s
840:	learn: 0.2416242	total: 13.5s	remaining: 2.55s
841:	learn: 0.2415649	total: 13.5s	remaining: 2.53s
842:	learn: 0.2415346	total: 13.5s	remaining: 2.52s
843:	learn: 0.2414719	total: 13.5s	remaining: 2.5s
844:	learn: 0.2414326	total: 13.5s	remaining: 2.48s
845:	learn: 0.2413828	total: 13.6s	remaining: 2.47s
846:	learn: 0.2413326	total: 13.6s	remaining: 2.45s
847:	learn: 0.2413004	total: 13.6s	remaining: 2.44s
848:	learn: 0.2412372	total: 13.6s	remaining: 2.42s
849:	learn: 0.2411850	total: 13.6s	remaining: 2.4s
850:	learn: 0.2411413	total: 13.6s	remaining: 2.39s
851:	learn: 0.2410588	total: 13.7s	remaining: 2.37s
852:	learn: 0.2409988	total: 13.7s	remaining: 2.36s
853:	learn: 0.2409543	total: 13.7s	remaining: 2.34s
854:	learn: 0.2409134	total: 13.7s	remaining: 2.32s
855:	learn: 0.2408477	total: 13.7s	remaining: 2.31s
856:	learn: 0.2407971	total: 13.7s	remaining: 2.29s
857:	learn: 0.2407485	total: 13.8s	remaining: 2.27s
858:	learn: 0.2407145	total: 13.8s	remaining: 2.26s
859:	learn: 0.2406695	total: 13.8s	remaining: 2.24s
860:	learn: 0.2406157	total: 13.8s	remaining: 2.23s
861:	learn: 0.2405748	total: 13.8s	remaining: 2.21s
862:	learn: 0.2405239	total: 13.8s	remaining: 2.19s
863:	learn: 0.2404619	total: 13.8s	remaining: 2.18s
864:	learn: 0.2403975	total: 13.9s	remaining: 2.16s
865:	learn: 0.2403319	total: 13.9s	remaining: 2.15s
866:	learn: 0.2402985	total: 13.9s	remaining: 2.13s
867:	learn: 0.2402551	total: 13.9s	remaining: 2.12s
868:	learn: 0.2402096	total: 13.9s	remaining: 2.1s
869:	learn: 0.2401800	total: 13.9s	remaining: 2.08s
870:	learn: 0.2401389	total: 14s	remaining: 2.07s
871:	learn: 0.2400823	total: 14s	remaining: 2.05s
872:	learn: 0.2400425	total: 14s	remaining: 2.03s
873:	learn: 0.2399951	total: 14s	remaining: 2.02s
874:	learn: 0.2399413	total: 14s	remaining: 2s
875:	learn: 0.2398957	total: 14s	remaining: 1.99s
876:	learn: 0.2398433	total: 14.1s	remaining: 1.97s
877:	learn: 0.2397857	total: 14.1s	remaining: 1.95s
878:	learn: 0.2397384	total: 14.1s	remaining: 1.94s
879:	learn: 0.2396931	total: 14.1s	remaining: 1.92s
880:	learn: 0.2396608	total: 14.1s	remaining: 1.91s
881:	learn: 0.2396130	total: 14.1s	remaining: 1.89s
882:	learn: 0.2395678	total: 14.1s	remaining: 1.87s
883:	learn: 0.2395207	total: 14.2s	remaining: 1.86s
884:	learn: 0.2394700	total: 14.2s	remaining: 1.84s
885:	learn: 0.2394176	total: 14.2s	remaining: 1.82s
886:	learn: 0.2393682	total: 14.2s	remaining: 1.81s
887:	learn: 0.2393139	total: 14.2s	remaining: 1.79s
888:	learn: 0.2392730	total: 14.3s	remaining: 1.78s
889:	learn: 0.2392253	total: 14.3s	remaining: 1.76s
890:	learn: 0.2391987	total: 14.3s	remaining: 1.75s
891:	learn: 0.2391544	total: 14.3s	remaining: 1.73s
892:	learn: 0.2391115	total: 14.3s	remaining: 1.72s
893:	learn: 0.2390717	total: 14.4s	remaining: 1.7s
894:	learn: 0.2390218	total: 14.4s	remaining: 1.69s
895:	learn: 0.2389918	total: 14.4s	remaining: 1.67s
896:	learn: 0.2389481	total: 14.4s	remaining: 1.65s
897:	learn: 0.2389036	total: 14.4s	remaining: 1.64s
898:	learn: 0.2388523	total: 14.4s	remaining: 1.62s
899:	learn: 0.2388107	total: 14.5s	remaining: 1.61s
900:	learn: 0.2387748	total: 14.5s	remaining: 1.59s
901:	learn: 0.2387187	total: 14.5s	remaining: 1.57s
902:	learn: 0.2386752	total: 14.5s	remaining: 1.56s
903:	learn: 0.2386253	total: 14.5s	remaining: 1.54s
904:	learn: 0.2385669	total: 14.5s	remaining: 1.52s
905:	learn: 0.2385191	total: 14.5s	remaining: 1.51s
906:	learn: 0.2384988	total: 14.6s	remaining: 1.49s
907:	learn: 0.2384551	total: 14.6s	remaining: 1.48s
908:	learn: 0.2384118	total: 14.6s	remaining: 1.46s
909:	learn: 0.2383773	total: 14.6s	remaining: 1.45s
910:	learn: 0.2383360	total: 14.6s	remaining: 1.43s
911:	learn: 0.2382983	total: 14.6s	remaining: 1.41s
912:	learn: 0.2382556	total: 14.7s	remaining: 1.4s
913:	learn: 0.2382350	total: 14.7s	remaining: 1.38s
914:	learn: 0.2381577	total: 14.7s	remaining: 1.36s
915:	learn: 0.2380981	total: 14.7s	remaining: 1.35s
916:	learn: 0.2380420	total: 14.7s	remaining: 1.33s
917:	learn: 0.2379920	total: 14.7s	remaining: 1.32s
918:	learn: 0.2379506	total: 14.8s	remaining: 1.3s
919:	learn: 0.2379006	total: 14.8s	remaining: 1.28s
920:	learn: 0.2378590	total: 14.8s	remaining: 1.27s
921:	learn: 0.2378123	total: 14.8s	remaining: 1.25s
922:	learn: 0.2377656	total: 14.8s	remaining: 1.24s
923:	learn: 0.2377079	total: 14.8s	remaining: 1.22s
924:	learn: 0.2376577	total: 14.8s	remaining: 1.2s
925:	learn: 0.2375939	total: 14.9s	remaining: 1.19s
926:	learn: 0.2375496	total: 14.9s	remaining: 1.17s
927:	learn: 0.2375283	total: 14.9s	remaining: 1.16s
928:	learn: 0.2374676	total: 14.9s	remaining: 1.14s
929:	learn: 0.2374244	total: 14.9s	remaining: 1.12s
930:	learn: 0.2373706	total: 14.9s	remaining: 1.11s
931:	learn: 0.2372846	total: 15s	remaining: 1.09s
932:	learn: 0.2372460	total: 15s	remaining: 1.07s
933:	learn: 0.2371937	total: 15s	remaining: 1.06s
934:	learn: 0.2371455	total: 15s	remaining: 1.04s
935:	learn: 0.2370846	total: 15s	remaining: 1.03s
936:	learn: 0.2370469	total: 15s	remaining: 1.01s
937:	learn: 0.2369962	total: 15s	remaining: 995ms
938:	learn: 0.2369616	total: 15.1s	remaining: 979ms
939:	learn: 0.2369067	total: 15.1s	remaining: 962ms
940:	learn: 0.2368527	total: 15.1s	remaining: 946ms
941:	learn: 0.2367814	total: 15.1s	remaining: 930ms
942:	learn: 0.2367123	total: 15.1s	remaining: 914ms
943:	learn: 0.2366689	total: 15.1s	remaining: 898ms
944:	learn: 0.2366119	total: 15.2s	remaining: 882ms
945:	learn: 0.2365652	total: 15.2s	remaining: 866ms
946:	learn: 0.2365333	total: 15.2s	remaining: 850ms
947:	learn: 0.2364712	total: 15.2s	remaining: 834ms
948:	learn: 0.2364393	total: 15.2s	remaining: 818ms
949:	learn: 0.2363692	total: 15.2s	remaining: 802ms
950:	learn: 0.2363086	total: 15.3s	remaining: 786ms
951:	learn: 0.2362640	total: 15.3s	remaining: 770ms
952:	learn: 0.2362275	total: 15.3s	remaining: 754ms
953:	learn: 0.2361713	total: 15.3s	remaining: 738ms
954:	learn: 0.2361375	total: 15.3s	remaining: 721ms
955:	learn: 0.2361068	total: 15.3s	remaining: 705ms
956:	learn: 0.2360703	total: 15.3s	remaining: 689ms
957:	learn: 0.2360238	total: 15.4s	remaining: 673ms
958:	learn: 0.2359527	total: 15.4s	remaining: 657ms
959:	learn: 0.2359029	total: 15.4s	remaining: 641ms
960:	learn: 0.2358613	total: 15.4s	remaining: 625ms
961:	learn: 0.2358066	total: 15.4s	remaining: 609ms
962:	learn: 0.2357766	total: 15.4s	remaining: 593ms
963:	learn: 0.2357294	total: 15.4s	remaining: 577ms
964:	learn: 0.2356838	total: 15.5s	remaining: 561ms
965:	learn: 0.2356378	total: 15.5s	remaining: 545ms
966:	learn: 0.2355685	total: 15.5s	remaining: 529ms
967:	learn: 0.2355349	total: 15.5s	remaining: 513ms
968:	learn: 0.2354947	total: 15.5s	remaining: 497ms
969:	learn: 0.2354376	total: 15.5s	remaining: 481ms
970:	learn: 0.2354015	total: 15.6s	remaining: 465ms
971:	learn: 0.2353515	total: 15.6s	remaining: 449ms
972:	learn: 0.2353100	total: 15.6s	remaining: 433ms
973:	learn: 0.2352776	total: 15.6s	remaining: 417ms
974:	learn: 0.2352368	total: 15.6s	remaining: 400ms
975:	learn: 0.2351770	total: 15.6s	remaining: 384ms
976:	learn: 0.2351215	total: 15.7s	remaining: 368ms
977:	learn: 0.2350577	total: 15.7s	remaining: 352ms
978:	learn: 0.2350007	total: 15.7s	remaining: 336ms
979:	learn: 0.2349692	total: 15.7s	remaining: 320ms
980:	learn: 0.2349258	total: 15.7s	remaining: 304ms
981:	learn: 0.2348717	total: 15.7s	remaining: 288ms
982:	learn: 0.2348056	total: 15.7s	remaining: 272ms
983:	learn: 0.2347585	total: 15.8s	remaining: 256ms
984:	learn: 0.2347097	total: 15.8s	remaining: 240ms
985:	learn: 0.2346470	total: 15.8s	remaining: 224ms
986:	learn: 0.2345769	total: 15.8s	remaining: 208ms
987:	learn: 0.2345387	total: 15.8s	remaining: 192ms
988:	learn: 0.2344945	total: 15.8s	remaining: 176ms
989:	learn: 0.2344357	total: 15.9s	remaining: 160ms
990:	learn: 0.2343961	total: 15.9s	remaining: 144ms
991:	learn: 0.2343647	total: 15.9s	remaining: 128ms
992:	learn: 0.2343208	total: 15.9s	remaining: 112ms
993:	learn: 0.2342831	total: 15.9s	remaining: 96.1ms
994:	learn: 0.2342506	total: 15.9s	remaining: 80.1ms
995:	learn: 0.2342293	total: 15.9s	remaining: 64ms
996:	learn: 0.2341951	total: 16s	remaining: 48ms
997:	learn: 0.2341430	total: 16s	remaining: 32ms
998:	learn: 0.2341071	total: 16s	remaining: 16ms
999:	learn: 0.2340865	total: 16s	remaining: 0us
</pre>
<pre>
array([[0.93978234, 0.06021766],
       [0.95124372, 0.04875628],
       [0.96812596, 0.03187404],
       ...,
       [0.98319969, 0.01680031],
       [0.96758391, 0.03241609],
       [0.97709079, 0.02290921]])
</pre>

```python
sub=pd.read_csv("/kaggle/input/DontGetKicked/example_entry.csv")
sub
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>RefId</th>
      <th>IsBadBuy</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>73015</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>73016</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>73017</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>73018</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>73019</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>48702</th>
      <td>121742</td>
      <td>0</td>
    </tr>
    <tr>
      <th>48703</th>
      <td>121743</td>
      <td>0</td>
    </tr>
    <tr>
      <th>48704</th>
      <td>121744</td>
      <td>0</td>
    </tr>
    <tr>
      <th>48705</th>
      <td>121745</td>
      <td>0</td>
    </tr>
    <tr>
      <th>48706</th>
      <td>121746</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>48707 rows × 2 columns</p>
</div>



```python
sub["IsBadBuy"]=result[:,1]
sub
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>RefId</th>
      <th>IsBadBuy</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>73015</td>
      <td>0.060218</td>
    </tr>
    <tr>
      <th>1</th>
      <td>73016</td>
      <td>0.048756</td>
    </tr>
    <tr>
      <th>2</th>
      <td>73017</td>
      <td>0.031874</td>
    </tr>
    <tr>
      <th>3</th>
      <td>73018</td>
      <td>0.211790</td>
    </tr>
    <tr>
      <th>4</th>
      <td>73019</td>
      <td>0.990167</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>48702</th>
      <td>121742</td>
      <td>0.106484</td>
    </tr>
    <tr>
      <th>48703</th>
      <td>121743</td>
      <td>0.076228</td>
    </tr>
    <tr>
      <th>48704</th>
      <td>121744</td>
      <td>0.016800</td>
    </tr>
    <tr>
      <th>48705</th>
      <td>121745</td>
      <td>0.032416</td>
    </tr>
    <tr>
      <th>48706</th>
      <td>121746</td>
      <td>0.022909</td>
    </tr>
  </tbody>
</table>
<p>48707 rows × 2 columns</p>
</div>



```python
cbc.feature_importances_
```

<pre>
array([2.37333696, 2.48583464, 3.23834754, 1.43343693, 3.38399564,
       2.57961296, 3.18845789, 1.26556088, 0.26474531, 8.50870017,
       5.53477726, 4.33262873, 0.33648363, 1.08664952, 0.7611835 ,
       2.60615011, 2.40282626, 2.37301766, 2.0830943 , 3.670945  ,
       3.43485981, 3.55927567, 2.67167673, 1.66807044, 0.92591741,
       5.33460896, 5.71703873, 2.49554436, 5.7162646 , 0.13503464,
       2.80221508, 1.64747234, 5.35793584, 2.98069144, 1.64360905])
</pre>

```python
pd.Series(cbc.feature_importances_,index=train2.columns).sort_values()
```

<pre>
IsOnlineSale                         0.135035
Transmission                         0.264745
Nationality                          0.336484
TopThreeAmericanName                 0.761184
AUCGUART                             0.925917
Size                                 1.086650
Color                                1.265561
Make                                 1.433437
weekday                              1.643609
year                                 1.647472
PRIMEUNIT                            1.668070
MMRAcquisitonRetailCleanPrice        2.083094
MMRAcquisitionRetailAveragePrice     2.373018
Auction                              2.373337
MMRAcquisitionAuctionCleanPrice      2.402826
VehYear                              2.485835
VNST                                 2.495544
Trim                                 2.579613
MMRAcquisitionAuctionAveragePrice    2.606150
MMRCurrentRetailCleanPrice           2.671677
WarrantyCost                         2.802215
day                                  2.980691
SubModel                             3.188458
VehicleAge                           3.238348
Model                                3.383996
MMRCurrentAuctionCleanPrice          3.434860
MMRCurrentRetailAveragePrice         3.559276
MMRCurrentAuctionAveragePrice        3.670945
VehOdo                               4.332629
BYRNO                                5.334609
month                                5.357936
WheelType                            5.534777
VehBCost                             5.716265
VNZIP1                               5.717039
WheelTypeID                          8.508700
dtype: float64
</pre>

```python
sub.to_csv("cbc_with_array.csv",index=False)
```
