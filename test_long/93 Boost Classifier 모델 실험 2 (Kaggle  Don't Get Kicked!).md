# 3 Boost Classifier 모델 실험 2 (Kaggle  Don't Get Kicked!)


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

/kaggle/input/DontGetKicked/example_entry.csv

/kaggle/input/DontGetKicked/training.zip

/kaggle/input/DontGetKicked/Carvana_Data_Dictionary.txt

/kaggle/input/DontGetKicked/test.zip

/kaggle/input/DontGetKicked/training.csv

/kaggle/input/DontGetKicked/test.csv


```python
train=pd.read_csv("/kaggle/input/DontGetKicked/training.csv")
test=pd.read_csv("/kaggle/input/DontGetKicked/test.csv")
pd.options.display.max_columns=99
display(train,test)
```

<div>

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
----
alldata에서 train 항목 대상 칼럼을 정하기 위해, countplot으로 target columns "IsBadBuy"와의 상관성을 분석합니다

----

```python
import matplotlib.pyplot as plt
import seaborn as sns
plt.figure(figsize=(16,8))
sns.countplot(alldata["weekday"],hue=alldata["IsBadBuy"])
```
![image](https://user-images.githubusercontent.com/69743938/172118070-20cb977b-39a2-4fa2-b086-c6cb621cc55f.png)

```python
plt.figure(figsize=(16,8))
sns.countplot(alldata["Auction"],hue=alldata["IsBadBuy"])
```

![image](https://user-images.githubusercontent.com/69743938/172118108-df71cabc-475e-4149-a98e-d9116f9a1841.png)

```python
plt.figure(figsize=(16,8))
sns.countplot(alldata["WheelType"],hue=alldata["IsBadBuy"])
```

![image](https://user-images.githubusercontent.com/69743938/172118144-14f66b0e-8749-4950-ac19-f9d090208ed1.png)


```python
plt.figure(figsize=(16,8))
sns.countplot(alldata["Transmission"],hue=alldata["IsBadBuy"])
```

![image](https://user-images.githubusercontent.com/69743938/172118175-979a29bc-9fb5-4165-81dd-69bca87300c9.png)


```python
plt.figure(figsize=(16,8))
sns.countplot(alldata["VehicleAge"],hue=alldata["IsBadBuy"])
```

![image](https://user-images.githubusercontent.com/69743938/172118208-7d2d4eaa-9e5a-45f3-a32e-19a3cb7fc33a.png)

--------
위의 그림을 통해, 자동차를 구매했을때 불량일 확률과 weekday / Auction / WheelType / Transmission / VehicleAge의 영향성을 알 수 있습니다.

CatBoostClassifier를 제외하고 다른 모델에서는 주로 datetime 형식을 인식할 수 없어 전처리해주었습니다.

-------

```python
alldata2=alldata.drop(columns=["IsBadBuy","RefId","PurchDate"])
# alldata2=alldata.drop(columns=["IsBadBuy","RefId"])
```

-----------
Auction의 그룹별 평균 값을 보았을때 높은 순서대로 배열하여 예측의 정확성을 높일 수 있습니다.

RandomForestClassifier에서 score 0.23688(높을 수록 순위 향상)이나 순서대로 배열하여 예측하지 않은 경우 동일 조건의 score 0.23680로 나타났습니다.

------

```python
alldata.groupby("Auction")["IsBadBuy"].mean()
alldata2["Auction"]=alldata2["Auction"].replace({"ADESA ":2, "OTHER":1, "MANHEIM":0})
```
-----
classifier 모델은 object 형태의 데이터를 처리할 수 없으므로 레이블 인코딩을 사용하여 숫자 형식으로 변환한다.

-----

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

---------------

점수 개선 순위를 살펴보면 다음과 같습니다.

CatBoostClassifier > LGBMClassifier > GradientBoostingClassifier > XGBClassifier > RandomForestClassifier

이전 대회 Shelter Animal Outcomes와 달리, CatBoostClassifier는 LightGBM Classifier보다 정확성이 높게 확인되었습니다.

LightGBM Classifier에서 리프중심 트리분할을 사용할 경우 예측 오류 손실은 최소화하나 과대적합이 동시에 일어났을 것으로 예상됩니다.

또한, CatBoostClassifier의 경우 오류를 보정하면서 date time 형식의 데이터를 추가로 학습할 수 있어 이 데이터에 가장 적합해보입니다.

-----------------

```python
from sklearn.ensemble import RandomForestClassifier
rfc=RandomForestClassifier()
rfc.fit(train2,train["IsBadBuy"])
result=rfc.predict_proba(test2)
result
```



array([[0.93, 0.07],
[0.94, 0.06],
[0.98, 0.02],
  ...,
[0.97, 0.03],
[0.88, 0.12],
[0.93, 0.07]])


```python
from sklearn.ensemble import GradientBoostingClassifier
gbc=GradientBoostingClassifier()
gbc.fit(train2,train["IsBadBuy"])
result=gbc.predict_proba(test2)
result
```

array([[0.93534645, 0.06465355],
[0.94635939, 0.05364061],
[0.95021494, 0.04978506],
...,
[0.96491573, 0.03508427],
[0.94898903, 0.05101097],
[0.94792384, 0.05207616]])

```python
from xgboost import XGBClassifier
xgbc=XGBClassifier()
xgbc.fit(train2,train["IsBadBuy"])
result=xgbc.predict_proba(test2)
result
```

array([[0.9634486 , 0.03655142],
[0.95317996, 0.04682005],
[0.9588968 , 0.04110317],
...,
[0.9913116 , 0.00868841],
[0.9735207 , 0.02647929],
[0.9904574 , 0.00954259]], dtype=float32)


```python
from lightgbm import LGBMClassifier
lgbmc=LGBMClassifier()
lgbmc.fit(train2,train["IsBadBuy"])
result=lgbmc.predict_proba(test2)
result
```

array([[0.93183565, 0.06816435],
[0.94422586, 0.05577414],
[0.94985675, 0.05014325],
...,
[0.98243161, 0.01756839],
[0.96154284, 0.03845716],
[0.96159952, 0.03840048]])


```python
from catboost import CatBoostClassifier
cbc=CatBoostClassifier()
cbc.fit(train2,train["IsBadBuy"])
result=cbc.predict_proba(test2)
result
```


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

...

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



array([[0.93978234, 0.06021766],

[0.95124372, 0.04875628],

[0.96812596, 0.03187404],

...,

[0.98319969, 0.01680031],

[0.96758391, 0.03241609],

[0.97709079, 0.02290921]])

```python
sub=pd.read_csv("/kaggle/input/DontGetKicked/example_entry.csv")
sub
```

<div>

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


array([2.37333696, 2.48583464, 3.23834754, 1.43343693, 3.38399564,

2.57961296, 3.18845789, 1.26556088, 0.26474531, 8.50870017,

5.53477726, 4.33262873, 0.33648363, 1.08664952, 0.7611835 ,

2.60615011, 2.40282626, 2.37301766, 2.0830943 , 3.670945  ,

3.43485981, 3.55927567, 2.67167673, 1.66807044, 0.92591741,

5.33460896, 5.71703873, 2.49554436, 5.7162646 , 0.13503464,

2.80221508, 1.64747234, 5.35793584, 2.98069144, 1.64360905])

```python
pd.Series(cbc.feature_importances_,index=train2.columns).sort_values()
```

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



```python
sub.to_csv("cbc_with_array.csv",index=False)
```
