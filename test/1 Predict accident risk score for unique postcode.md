# 1. Predict accident risk score for unique postcode

![image](https://user-images.githubusercontent.com/69743938/172154090-fec8ef84-1596-4571-8779-18b41bcef956.png)




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


/kaggle/input/participantsdataset/sample_submission.csv

/kaggle/input/participantsdataset/population.csv

/kaggle/input/participantsdataset/train.csv

/kaggle/input/participantsdataset/test.csv

/kaggle/input/participantsdataset/roads_network.csv


```python
pd.options.display.max_columns=999
pd.options.display.max_rows=100
```


```python
train = pd.read_csv("/kaggle/input/participantsdataset/train.csv")
test = pd.read_csv("/kaggle/input/participantsdataset/test.csv")
sub = pd.read_csv("/kaggle/input/participantsdataset/sample_submission.csv")

display(train,test,sub)
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Accident_ID</th>
      <th>Police_Force</th>
      <th>Number_of_Vehicles</th>
      <th>Number_of_Casualties</th>
      <th>Date</th>
      <th>Day_of_Week</th>
      <th>Time</th>
      <th>Local_Authority_(District)</th>
      <th>Local_Authority_(Highway)</th>
      <th>1st_Road_Class</th>
      <th>1st_Road_Number</th>
      <th>Road_Type</th>
      <th>Speed_limit</th>
      <th>2nd_Road_Class</th>
      <th>2nd_Road_Number</th>
      <th>Pedestrian_Crossing-Human_Control</th>
      <th>Pedestrian_Crossing-Physical_Facilities</th>
      <th>Light_Conditions</th>
      <th>Weather_Conditions</th>
      <th>Road_Surface_Conditions</th>
      <th>Special_Conditions_at_Site</th>
      <th>Carriageway_Hazards</th>
      <th>Urban_or_Rural_Area</th>
      <th>Did_Police_Officer_Attend_Scene_of_Accident</th>
      <th>state</th>
      <th>postcode</th>
      <th>country</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>34</td>
      <td>2</td>
      <td>1</td>
      <td>19/12/12</td>
      <td>7</td>
      <td>13:20</td>
      <td>344</td>
      <td>E10000032</td>
      <td>4</td>
      <td>395</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>-1</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>Ol or diesel</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>OX3 9UP</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>5</td>
      <td>2</td>
      <td>1</td>
      <td>02/11/12</td>
      <td>4</td>
      <td>7:53</td>
      <td>102</td>
      <td>E09000026</td>
      <td>3</td>
      <td>13</td>
      <td>One way street</td>
      <td>30</td>
      <td>-1</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Raining without high winds</td>
      <td>Dry</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>No</td>
      <td>England</td>
      <td>S35 4EZ</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
      <td>02/11/12</td>
      <td>4</td>
      <td>16:00</td>
      <td>531</td>
      <td>E10000016</td>
      <td>6</td>
      <td>8</td>
      <td>Roundabout</td>
      <td>40</td>
      <td>6</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>Zebra crossing</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>No</td>
      <td>England</td>
      <td>BN21 2XR</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>06/05/12</td>
      <td>1</td>
      <td>16:50</td>
      <td>7</td>
      <td>E08000035</td>
      <td>6</td>
      <td>13</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>6</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>Roadworks</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>TA20 3PT</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>46</td>
      <td>1</td>
      <td>1</td>
      <td>30/06/12</td>
      <td>3</td>
      <td>13:25</td>
      <td>519</td>
      <td>E10000031</td>
      <td>3</td>
      <td>24</td>
      <td>Dual carriageway</td>
      <td>30</td>
      <td>6</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>Zebra crossing</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>No</td>
      <td>England</td>
      <td>DN20 0QF</td>
      <td>United Kingdom</td>
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
    </tr>
    <tr>
      <th>478736</th>
      <td>599995</td>
      <td>13</td>
      <td>1</td>
      <td>1</td>
      <td>28/09/12</td>
      <td>6</td>
      <td>16:35</td>
      <td>199</td>
      <td>E10000015</td>
      <td>6</td>
      <td>0</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>-1</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Snow</td>
      <td>None</td>
      <td>None</td>
      <td>2</td>
      <td>Yes</td>
      <td>England</td>
      <td>E12 6EA</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>478737</th>
      <td>599996</td>
      <td>13</td>
      <td>2</td>
      <td>1</td>
      <td>23/01/12</td>
      <td>4</td>
      <td>20:45</td>
      <td>211</td>
      <td>E09000012</td>
      <td>6</td>
      <td>1293</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>-1</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Wet/Damp</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>No</td>
      <td>England</td>
      <td>NN2 8PF</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>478738</th>
      <td>599997</td>
      <td>6</td>
      <td>2</td>
      <td>4</td>
      <td>15/05/12</td>
      <td>6</td>
      <td>10:45</td>
      <td>80</td>
      <td>E06000047</td>
      <td>3</td>
      <td>310</td>
      <td>Roundabout</td>
      <td>30</td>
      <td>-1</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>No</td>
      <td>England</td>
      <td>DN36 5FR</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>478739</th>
      <td>599998</td>
      <td>33</td>
      <td>2</td>
      <td>1</td>
      <td>09/10/12</td>
      <td>2</td>
      <td>11:22</td>
      <td>321</td>
      <td>E10000024</td>
      <td>3</td>
      <td>3283</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>5</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>None</td>
      <td>Other object in carriageway</td>
      <td>2</td>
      <td>No</td>
      <td>England</td>
      <td>BN11 2EB</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>478740</th>
      <td>599999</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
      <td>12/04/12</td>
      <td>6</td>
      <td>11:50</td>
      <td>23</td>
      <td>E09000025</td>
      <td>4</td>
      <td>9</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>6</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Raining without high winds</td>
      <td>Dry</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>IP10 0AH</td>
      <td>United Kingdom</td>
    </tr>
  </tbody>
</table>
<p>478741 rows × 27 columns</p>
</div>


<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Accident_ID</th>
      <th>Police_Force</th>
      <th>Number_of_Vehicles</th>
      <th>Number_of_Casualties</th>
      <th>Date</th>
      <th>Day_of_Week</th>
      <th>Time</th>
      <th>Local_Authority_(District)</th>
      <th>Local_Authority_(Highway)</th>
      <th>1st_Road_Class</th>
      <th>1st_Road_Number</th>
      <th>Road_Type</th>
      <th>Speed_limit</th>
      <th>2nd_Road_Class</th>
      <th>2nd_Road_Number</th>
      <th>Pedestrian_Crossing-Human_Control</th>
      <th>Pedestrian_Crossing-Physical_Facilities</th>
      <th>Light_Conditions</th>
      <th>Weather_Conditions</th>
      <th>Road_Surface_Conditions</th>
      <th>Special_Conditions_at_Site</th>
      <th>Carriageway_Hazards</th>
      <th>Urban_or_Rural_Area</th>
      <th>Did_Police_Officer_Attend_Scene_of_Accident</th>
      <th>state</th>
      <th>postcode</th>
      <th>country</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>14</td>
      <td>13</td>
      <td>2</td>
      <td>0</td>
      <td>06/10/13</td>
      <td>6</td>
      <td>13:28</td>
      <td>218</td>
      <td>E10000032</td>
      <td>4</td>
      <td>6358</td>
      <td>Single carriageway</td>
      <td>60</td>
      <td>6</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Snowing without high winds</td>
      <td>Dry</td>
      <td>None</td>
      <td>None</td>
      <td>2</td>
      <td>Yes</td>
      <td>England</td>
      <td>HX2 8WH</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>1</th>
      <td>17</td>
      <td>13</td>
      <td>2</td>
      <td>0</td>
      <td>22/04/13</td>
      <td>7</td>
      <td>9:30</td>
      <td>157</td>
      <td>E10000034</td>
      <td>6</td>
      <td>29</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>-1</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>No</td>
      <td>England</td>
      <td>RM8 1DD</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>2</th>
      <td>21</td>
      <td>13</td>
      <td>2</td>
      <td>0</td>
      <td>27/09/13</td>
      <td>3</td>
      <td>19:10</td>
      <td>155</td>
      <td>E09000012</td>
      <td>3</td>
      <td>5376</td>
      <td>Roundabout</td>
      <td>40</td>
      <td>3</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Wet/Damp</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>SE23 1NH</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>3</th>
      <td>23</td>
      <td>13</td>
      <td>2</td>
      <td>0</td>
      <td>13/03/13</td>
      <td>4</td>
      <td>9:19</td>
      <td>26</td>
      <td>E10000016</td>
      <td>4</td>
      <td>1252</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>-1</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>HU10 7QS</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>4</th>
      <td>28</td>
      <td>14</td>
      <td>2</td>
      <td>0</td>
      <td>13/06/13</td>
      <td>1</td>
      <td>14:59</td>
      <td>6</td>
      <td>E08000012</td>
      <td>4</td>
      <td>1202</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>3</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>BD23 5JL</td>
      <td>United Kingdom</td>
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
    </tr>
    <tr>
      <th>121254</th>
      <td>599986</td>
      <td>1</td>
      <td>2</td>
      <td>0</td>
      <td>05/07/13</td>
      <td>5</td>
      <td>18:31</td>
      <td>6</td>
      <td>E06000042</td>
      <td>6</td>
      <td>0</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>3</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Darkness: Street lights present and lit</td>
      <td>Fine without high winds</td>
      <td>Wet/Damp</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>HD9 4AB</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>121255</th>
      <td>599990</td>
      <td>62</td>
      <td>2</td>
      <td>0</td>
      <td>22/11/13</td>
      <td>6</td>
      <td>7:40</td>
      <td>633</td>
      <td>W06000004</td>
      <td>3</td>
      <td>379</td>
      <td>Dual carriageway</td>
      <td>30</td>
      <td>6</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Raining without high winds</td>
      <td>Wet/Damp</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>Alba / Scotland</td>
      <td>AL2 1FS</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>121256</th>
      <td>599991</td>
      <td>13</td>
      <td>2</td>
      <td>0</td>
      <td>12/10/13</td>
      <td>6</td>
      <td>8:26</td>
      <td>143</td>
      <td>E10000034</td>
      <td>3</td>
      <td>19</td>
      <td>Dual carriageway</td>
      <td>40</td>
      <td>5</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>Roadworks</td>
      <td>None</td>
      <td>2</td>
      <td>Yes</td>
      <td>England</td>
      <td>BN3 3WA</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>121257</th>
      <td>599993</td>
      <td>1</td>
      <td>2</td>
      <td>0</td>
      <td>05/06/13</td>
      <td>5</td>
      <td>22:54</td>
      <td>7</td>
      <td>E09000016</td>
      <td>6</td>
      <td>13</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>6</td>
      <td>0</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Wet/Damp</td>
      <td>Roadworks</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>DL14 8HH</td>
      <td>United Kingdom</td>
    </tr>
    <tr>
      <th>121258</th>
      <td>600000</td>
      <td>1</td>
      <td>2</td>
      <td>0</td>
      <td>08/10/13</td>
      <td>2</td>
      <td>10:20</td>
      <td>22</td>
      <td>E09000025</td>
      <td>5</td>
      <td>13</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>6</td>
      <td>0</td>
      <td>Control by other authorised person</td>
      <td>Central refuge</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Wet/Damp</td>
      <td>Roadworks</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>E14 8JT</td>
      <td>United Kingdom</td>
    </tr>
  </tbody>
</table>
<p>121259 rows × 27 columns</p>
</div>


<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>postcode</th>
      <th>Accident_risk_index</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>AB10 1AU</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>AB10 1PG</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>AB10 1TT</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>AB10 1YP</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>AB10 6LQ</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>49767</th>
      <td>ZE2 9LZ</td>
      <td>0</td>
    </tr>
    <tr>
      <th>49768</th>
      <td>ZE2 9RE</td>
      <td>0</td>
    </tr>
    <tr>
      <th>49769</th>
      <td>ZE2 9RJ</td>
      <td>0</td>
    </tr>
    <tr>
      <th>49770</th>
      <td>ZE2 9SB</td>
      <td>0</td>
    </tr>
    <tr>
      <th>49771</th>
      <td>ZE2 9SD</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>49772 rows × 2 columns</p>
</div>



```python
test['Number_of_Casualties'].value_counts()
```


0    121259
Name: Number_of_Casualties, dtype: int64

-------------
As opposed to train data, in test data, all 'Number_of_Casualties' column values are 'zero'.

I will predict 'Number_of_Casualties' and then expect the value of 'Accident_risk_index' in submission data.

---------------


```python
roads_network = pd.read_csv("/kaggle/input/participantsdataset/roads_network.csv")
population = pd.read_csv("/kaggle/input/participantsdataset/population.csv")
display(roads_network,population)
```


<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>WKT</th>
      <th>roadClassi</th>
      <th>roadFuncti</th>
      <th>formOfWay</th>
      <th>length</th>
      <th>primaryRou</th>
      <th>distance to the nearest point on rd</th>
      <th>postcode</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>POINT (-2.3501 56.603923)</td>
      <td>A Road</td>
      <td>A Road</td>
      <td>Single Carriageway</td>
      <td>2643.0</td>
      <td>1.0</td>
      <td>1.256769</td>
      <td>AB1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>POINT (-2.021334 57.130142)</td>
      <td>A Road</td>
      <td>A Road</td>
      <td>Single Carriageway</td>
      <td>2643.0</td>
      <td>1.0</td>
      <td>1.834101</td>
      <td>AB1 9NN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>POINT (-2.108598 57.146338)</td>
      <td>A Road</td>
      <td>A Road</td>
      <td>Single Carriageway</td>
      <td>2643.0</td>
      <td>1.0</td>
      <td>1.830243</td>
      <td>AB10 1UH</td>
    </tr>
    <tr>
      <th>3</th>
      <td>POINT (-2.093928 57.148218)</td>
      <td>A Road</td>
      <td>A Road</td>
      <td>Single Carriageway</td>
      <td>2643.0</td>
      <td>1.0</td>
      <td>1.835092</td>
      <td>AB10 1YL</td>
    </tr>
    <tr>
      <th>4</th>
      <td>POINT (-2.116089 57.131671)</td>
      <td>A Road</td>
      <td>A Road</td>
      <td>Single Carriageway</td>
      <td>2643.0</td>
      <td>1.0</td>
      <td>1.814373</td>
      <td>AB10 6AT</td>
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
    </tr>
    <tr>
      <th>91561</th>
      <td>POINT (-0.82061 60.797906)</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>ZE2 9TJ</td>
    </tr>
    <tr>
      <th>91562</th>
      <td>POINT (-1.289882 59.890975)</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>ZE3 9</td>
    </tr>
    <tr>
      <th>91563</th>
      <td>POINT (-1.308846 59.882168)</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>ZE3 9JL</td>
    </tr>
    <tr>
      <th>91564</th>
      <td>POINT (-1.292023 59.877697)</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>ZE3 9JP</td>
    </tr>
    <tr>
      <th>91565</th>
      <td>POINT (-1.42145 53.450306)</td>
      <td>A Road</td>
      <td>A Road</td>
      <td>Single Carriageway</td>
      <td>295.0</td>
      <td>0.0</td>
      <td>0.000645</td>
      <td>ZE3 9JW</td>
    </tr>
  </tbody>
</table>
<p>91566 rows × 8 columns</p>
</div>


<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>postcode</th>
      <th>Rural Urban</th>
      <th>Variable: All usual residents; measures: Value</th>
      <th>Variable: Males; measures: Value</th>
      <th>Variable: Females; measures: Value</th>
      <th>Variable: Lives in a household; measures: Value</th>
      <th>Variable: Lives in a communal establishment; measures: Value</th>
      <th>Variable: Schoolchild or full-time student aged 4 and over at their non term-time address; measures: Value</th>
      <th>Variable: Area (Hectares); measures: Value</th>
      <th>Variable: Density (number of persons per hectare); measures: Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>AL1  1</td>
      <td>Total</td>
      <td>5453</td>
      <td>2715</td>
      <td>2738</td>
      <td>5408</td>
      <td>45</td>
      <td>75</td>
      <td>225.63</td>
      <td>24.2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>AL1  2</td>
      <td>Total</td>
      <td>6523</td>
      <td>3183</td>
      <td>3340</td>
      <td>6418</td>
      <td>105</td>
      <td>77</td>
      <td>286.59</td>
      <td>22.8</td>
    </tr>
    <tr>
      <th>2</th>
      <td>AL1  3</td>
      <td>Total</td>
      <td>4179</td>
      <td>2121</td>
      <td>2058</td>
      <td>4100</td>
      <td>79</td>
      <td>46</td>
      <td>97.12</td>
      <td>43.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>AL1  4</td>
      <td>Total</td>
      <td>9799</td>
      <td>4845</td>
      <td>4954</td>
      <td>9765</td>
      <td>34</td>
      <td>285</td>
      <td>244.75</td>
      <td>40.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>AL1  5</td>
      <td>Total</td>
      <td>10226</td>
      <td>5129</td>
      <td>5097</td>
      <td>10211</td>
      <td>15</td>
      <td>133</td>
      <td>200.93</td>
      <td>50.9</td>
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
    </tr>
    <tr>
      <th>8030</th>
      <td>SA73 3</td>
      <td>Total</td>
      <td>5246</td>
      <td>2515</td>
      <td>2731</td>
      <td>5244</td>
      <td>2</td>
      <td>59</td>
      <td>1284.14</td>
      <td>4.1</td>
    </tr>
    <tr>
      <th>8031</th>
      <td>SA8  3</td>
      <td>Total</td>
      <td>4769</td>
      <td>2344</td>
      <td>2425</td>
      <td>4736</td>
      <td>33</td>
      <td>59</td>
      <td>2061.58</td>
      <td>2.3</td>
    </tr>
    <tr>
      <th>8032</th>
      <td>SA8  4</td>
      <td>Total</td>
      <td>7787</td>
      <td>3816</td>
      <td>3971</td>
      <td>7673</td>
      <td>114</td>
      <td>76</td>
      <td>3174.90</td>
      <td>2.5</td>
    </tr>
    <tr>
      <th>8033</th>
      <td>SA9  1</td>
      <td>Total</td>
      <td>7898</td>
      <td>3827</td>
      <td>4071</td>
      <td>7723</td>
      <td>175</td>
      <td>67</td>
      <td>8164.17</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>8034</th>
      <td>SA9  2</td>
      <td>Total</td>
      <td>7281</td>
      <td>3595</td>
      <td>3686</td>
      <td>7253</td>
      <td>28</td>
      <td>69</td>
      <td>3306.61</td>
      <td>2.2</td>
    </tr>
  </tbody>
</table>
<p>8035 rows × 10 columns</p>
</div>

------------------
'postcode' columns are in train, test, road_network, and population, which is beneficial for merge.
 However, we should delete the useless data for predicting the 'Number_of_Casualties' while training only meaningful columns
 Concerning the properties and amounts of data, 'length' column in road_network data look most useful factor.
In addition, according to the unique counts of data, in population data, 'Variable: All usual residents; measures: Value', 'Variable: Lives in a household; measures: Value', 뭉 'Variable: Area (Hectares); measures: Value' look so elegible.

------------

```python
display(roads_network['WKT'].value_counts(),roads_network['roadClassi'].value_counts(),roads_network['roadFuncti'].value_counts(),roads_network['formOfWay'].value_counts(),roads_network['length'].value_counts(),roads_network['primaryRou'].value_counts(),roads_network['distance to the nearest point on rd'].value_counts())
```



POINT (-1.453595 53.423419)    4

POINT (-1.231984 51.615318)    4

POINT (-1.453592 53.423635)    4

POINT (-1.453836 53.42342)     4

POINT (-4.905896 51.672221)    4
..
POINT (-0.439516 51.778167)    1

POINT (-0.439738 51.778458)    1

POINT (-0.438121 51.778293)    1

POINT (-0.412476 51.772122)    1

POINT (-1.42145 53.450306)     1

Name: WKT, Length: 75864, dtype: int64

A Road      90033

Motorway      319

Name: roadClassi, dtype: int64

A Road      90033

Motorway      319

Name: roadFuncti, dtype: int64

Single Carriageway            46015

Collapsed Dual Carriageway    22290

Roundabout                    16667

Slip Road                      3469

Dual Carriageway               1911

Name: formOfWay, dtype: int64

2643.0    1863

65.0      1471

500.0     1275

34.0      1271

21.0      1196
... 
1616.0       1

1556.0       1

1455.0       1

1374.0       1

614.0        1

Name: length, Length: 1665, dtype: int64

1.0    66036

0.0    24316

Name: primaryRou, dtype: int64

0.015753    4

0.016072    4

0.033832    4

0.007051    4

0.015898    4
..
0.122929    1

0.058770    1

0.039234    1

0.036343    1

0.000645    1

Name: distance to the nearest point on rd, Length: 74641, dtype: int64



```python
population.nunique()
```


postcode                                                                                                      8035

Rural Urban                                                                                                      1

Variable: All usual residents; measures: Value                                                                6060

Variable: Males; measures: Value                                                                              4736

Variable: Females; measures: Value                                                                            4767

Variable: Lives in a household; measures: Value                                                               6072

Variable: Lives in a communal establishment; measures: Value                                                   729

Variable: Schoolchild or full-time student aged 4 and over at their non term-time address; measures: Value     301

Variable: Area (Hectares); measures: Value                                                                    7813

Variable: Density (number of persons per hectare); measures: Value                                            1182

dtype: int64


```python
roads_network_postcode_length = roads_network.groupby("postcode")["length"].mean()
roads_network_postcode_length
```

postcode

AB1         2643.0

AB1 9NN     2643.0

AB10 1UH    2643.0

AB10 1YL    2643.0

AB10 6AT    2643.0
...  
ZE3 9          NaN

ZE3 9JL        NaN

ZE3 9JP        NaN

ZE3 9JW      295.0

m23 5bt      934.0

Name: length, Length: 75895, dtype: float64



```python
population_postcode_values = population.groupby("postcode")["Variable: All usual residents; measures: Value"].mean()
population_postcode_values
```

postcode

AL1  1     5453.0

AL1  2     6523.0

AL1  3     4179.0

AL1  4     9799.0

AL1  5    10226.0
...   
YO8  4     6998.0

YO8  5     6557.0

YO8  6     5096.0

YO8  8     8413.0

YO8  9    12226.0

Name: Variable: All usual residents; measures: Value, Length: 8035, dtype: float64



```python
population_postcode_values2 = population.groupby("postcode")["Variable: Lives in a household; measures: Value"].mean()
population_postcode_values2
```

postcode

AL1  1     5408.0

AL1  2     6418.0

AL1  3     4100.0

AL1  4     9765.0

AL1  5    10211.0
...   
YO8  4     6886.0

YO8  5     6526.0

YO8  6     5096.0

YO8  8     8310.0

YO8  9    12169.0

Name: Variable: Lives in a household; measures: Value, Length: 8035, dtype: float64



```python
population_postcode_values3 = population.groupby("postcode")["Variable: Area (Hectares); measures: Value"].mean()
population_postcode_values3
```

postcode

AL1  1     225.63

AL1  2     286.59

AL1  3      97.12

AL1  4     244.75

AL1  5     200.93
...   
YO8  4     329.16

YO8  5    4053.79

YO8  6    8083.27

YO8  8    6484.91

YO8  9    2703.83

Name: Variable: Area (Hectares); measures: Value, Length: 8035, dtype: float64



```python
train.nunique() 
```



Accident_ID                                    478741

Police_Force                                       66


Number_of_Vehicles                                  4

Number_of_Casualties                                5

Date                                              366

Day_of_Week                                         7

Time                                             1367

Local_Authority_(District)                        880

Local_Authority_(Highway)                         207

1st_Road_Class                                      5

1st_Road_Number                                  5464

Road_Type                                           6

Speed_limit                                         6

2nd_Road_Class                                      5

2nd_Road_Number                                     1

Pedestrian_Crossing-Human_Control                   3

Pedestrian_Crossing-Physical_Facilities             6

Light_Conditions                                    5

Weather_Conditions                                  9

Road_Surface_Conditions                             5

Special_Conditions_at_Site                          8

Carriageway_Hazards                                 6

Urban_or_Rural_Area                                 2

Did_Police_Officer_Attend_Scene_of_Accident         2

state                                               3

postcode                                        95625

country                                             1

dtype: int64




```python
test.nunique() 
```



Accident_ID                                    121259

Police_Force                                       60

Number_of_Vehicles                                  4

Number_of_Casualties                                1

Date                                              365

Day_of_Week                                         7

Time                                             1302

Local_Authority_(District)                        778

Local_Authority_(Highway)                         205

1st_Road_Class                                      5

1st_Road_Number                                  3827


Road_Type                                           6

Speed_limit                                         6

2nd_Road_Class                                      5

2nd_Road_Number                                     1

Pedestrian_Crossing-Human_Control                   3

Pedestrian_Crossing-Physical_Facilities             6


Light_Conditions                                    5

Weather_Conditions                                  9

Road_Surface_Conditions                             5

Special_Conditions_at_Site                          8

Carriageway_Hazards                                 6


Urban_or_Rural_Area                                 2

Did_Police_Officer_Attend_Scene_of_Accident         2

state                                               3

postcode                                        49772

country                                             1

dtype: int64





```python

train["Number_of_Casualties"].value_counts()

```



1    329124

2     98814

3     35399

4      9318

5      6086

Name: Number_of_Casualties, dtype: int64

-----------
We should examine the properties of individual columns in terms of correlation with result. I think that the one whose number is less than one, it is not effective to predict the answer. Therefore, I would delete the columns of '2nd_Road_Number', 'country' as well as removing the target column, 'Number_of_casualties'. I will merge the train and test into alldata with additionally helpful columns. I will also distribute the date columns into more specified columns.

-----------

```python
allData = pd.concat([train, test], axis=0)
allData = pd.merge(allData, roads_network_postcode_length, how="left", on="postcode")
allData = pd.merge(allData, population_postcode_values, how="left", on="postcode")
allData = pd.merge(allData, population_postcode_values2, how="left", on="postcode")
allData = pd.merge(allData, population_postcode_values3, how="left", on="postcode")


allData["Date"] = pd.to_datetime(allData["Date"])
allData["Time"] = pd.to_datetime(allData["Time"])
allData["hour"] = allData["Time"].dt.hour
allData["minute"] = allData["Time"].dt.minute
allData["month"] = allData["Date"].dt.month
allData["day"] = allData["Date"].dt.day
```
-----------
With boxplot below, we can find the correlation between allData["Day_of_Week"] and allData["Number_of_Casualties"].

------------

```python
import matplotlib.pyplot as plt
import seaborn as sns
plt.figure(figsize=(16,8))
sns.boxplot(allData["Day_of_Week"],allData["Number_of_Casualties"],showfliers=False)
```


<img src="data:image/png;base64,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"/>


```python
allData2 = allData.drop(columns=["2nd_Road_Number", "country", "Number_of_Casualties", "Accident_ID","Date","Time"])
allData2
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Police_Force</th>
      <th>Number_of_Vehicles</th>
      <th>Day_of_Week</th>
      <th>Local_Authority_(District)</th>
      <th>Local_Authority_(Highway)</th>
      <th>1st_Road_Class</th>
      <th>1st_Road_Number</th>
      <th>Road_Type</th>
      <th>Speed_limit</th>
      <th>2nd_Road_Class</th>
      <th>Pedestrian_Crossing-Human_Control</th>
      <th>Pedestrian_Crossing-Physical_Facilities</th>
      <th>Light_Conditions</th>
      <th>Weather_Conditions</th>
      <th>Road_Surface_Conditions</th>
      <th>Special_Conditions_at_Site</th>
      <th>Carriageway_Hazards</th>
      <th>Urban_or_Rural_Area</th>
      <th>Did_Police_Officer_Attend_Scene_of_Accident</th>
      <th>state</th>
      <th>postcode</th>
      <th>length</th>
      <th>Variable: All usual residents; measures: Value</th>
      <th>Variable: Lives in a household; measures: Value</th>
      <th>Variable: Area (Hectares); measures: Value</th>
      <th>hour</th>
      <th>minute</th>
      <th>month</th>
      <th>day</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>34</td>
      <td>2</td>
      <td>7</td>
      <td>344</td>
      <td>E10000032</td>
      <td>4</td>
      <td>395</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>-1</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>Ol or diesel</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>OX3 9UP</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13.0</td>
      <td>20.0</td>
      <td>12</td>
      <td>19</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5</td>
      <td>2</td>
      <td>4</td>
      <td>102</td>
      <td>E09000026</td>
      <td>3</td>
      <td>13</td>
      <td>One way street</td>
      <td>30</td>
      <td>-1</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Raining without high winds</td>
      <td>Dry</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>No</td>
      <td>England</td>
      <td>S35 4EZ</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7.0</td>
      <td>53.0</td>
      <td>2</td>
      <td>11</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>2</td>
      <td>4</td>
      <td>531</td>
      <td>E10000016</td>
      <td>6</td>
      <td>8</td>
      <td>Roundabout</td>
      <td>40</td>
      <td>6</td>
      <td>None within 50 metres</td>
      <td>Zebra crossing</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>No</td>
      <td>England</td>
      <td>BN21 2XR</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>16.0</td>
      <td>0.0</td>
      <td>2</td>
      <td>11</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>7</td>
      <td>E08000035</td>
      <td>6</td>
      <td>13</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>6</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>Roadworks</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>TA20 3PT</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>16.0</td>
      <td>50.0</td>
      <td>6</td>
      <td>5</td>
    </tr>
    <tr>
      <th>4</th>
      <td>46</td>
      <td>1</td>
      <td>3</td>
      <td>519</td>
      <td>E10000031</td>
      <td>3</td>
      <td>24</td>
      <td>Dual carriageway</td>
      <td>30</td>
      <td>6</td>
      <td>None within 50 metres</td>
      <td>Zebra crossing</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>No</td>
      <td>England</td>
      <td>DN20 0QF</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13.0</td>
      <td>25.0</td>
      <td>6</td>
      <td>30</td>
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
    </tr>
    <tr>
      <th>599995</th>
      <td>1</td>
      <td>2</td>
      <td>5</td>
      <td>6</td>
      <td>E06000042</td>
      <td>6</td>
      <td>0</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>3</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Darkness: Street lights present and lit</td>
      <td>Fine without high winds</td>
      <td>Wet/Damp</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>HD9 4AB</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18.0</td>
      <td>31.0</td>
      <td>5</td>
      <td>7</td>
    </tr>
    <tr>
      <th>599996</th>
      <td>62</td>
      <td>2</td>
      <td>6</td>
      <td>633</td>
      <td>W06000004</td>
      <td>3</td>
      <td>379</td>
      <td>Dual carriageway</td>
      <td>30</td>
      <td>6</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Raining without high winds</td>
      <td>Wet/Damp</td>
      <td>None</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>Alba / Scotland</td>
      <td>AL2 1FS</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7.0</td>
      <td>40.0</td>
      <td>11</td>
      <td>22</td>
    </tr>
    <tr>
      <th>599997</th>
      <td>13</td>
      <td>2</td>
      <td>6</td>
      <td>143</td>
      <td>E10000034</td>
      <td>3</td>
      <td>19</td>
      <td>Dual carriageway</td>
      <td>40</td>
      <td>5</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Dry</td>
      <td>Roadworks</td>
      <td>None</td>
      <td>2</td>
      <td>Yes</td>
      <td>England</td>
      <td>BN3 3WA</td>
      <td>125.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>8.0</td>
      <td>26.0</td>
      <td>12</td>
      <td>10</td>
    </tr>
    <tr>
      <th>599998</th>
      <td>1</td>
      <td>2</td>
      <td>5</td>
      <td>7</td>
      <td>E09000016</td>
      <td>6</td>
      <td>13</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>6</td>
      <td>None within 50 metres</td>
      <td>No physical crossing within 50 meters</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Wet/Damp</td>
      <td>Roadworks</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>DL14 8HH</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>54.0</td>
      <td>5</td>
      <td>6</td>
    </tr>
    <tr>
      <th>599999</th>
      <td>1</td>
      <td>2</td>
      <td>2</td>
      <td>22</td>
      <td>E09000025</td>
      <td>5</td>
      <td>13</td>
      <td>Single carriageway</td>
      <td>30</td>
      <td>6</td>
      <td>Control by other authorised person</td>
      <td>Central refuge</td>
      <td>Daylight: Street light present</td>
      <td>Fine without high winds</td>
      <td>Wet/Damp</td>
      <td>Roadworks</td>
      <td>None</td>
      <td>1</td>
      <td>Yes</td>
      <td>England</td>
      <td>E14 8JT</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>10.0</td>
      <td>20.0</td>
      <td>8</td>
      <td>10</td>
    </tr>
  </tbody>
</table>
<p>600000 rows × 29 columns</p>
</div>

-------
The several values of columns are range, which will be transformed into the label encoding.

--------

```python
from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

category_cols = allData2.columns[allData2.dtypes=="object"]
category_cols

for i in category_cols:
    allData2[i] = le.fit_transform(allData2[i])
    
allData2
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Police_Force</th>
      <th>Number_of_Vehicles</th>
      <th>Day_of_Week</th>
      <th>Local_Authority_(District)</th>
      <th>Local_Authority_(Highway)</th>
      <th>1st_Road_Class</th>
      <th>1st_Road_Number</th>
      <th>Road_Type</th>
      <th>Speed_limit</th>
      <th>2nd_Road_Class</th>
      <th>Pedestrian_Crossing-Human_Control</th>
      <th>Pedestrian_Crossing-Physical_Facilities</th>
      <th>Light_Conditions</th>
      <th>Weather_Conditions</th>
      <th>Road_Surface_Conditions</th>
      <th>Special_Conditions_at_Site</th>
      <th>Carriageway_Hazards</th>
      <th>Urban_or_Rural_Area</th>
      <th>Did_Police_Officer_Attend_Scene_of_Accident</th>
      <th>state</th>
      <th>postcode</th>
      <th>length</th>
      <th>Variable: All usual residents; measures: Value</th>
      <th>Variable: Lives in a household; measures: Value</th>
      <th>Variable: Area (Hectares); measures: Value</th>
      <th>hour</th>
      <th>minute</th>
      <th>month</th>
      <th>day</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>34</td>
      <td>2</td>
      <td>7</td>
      <td>344</td>
      <td>150</td>
      <td>4</td>
      <td>395</td>
      <td>3</td>
      <td>30</td>
      <td>-1</td>
      <td>2</td>
      <td>2</td>
      <td>4</td>
      <td>1</td>
      <td>0</td>
      <td>4</td>
      <td>3</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>63244</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13.0</td>
      <td>20.0</td>
      <td>12</td>
      <td>19</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5</td>
      <td>2</td>
      <td>4</td>
      <td>102</td>
      <td>117</td>
      <td>3</td>
      <td>13</td>
      <td>1</td>
      <td>30</td>
      <td>-1</td>
      <td>2</td>
      <td>2</td>
      <td>4</td>
      <td>5</td>
      <td>0</td>
      <td>3</td>
      <td>3</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>72569</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7.0</td>
      <td>53.0</td>
      <td>2</td>
      <td>11</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>2</td>
      <td>4</td>
      <td>531</td>
      <td>136</td>
      <td>6</td>
      <td>8</td>
      <td>2</td>
      <td>40</td>
      <td>6</td>
      <td>2</td>
      <td>4</td>
      <td>4</td>
      <td>1</td>
      <td>0</td>
      <td>3</td>
      <td>3</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>7991</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>16.0</td>
      <td>0.0</td>
      <td>2</td>
      <td>11</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>7</td>
      <td>90</td>
      <td>6</td>
      <td>13</td>
      <td>3</td>
      <td>30</td>
      <td>6</td>
      <td>2</td>
      <td>2</td>
      <td>4</td>
      <td>1</td>
      <td>0</td>
      <td>7</td>
      <td>3</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>86698</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>16.0</td>
      <td>50.0</td>
      <td>6</td>
      <td>5</td>
    </tr>
    <tr>
      <th>4</th>
      <td>46</td>
      <td>1</td>
      <td>3</td>
      <td>519</td>
      <td>149</td>
      <td>3</td>
      <td>24</td>
      <td>0</td>
      <td>30</td>
      <td>6</td>
      <td>2</td>
      <td>4</td>
      <td>4</td>
      <td>1</td>
      <td>0</td>
      <td>3</td>
      <td>3</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>23334</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13.0</td>
      <td>25.0</td>
      <td>6</td>
      <td>30</td>
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
    </tr>
    <tr>
      <th>599995</th>
      <td>1</td>
      <td>2</td>
      <td>5</td>
      <td>6</td>
      <td>41</td>
      <td>6</td>
      <td>0</td>
      <td>3</td>
      <td>30</td>
      <td>3</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>1</td>
      <td>4</td>
      <td>3</td>
      <td>3</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>35428</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18.0</td>
      <td>31.0</td>
      <td>5</td>
      <td>7</td>
    </tr>
    <tr>
      <th>599996</th>
      <td>62</td>
      <td>2</td>
      <td>6</td>
      <td>633</td>
      <td>188</td>
      <td>3</td>
      <td>379</td>
      <td>0</td>
      <td>30</td>
      <td>6</td>
      <td>2</td>
      <td>2</td>
      <td>4</td>
      <td>5</td>
      <td>4</td>
      <td>3</td>
      <td>3</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>754</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7.0</td>
      <td>40.0</td>
      <td>11</td>
      <td>22</td>
    </tr>
    <tr>
      <th>599997</th>
      <td>13</td>
      <td>2</td>
      <td>6</td>
      <td>143</td>
      <td>151</td>
      <td>3</td>
      <td>19</td>
      <td>0</td>
      <td>40</td>
      <td>5</td>
      <td>2</td>
      <td>2</td>
      <td>4</td>
      <td>1</td>
      <td>0</td>
      <td>7</td>
      <td>3</td>
      <td>2</td>
      <td>1</td>
      <td>2</td>
      <td>8235</td>
      <td>125.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>8.0</td>
      <td>26.0</td>
      <td>12</td>
      <td>10</td>
    </tr>
    <tr>
      <th>599998</th>
      <td>1</td>
      <td>2</td>
      <td>5</td>
      <td>7</td>
      <td>107</td>
      <td>6</td>
      <td>13</td>
      <td>3</td>
      <td>30</td>
      <td>6</td>
      <td>2</td>
      <td>2</td>
      <td>4</td>
      <td>1</td>
      <td>4</td>
      <td>7</td>
      <td>3</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>22096</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>54.0</td>
      <td>5</td>
      <td>6</td>
    </tr>
    <tr>
      <th>599999</th>
      <td>1</td>
      <td>2</td>
      <td>2</td>
      <td>22</td>
      <td>116</td>
      <td>5</td>
      <td>13</td>
      <td>3</td>
      <td>30</td>
      <td>6</td>
      <td>0</td>
      <td>0</td>
      <td>4</td>
      <td>1</td>
      <td>4</td>
      <td>7</td>
      <td>3</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>25784</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>10.0</td>
      <td>20.0</td>
      <td>8</td>
      <td>10</td>
    </tr>
  </tbody>
</table>
<p>600000 rows × 29 columns</p>
</div>

------------
In order to train the boosting, we should divide the refiend alldata2 into train2 and test2.

---------

```python
train2 = allData2[:len(train)]
test2 = allData2[len(train):]
```
-----------
We can make training the ["Number_of_Casualties"] column by using CatBoostRegressor.

----------

```python
from catboost import CatBoostRegressor

cbr = CatBoostRegressor(verbose=100, cat_features=np.where(train2.dtypes=="int")[0], task_type="GPU") # 문자열 컬럼을 지정해줌으로 성능 개선 가능
cbr.fit(train2, train["Number_of_Casualties"])
```


Learning rate set to 0.090658

0:	learn: 0.8151880	total: 59.6ms	remaining: 59.5s

100:	learn: 0.8091451	total: 6.2s	remaining: 55.2s

200:	learn: 0.8085206	total: 12.6s	remaining: 50.3s

300:	learn: 0.8078881	total: 18.8s	remaining: 43.5s

400:	learn: 0.8073783	total: 25.3s	remaining: 37.7s

500:	learn: 0.8068537	total: 32.8s	remaining: 32.7s

600:	learn: 0.8063541	total: 39.1s	remaining: 26s

700:	learn: 0.8058819	total: 46s	remaining: 19.6s

800:	learn: 0.8054018	total: 52.7s	remaining: 13.1s

900:	learn: 0.8049232	total: 59.4s	remaining: 6.53s

999:	learn: 0.8044456	total: 1m 6s	remaining: 0us

<catboost.core.CatBoostRegressor at 0x7f8f4bd7fa50>


```python
result = cbr.predict(test2)
result
```


array([1.56039144, 1.40014073, 1.5783172 , ..., 1.63602668, 1.20295673,
 1.23252492])

```python
test["result"] = result
```
--------
The mean value of individual postcode will be result to submission data.

---------

```python
result_mean = test.groupby("postcode")["result"].mean().values
result_mean
```


array([1.35854604, 1.32673513, 1.44144427, ..., 1.22782925, 1.53374147,
1.32462278])


```python
sub["Accident_risk_index"] = result_mean
sub.to_csv("submissoin.csv")
```


```python
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>postcode</th>
      <th>Accident_risk_index</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>AB10 1AU</td>
      <td>1.358546</td>
    </tr>
    <tr>
      <th>1</th>
      <td>AB10 1PG</td>
      <td>1.326735</td>
    </tr>
    <tr>
      <th>2</th>
      <td>AB10 1TT</td>
      <td>1.441444</td>
    </tr>
    <tr>
      <th>3</th>
      <td>AB10 1YP</td>
      <td>1.388424</td>
    </tr>
    <tr>
      <th>4</th>
      <td>AB10 6LQ</td>
      <td>1.348133</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>49767</th>
      <td>ZE2 9LZ</td>
      <td>1.335666</td>
    </tr>
    <tr>
      <th>49768</th>
      <td>ZE2 9RE</td>
      <td>1.342281</td>
    </tr>
    <tr>
      <th>49769</th>
      <td>ZE2 9RJ</td>
      <td>1.227829</td>
    </tr>
    <tr>
      <th>49770</th>
      <td>ZE2 9SB</td>
      <td>1.533741</td>
    </tr>
    <tr>
      <th>49771</th>
      <td>ZE2 9SD</td>
      <td>1.324623</td>
    </tr>
  </tbody>
</table>
<p>49772 rows × 2 columns</p>
</div>

