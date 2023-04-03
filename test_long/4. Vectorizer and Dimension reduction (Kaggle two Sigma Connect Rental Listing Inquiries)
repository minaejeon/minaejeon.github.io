
# 4. Vectorizer and Dimension reduction (Kaggle two Sigma Connect Rental Listing Inquiries)



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


/kaggle/input/two-sigma-connect-rental-listing-inquiries/images_sample.zip

/kaggle/input/two-sigma-connect-rental-listing-inquiries/Kaggle-renthop.torrent

/kaggle/input/two-sigma-connect-rental-listing-inquiries/sample_submission.csv.zip

/kaggle/input/two-sigma-connect-rental-listing-inquiries/test.json.zip

/kaggle/input/two-sigma-connect-rental-listing-inquiries/train.json.zip


```python
train=pd.read_json('/kaggle/input/two-sigma-connect-rental-listing-inquiries/train.json.zip')
test=pd.read_json('/kaggle/input/two-sigma-connect-rental-listing-inquiries/test.json.zip')
sub=pd.read_csv('/kaggle/input/two-sigma-connect-rental-listing-inquiries/sample_submission.csv.zip')
display(train,test)
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>bathrooms</th>
      <th>bedrooms</th>
      <th>building_id</th>
      <th>created</th>
      <th>description</th>
      <th>display_address</th>
      <th>features</th>
      <th>latitude</th>
      <th>listing_id</th>
      <th>longitude</th>
      <th>manager_id</th>
      <th>photos</th>
      <th>price</th>
      <th>street_address</th>
      <th>interest_level</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>1.0</td>
      <td>1</td>
      <td>8579a0b0d54db803821a35a4a615e97a</td>
      <td>2016-06-16 05:55:27</td>
      <td>Spacious 1 Bedroom 1 Bathroom in Williamsburg!...</td>
      <td>145 Borinquen Place</td>
      <td>[Dining Room, Pre-War, Laundry in Building, Di...</td>
      <td>40.7108</td>
      <td>7170325</td>
      <td>-73.9539</td>
      <td>a10db4590843d78c784171a107bdacb4</td>
      <td>[https://photos.renthop.com/2/7170325_3bb5ac84...</td>
      <td>2400</td>
      <td>145 Borinquen Place</td>
      <td>medium</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1.0</td>
      <td>2</td>
      <td>b8e75fc949a6cd8225b455648a951712</td>
      <td>2016-06-01 05:44:33</td>
      <td>BRAND NEW GUT RENOVATED TRUE 2 BEDROOMFind you...</td>
      <td>East 44th</td>
      <td>[Doorman, Elevator, Laundry in Building, Dishw...</td>
      <td>40.7513</td>
      <td>7092344</td>
      <td>-73.9722</td>
      <td>955db33477af4f40004820b4aed804a0</td>
      <td>[https://photos.renthop.com/2/7092344_7663c19a...</td>
      <td>3800</td>
      <td>230 East 44th</td>
      <td>low</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1.0</td>
      <td>2</td>
      <td>cd759a988b8f23924b5a2058d5ab2b49</td>
      <td>2016-06-14 15:19:59</td>
      <td>**FLEX 2 BEDROOM WITH FULL PRESSURIZED WALL**L...</td>
      <td>East 56th Street</td>
      <td>[Doorman, Elevator, Laundry in Building, Laund...</td>
      <td>40.7575</td>
      <td>7158677</td>
      <td>-73.9625</td>
      <td>c8b10a317b766204f08e613cef4ce7a0</td>
      <td>[https://photos.renthop.com/2/7158677_c897a134...</td>
      <td>3495</td>
      <td>405 East 56th Street</td>
      <td>medium</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1.5</td>
      <td>3</td>
      <td>53a5b119ba8f7b61d4e010512e0dfc85</td>
      <td>2016-06-24 07:54:24</td>
      <td>A Brand New 3 Bedroom 1.5 bath ApartmentEnjoy ...</td>
      <td>Metropolitan Avenue</td>
      <td>[]</td>
      <td>40.7145</td>
      <td>7211212</td>
      <td>-73.9425</td>
      <td>5ba989232d0489da1b5f2c45f6688adc</td>
      <td>[https://photos.renthop.com/2/7211212_1ed4542e...</td>
      <td>3000</td>
      <td>792 Metropolitan Avenue</td>
      <td>medium</td>
    </tr>
    <tr>
      <th>15</th>
      <td>1.0</td>
      <td>0</td>
      <td>bfb9405149bfff42a92980b594c28234</td>
      <td>2016-06-28 03:50:23</td>
      <td>Over-sized Studio w abundant closets. Availabl...</td>
      <td>East 34th Street</td>
      <td>[Doorman, Elevator, Fitness Center, Laundry in...</td>
      <td>40.7439</td>
      <td>7225292</td>
      <td>-73.9743</td>
      <td>2c3b41f588fbb5234d8a1e885a436cfa</td>
      <td>[https://photos.renthop.com/2/7225292_901f1984...</td>
      <td>2795</td>
      <td>340 East 34th Street</td>
      <td>low</td>
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
    </tr>
    <tr>
      <th>124000</th>
      <td>1.0</td>
      <td>3</td>
      <td>92bbbf38baadfde0576fc496bd41749c</td>
      <td>2016-04-05 03:58:33</td>
      <td>There is 700 square feet of recently renovated...</td>
      <td>W 171 Street</td>
      <td>[Elevator, Dishwasher, Hardwood Floors]</td>
      <td>40.8433</td>
      <td>6824800</td>
      <td>-73.9396</td>
      <td>a61e21da3ba18c7a3d54cfdcc247e1f8</td>
      <td>[https://photos.renthop.com/2/6824800_0682be16...</td>
      <td>2800</td>
      <td>620 W 171 Street</td>
      <td>low</td>
    </tr>
    <tr>
      <th>124002</th>
      <td>1.0</td>
      <td>2</td>
      <td>5565db9b7cba3603834c4aa6f2950960</td>
      <td>2016-04-02 02:25:31</td>
      <td>2 bedroom apartment with updated kitchen, rece...</td>
      <td>Broadway</td>
      <td>[Common Outdoor Space, Cats Allowed, Dogs Allo...</td>
      <td>40.8198</td>
      <td>6813268</td>
      <td>-73.9578</td>
      <td>8f90e5e10e8a2d7cf997f016d89230eb</td>
      <td>[https://photos.renthop.com/2/6813268_1e6fcc32...</td>
      <td>2395</td>
      <td>3333 Broadway</td>
      <td>medium</td>
    </tr>
    <tr>
      <th>124004</th>
      <td>1.0</td>
      <td>1</td>
      <td>67997a128056ee1ed7d046bbb856e3c7</td>
      <td>2016-04-26 05:42:03</td>
      <td>No Brokers Fee * Never Lived 1 Bedroom 1 Bathr...</td>
      <td>210 Brighton 15th St</td>
      <td>[Dining Room, Elevator, Pre-War, Laundry in Bu...</td>
      <td>40.5765</td>
      <td>6927093</td>
      <td>-73.9554</td>
      <td>a10db4590843d78c784171a107bdacb4</td>
      <td>[https://photos.renthop.com/2/6927093_93a52104...</td>
      <td>1850</td>
      <td>210 Brighton 15th St</td>
      <td>medium</td>
    </tr>
    <tr>
      <th>124008</th>
      <td>1.0</td>
      <td>2</td>
      <td>3c0574a740154806c18bdf1fddd3d966</td>
      <td>2016-04-19 02:47:33</td>
      <td>Wonderful Bright Chelsea 2 Bedroom apartment o...</td>
      <td>West 21st Street</td>
      <td>[Pre-War, Laundry in Unit, Dishwasher, No Fee,...</td>
      <td>40.7448</td>
      <td>6892816</td>
      <td>-74.0017</td>
      <td>c3cd45f4381ac371507090e9ffabea80</td>
      <td>[https://photos.renthop.com/2/6892816_1a8d087a...</td>
      <td>4195</td>
      <td>350 West 21st Street</td>
      <td>medium</td>
    </tr>
    <tr>
      <th>124009</th>
      <td>1.0</td>
      <td>3</td>
      <td>d89f514c3ed0abaae52cba7017ac0701</td>
      <td>2016-04-20 05:34:00</td>
      <td>***PRIME MIDTOWN EAST OFF PARK AVE***TRUE 3 BE...</td>
      <td>E 54th St</td>
      <td>[Dining Room, Elevator, Laundry in Building, D...</td>
      <td>40.7594</td>
      <td>6901023</td>
      <td>-73.9712</td>
      <td>e90f2ded843cdb2efd65ef47d9fc8029</td>
      <td>[https://photos.renthop.com/2/6901023_02052d90...</td>
      <td>4280</td>
      <td>123 E 54th St</td>
      <td>high</td>
    </tr>
  </tbody>
</table>
<p>49352 rows × 15 columns</p>
</div>


<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>bathrooms</th>
      <th>bedrooms</th>
      <th>building_id</th>
      <th>created</th>
      <th>description</th>
      <th>display_address</th>
      <th>features</th>
      <th>latitude</th>
      <th>listing_id</th>
      <th>longitude</th>
      <th>manager_id</th>
      <th>photos</th>
      <th>price</th>
      <th>street_address</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.0</td>
      <td>1</td>
      <td>79780be1514f645d7e6be99a3de696c5</td>
      <td>2016-06-11 05:29:41</td>
      <td>Large with awesome terrace--accessible via bed...</td>
      <td>Suffolk Street</td>
      <td>[Elevator, Laundry in Building, Laundry in Uni...</td>
      <td>40.7185</td>
      <td>7142618</td>
      <td>-73.9865</td>
      <td>b1b1852c416d78d7765d746cb1b8921f</td>
      <td>[https://photos.renthop.com/2/7142618_1c45a2c8...</td>
      <td>2950</td>
      <td>99 Suffolk Street</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1.0</td>
      <td>2</td>
      <td>0</td>
      <td>2016-06-24 06:36:34</td>
      <td>Prime Soho - between Bleecker and Houston - Ne...</td>
      <td>Thompson Street</td>
      <td>[Pre-War, Dogs Allowed, Cats Allowed]</td>
      <td>40.7278</td>
      <td>7210040</td>
      <td>-74.0000</td>
      <td>d0b5648017832b2427eeb9956d966a14</td>
      <td>[https://photos.renthop.com/2/7210040_d824cc71...</td>
      <td>2850</td>
      <td>176 Thompson Street</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1.0</td>
      <td>0</td>
      <td>0</td>
      <td>2016-06-17 01:23:39</td>
      <td>Spacious studio in Prime Location. Cleanbuildi...</td>
      <td>Sullivan Street</td>
      <td>[Pre-War, Dogs Allowed, Cats Allowed]</td>
      <td>40.7260</td>
      <td>7174566</td>
      <td>-74.0026</td>
      <td>e6472c7237327dd3903b3d6f6a94515a</td>
      <td>[https://photos.renthop.com/2/7174566_ba3a35c5...</td>
      <td>2295</td>
      <td>115 Sullivan Street</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1.0</td>
      <td>2</td>
      <td>f9c826104b91d868e69bd25746448c0c</td>
      <td>2016-06-21 05:06:02</td>
      <td>For immediate access call Bryan.&lt;br /&gt;&lt;br /&gt;Bo...</td>
      <td>Jones Street</td>
      <td>[Hardwood Floors, Dogs Allowed, Cats Allowed]</td>
      <td>40.7321</td>
      <td>7191391</td>
      <td>-74.0028</td>
      <td>41735645e0f8f13993c42894023f8e58</td>
      <td>[https://photos.renthop.com/2/7191391_8c2f2d49...</td>
      <td>2900</td>
      <td>23 Jones Street</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1.0</td>
      <td>1</td>
      <td>81062936e12ee5fa6cd2b965698e17d5</td>
      <td>2016-06-16 07:24:27</td>
      <td>Beautiful TRUE 1 bedroom in a luxury building ...</td>
      <td>Exchange Place</td>
      <td>[Roof Deck, Doorman, Elevator, Fitness Center,...</td>
      <td>40.7054</td>
      <td>7171695</td>
      <td>-74.0095</td>
      <td>a742cf7dd3b2627d83417bc3a1b3ec96</td>
      <td>[https://photos.renthop.com/2/7171695_089ffee2...</td>
      <td>3254</td>
      <td>20 Exchange Place</td>
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
    </tr>
    <tr>
      <th>124003</th>
      <td>1.0</td>
      <td>1</td>
      <td>bd863d28a6b119ac3bc72d5f27b07f24</td>
      <td>2016-04-26 16:09:55</td>
      <td>BRAND NEW TO MARKET 1BDR \r107TH AND LEXINGTON...</td>
      <td>150 EAST 107TH STREET</td>
      <td>[]</td>
      <td>40.7925</td>
      <td>6928108</td>
      <td>-73.9454</td>
      <td>453d46f8113e1f2c730c2ee5a4469c71</td>
      <td>[https://photos.renthop.com/2/6928108_231eb983...</td>
      <td>1700</td>
      <td>158 EAST 107TH STREET</td>
    </tr>
    <tr>
      <th>124005</th>
      <td>1.0</td>
      <td>2</td>
      <td>9174b75c0cd978eb0e5aa93afbad754b</td>
      <td>2016-04-21 05:06:19</td>
      <td>Convertible 2BR apartment features a brand new...</td>
      <td>E 33rd St.</td>
      <td>[Doorman, Elevator, Laundry in Building, Dishw...</td>
      <td>40.7456</td>
      <td>6906674</td>
      <td>-73.9797</td>
      <td>2983e45f7e0ad87d677dacd13e362785</td>
      <td>[https://photos.renthop.com/2/6906674_9fe899a8...</td>
      <td>4195</td>
      <td>141 E 33rd St.</td>
    </tr>
    <tr>
      <th>124006</th>
      <td>1.0</td>
      <td>0</td>
      <td>0</td>
      <td>2016-04-20 01:31:52</td>
      <td>Let's get you in to see this $2,400/mo, recent...</td>
      <td>Lexington Avenue</td>
      <td>[Dogs Allowed, Cats Allowed]</td>
      <td>40.7416</td>
      <td>6897967</td>
      <td>-73.9829</td>
      <td>e6472c7237327dd3903b3d6f6a94515a</td>
      <td>[]</td>
      <td>2400</td>
      <td>95 Lexington Avenue</td>
    </tr>
    <tr>
      <th>124007</th>
      <td>2.0</td>
      <td>2</td>
      <td>c90c010e5505365676538e64d02aa1e0</td>
      <td>2016-04-08 02:26:45</td>
      <td>CooperCooper.com :: Web ID #171357; Access 100...</td>
      <td>Park Avenue</td>
      <td>[Doorman, Elevator, Cats Allowed, Dogs Allowed]</td>
      <td>40.7485</td>
      <td>6842183</td>
      <td>-73.9800</td>
      <td>6e5c10246156ae5bdcd9b487ca99d96a</td>
      <td>[https://photos.renthop.com/2/6842183_b1fe51f4...</td>
      <td>6895</td>
      <td>41 Park Avenue</td>
    </tr>
    <tr>
      <th>124010</th>
      <td>1.0</td>
      <td>3</td>
      <td>1a6cf9b71da65cdc0cfd5015a75317ac</td>
      <td>2016-04-18 02:51:21</td>
      <td>New renovated Bright 3Br Murray Hill. 3 QUEEN ...</td>
      <td>E 35 Street</td>
      <td>[Garden/Patio, Laundry in Unit, Dishwasher, Ha...</td>
      <td>40.7447</td>
      <td>6889319</td>
      <td>-73.9741</td>
      <td>d9039c43983f6e564b1482b273bd7b01</td>
      <td>[https://photos.renthop.com/2/6889319_79f186e7...</td>
      <td>4695</td>
      <td>326 E 35 Street</td>
    </tr>
  </tbody>
</table>
<p>74659 rows × 14 columns</p>
</div>



```python
alldata=pd.concat([train,test])
alldata
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>bathrooms</th>
      <th>bedrooms</th>
      <th>building_id</th>
      <th>created</th>
      <th>description</th>
      <th>display_address</th>
      <th>features</th>
      <th>latitude</th>
      <th>listing_id</th>
      <th>longitude</th>
      <th>manager_id</th>
      <th>photos</th>
      <th>price</th>
      <th>street_address</th>
      <th>interest_level</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>1.0</td>
      <td>1</td>
      <td>8579a0b0d54db803821a35a4a615e97a</td>
      <td>2016-06-16 05:55:27</td>
      <td>Spacious 1 Bedroom 1 Bathroom in Williamsburg!...</td>
      <td>145 Borinquen Place</td>
      <td>[Dining Room, Pre-War, Laundry in Building, Di...</td>
      <td>40.7108</td>
      <td>7170325</td>
      <td>-73.9539</td>
      <td>a10db4590843d78c784171a107bdacb4</td>
      <td>[https://photos.renthop.com/2/7170325_3bb5ac84...</td>
      <td>2400</td>
      <td>145 Borinquen Place</td>
      <td>medium</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1.0</td>
      <td>2</td>
      <td>b8e75fc949a6cd8225b455648a951712</td>
      <td>2016-06-01 05:44:33</td>
      <td>BRAND NEW GUT RENOVATED TRUE 2 BEDROOMFind you...</td>
      <td>East 44th</td>
      <td>[Doorman, Elevator, Laundry in Building, Dishw...</td>
      <td>40.7513</td>
      <td>7092344</td>
      <td>-73.9722</td>
      <td>955db33477af4f40004820b4aed804a0</td>
      <td>[https://photos.renthop.com/2/7092344_7663c19a...</td>
      <td>3800</td>
      <td>230 East 44th</td>
      <td>low</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1.0</td>
      <td>2</td>
      <td>cd759a988b8f23924b5a2058d5ab2b49</td>
      <td>2016-06-14 15:19:59</td>
      <td>**FLEX 2 BEDROOM WITH FULL PRESSURIZED WALL**L...</td>
      <td>East 56th Street</td>
      <td>[Doorman, Elevator, Laundry in Building, Laund...</td>
      <td>40.7575</td>
      <td>7158677</td>
      <td>-73.9625</td>
      <td>c8b10a317b766204f08e613cef4ce7a0</td>
      <td>[https://photos.renthop.com/2/7158677_c897a134...</td>
      <td>3495</td>
      <td>405 East 56th Street</td>
      <td>medium</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1.5</td>
      <td>3</td>
      <td>53a5b119ba8f7b61d4e010512e0dfc85</td>
      <td>2016-06-24 07:54:24</td>
      <td>A Brand New 3 Bedroom 1.5 bath ApartmentEnjoy ...</td>
      <td>Metropolitan Avenue</td>
      <td>[]</td>
      <td>40.7145</td>
      <td>7211212</td>
      <td>-73.9425</td>
      <td>5ba989232d0489da1b5f2c45f6688adc</td>
      <td>[https://photos.renthop.com/2/7211212_1ed4542e...</td>
      <td>3000</td>
      <td>792 Metropolitan Avenue</td>
      <td>medium</td>
    </tr>
    <tr>
      <th>15</th>
      <td>1.0</td>
      <td>0</td>
      <td>bfb9405149bfff42a92980b594c28234</td>
      <td>2016-06-28 03:50:23</td>
      <td>Over-sized Studio w abundant closets. Availabl...</td>
      <td>East 34th Street</td>
      <td>[Doorman, Elevator, Fitness Center, Laundry in...</td>
      <td>40.7439</td>
      <td>7225292</td>
      <td>-73.9743</td>
      <td>2c3b41f588fbb5234d8a1e885a436cfa</td>
      <td>[https://photos.renthop.com/2/7225292_901f1984...</td>
      <td>2795</td>
      <td>340 East 34th Street</td>
      <td>low</td>
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
    </tr>
    <tr>
      <th>124003</th>
      <td>1.0</td>
      <td>1</td>
      <td>bd863d28a6b119ac3bc72d5f27b07f24</td>
      <td>2016-04-26 16:09:55</td>
      <td>BRAND NEW TO MARKET 1BDR \r107TH AND LEXINGTON...</td>
      <td>150 EAST 107TH STREET</td>
      <td>[]</td>
      <td>40.7925</td>
      <td>6928108</td>
      <td>-73.9454</td>
      <td>453d46f8113e1f2c730c2ee5a4469c71</td>
      <td>[https://photos.renthop.com/2/6928108_231eb983...</td>
      <td>1700</td>
      <td>158 EAST 107TH STREET</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>124005</th>
      <td>1.0</td>
      <td>2</td>
      <td>9174b75c0cd978eb0e5aa93afbad754b</td>
      <td>2016-04-21 05:06:19</td>
      <td>Convertible 2BR apartment features a brand new...</td>
      <td>E 33rd St.</td>
      <td>[Doorman, Elevator, Laundry in Building, Dishw...</td>
      <td>40.7456</td>
      <td>6906674</td>
      <td>-73.9797</td>
      <td>2983e45f7e0ad87d677dacd13e362785</td>
      <td>[https://photos.renthop.com/2/6906674_9fe899a8...</td>
      <td>4195</td>
      <td>141 E 33rd St.</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>124006</th>
      <td>1.0</td>
      <td>0</td>
      <td>0</td>
      <td>2016-04-20 01:31:52</td>
      <td>Let's get you in to see this $2,400/mo, recent...</td>
      <td>Lexington Avenue</td>
      <td>[Dogs Allowed, Cats Allowed]</td>
      <td>40.7416</td>
      <td>6897967</td>
      <td>-73.9829</td>
      <td>e6472c7237327dd3903b3d6f6a94515a</td>
      <td>[]</td>
      <td>2400</td>
      <td>95 Lexington Avenue</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>124007</th>
      <td>2.0</td>
      <td>2</td>
      <td>c90c010e5505365676538e64d02aa1e0</td>
      <td>2016-04-08 02:26:45</td>
      <td>CooperCooper.com :: Web ID #171357; Access 100...</td>
      <td>Park Avenue</td>
      <td>[Doorman, Elevator, Cats Allowed, Dogs Allowed]</td>
      <td>40.7485</td>
      <td>6842183</td>
      <td>-73.9800</td>
      <td>6e5c10246156ae5bdcd9b487ca99d96a</td>
      <td>[https://photos.renthop.com/2/6842183_b1fe51f4...</td>
      <td>6895</td>
      <td>41 Park Avenue</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>124010</th>
      <td>1.0</td>
      <td>3</td>
      <td>1a6cf9b71da65cdc0cfd5015a75317ac</td>
      <td>2016-04-18 02:51:21</td>
      <td>New renovated Bright 3Br Murray Hill. 3 QUEEN ...</td>
      <td>E 35 Street</td>
      <td>[Garden/Patio, Laundry in Unit, Dishwasher, Ha...</td>
      <td>40.7447</td>
      <td>6889319</td>
      <td>-73.9741</td>
      <td>d9039c43983f6e564b1482b273bd7b01</td>
      <td>[https://photos.renthop.com/2/6889319_79f186e7...</td>
      <td>4695</td>
      <td>326 E 35 Street</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>124011 rows × 15 columns</p>
</div>



```python
alldata['photos'][0]
```


['https://photos.renthop.com/2/7142618_1c45a2c8f45e649b9ee77681cc7ca438.jpg',
 'https://photos.renthop.com/2/7142618_2a0268ff01f834c1039027a04e54edf4.jpg',
 'https://photos.renthop.com/2/7142618_1645edaeb3892d35c190356eeb16bd75.jpg',
 'https://photos.renthop.com/2/7142618_ca5c03339bd1f021b94da72af7356bca.jpg',
 'https://photos.renthop.com/2/7142618_b129d432a96a0ad419f1af430f4a20ff.jpg',
 'https://photos.renthop.com/2/7142618_dd3c3651b991455d3ed7403766c6941d.jpg',
 'https://photos.renthop.com/2/7142618_4ddef2aee0c343f5a86da7113f9336fc.jpg',
 'https://photos.renthop.com/2/7142618_6c51aec64570affecc573efbdc4453ca.jpg']


```python
alldata['features'][0]
```


['Elevator',
 'Laundry in Building',
 'Laundry in Unit',
 'Dishwasher',
 'Hardwood Floors',
 'Outdoor Space']


```python
alldata['description'][2]
```


'Spacious studio in Prime Location. Cleanbuilding with hands on management and super. Located very close to all major subway lines. Hardwood floors throughout, updated kitchen with Granite counter tops, and marble bathroom. Please contact Yana for private appointment. '


```python
[x+1 for x in [1,4,6]]
```


[2, 5, 7]


```python
x=['kaggle', 'apple', 'kiwi']
" ".join(x)
```


'kaggle apple kiwi'

---------------
정형 데이터와 텍스트가 혼재되어 있어, 각 column으로 부터 유의미한 데이터를 전처리 해줍니다.
photo의 갯수가 선호도에 영향을 줄 것으로 생각하였고, description과 feature의 갯수도 선호도에 영향을 줄 것으로 생각하였습니다.
특히 description과 feature는 내포된 특정한 단어로 인한 선호도 증감 유무를 확인 해보려 합니다.
photo는 사진을 볼 수 있는 site가 list 형식으로 구성되어 있습니다.
description은 text로 구성되어 있는데 띄어쓰기 기준으로 counting하려 합니다.
features 또한 list 형식으로 구성되어 있어 apply(len)을 이용하여 쉽게 counting할 수 있습니다. 

-------------


```python
alldata['num_photos']=alldata['photos'].apply(len)
alldata['num_features']=alldata['features'].apply(len)
alldata['num_description']=alldata['description'].apply(lambda x: len(x.split()))
```


```python
import matplotlib.pyplot as plt
import seaborn as sns
plt.figure(figsize=(16,8))
sns.countplot(alldata["num_photos"],hue=alldata["interest_level"])
plt.xlim(-1,15)
```


/opt/conda/lib/python3.7/site-packages/seaborn/_decorators.py:43: FutureWarning: Pass the following variable as a keyword arg: x. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
  FutureWarning


(-1.0, 15.0)

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA78AAAHhCAYAAACm+wk0AAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjUuMSwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/YYfK9AAAACXBIWXMAAAsTAAALEwEAmpwYAAAsVElEQVR4nO3de7hdVX03+u/PBMELFQWkSKRBpFyDQNIIchFEhFKOqFWBY1sQT/H04KW0UrFapFj72MqrqLWeeqFIWxVEqXmtF0CxKF6AAHIJWClGCEVBEAoqCjjeP/aERkhgJ6y9V/bI5/M869lzjjXmXL+xN2Tt7x5zjlWttQAAAEDPHjPuAgAAAGCqCb8AAAB0T/gFAACge8IvAAAA3RN+AQAA6J7wCwAAQPdmj7uAqbDRRhu1uXPnjrsMAAAApsDixYt/1FrbeFWO6TL8zp07NxdffPG4ywAAAGAKVNX3V/UYlz0DAADQPeEXAACA7gm/AAAAdK/Le34BAADWRPfcc0+WLVuWu+++e9ylzAjrrbde5syZk3XWWedRn0v4BQAAmCbLli3L+uuvn7lz56aqxl3OGq21lltvvTXLli3LFlts8ajP57JnAACAaXL33Xdnww03FHwnoaqy4YYbjmyWXPgFAACYRoLv5I3yeyX8AgAA0D3hFwAAYMye85znPGKfk08+OT/96U+ntI5//dd/zZIlSx62zxFHHJEzzzxzpK87Fed8MOEXAABgzL7+9a8/Yp/VCb/33XffKvWfTPidqYRfAACAMXviE5+YJPnKV76SvffeOy996UuzzTbb5BWveEVaa3nve9+b//qv/8o+++yTffbZJ0ly9tlnZ7fddssuu+ySl73sZbnrrruSJHPnzs0b3/jG7LLLLvnkJz+50n7HHXdctttuu+y44455wxvekK9//etZtGhRjj322Oy00075z//8z0ese/HixXnuc5+b+fPnZ//9989NN92Ua665JgsXLnygz9KlSzNv3ryV9p8uwi8AAMAa5NJLL83JJ5+cJUuW5LrrrssFF1yQ173udXna056W8847L+edd15+9KMf5a/+6q9y7rnn5pJLLsmCBQvyrne964FzbLjhhrnkkkvy/Oc/f4X9br311px11lm56qqrcvnll+ctb3lLnvOc5+SFL3xh3vnOd+ayyy7Llltu+bB13nPPPXnta1+bM888M4sXL86RRx6ZN7/5zdlmm23yi1/8It/73veSJKeffnoOOeSQlfafLj7nFwAAYA2ycOHCzJkzJ0my0047ZenSpdljjz1+pc83v/nNLFmyJLvvvnuS5Be/+EV22223B54/5JBDHrbfk570pKy33np51atelYMOOigHHXTQKtf5ne98J1deeWX222+/JBOXWG+66aZJkpe//OU5/fTTc9xxx+X000/P6aef/rD9p4PwCwAAsAZZd911H9ieNWtW7r333of0aa1lv/32y8c//vEVnuMJT3jCI/a78MIL86UvfSlnnnlm/u7v/i5f/vKXV6nO1lq23377fOMb33jIc4ccckhe9rKX5SUveUmqKltttVWuuOKKlfafDi57BgAAmAHWX3/93HnnnUmSXXfdNRdccEGuvfbaJMlPfvKT/Md//MdDjllZv7vuuit33HFHDjzwwLz73e/Ot7/97Ye8xiPZeuutc8sttzwQZu+5555cddVVSZItt9wys2bNytve9rYHZqEfrv90EH4BAABmgKOOOioHHHBA9tlnn2y88cY59dRTc9hhh2XHHXfMbrvtlmuuueYhx6ys35133pmDDjooO+64Y/bYY48H7hc+9NBD8853vjM777zzIy549djHPjZnnnlm3vjGN+ZZz3pWdtppp19ZtfqQQw7JP//zP+flL3/5pPpPtWqtTduLTZcFCxa0iy++eNxlAAAA/Iqrr74622677bjLmFFW9D2rqsWttQWrch4zvwAAAHTPglcAAAA8xNFHH50LLrjgV9pe//rX55WvfOWYKnp0hF+Atcj1J85b7WM3P/6KEVYCAKzp3v/+94+7hJFy2TMAAADdE34BAADonvALAABA94RfAAAAVsvee++d+z9m9sADD8ztt98+3oIehgWvAAAAxmT+saeN9HyL3/kHIz3fqvjc5z43tteeDDO/AAAAa5GlS5dmm222yRFHHJHf/M3fzCte8Yqce+652X333bPVVlvlwgsvzE9+8pMceeSRWbhwYXbeeed85jOfSZL87Gc/y6GHHpptt902L37xi/Ozn/3sgfPOnTs3P/rRj7J06dLssMMOD7SfdNJJOeGEE5JMzBQfc8wxWbBgQbbddttcdNFFeclLXpKtttoqb3nLW6Z03GZ+AQAA1jLXXnttPvnJT+aUU07Jb/3Wb+VjH/tYvva1r2XRokX567/+62y33XZ53vOel1NOOSW33357Fi5cmOc///n5h3/4hzz+8Y/P1Vdfncsvvzy77LLLKr/2Yx/72Fx88cV5z3vek4MPPjiLFy/OU57ylGy55ZY55phjsuGGG07BiIVfAACAtc4WW2yRefPmJUm233777LvvvqmqzJs3L0uXLs2yZcuyaNGinHTSSUmSu+++O9dff33OP//8vO51r0uS7Ljjjtlxxx1X+bVf+MIXJknmzZuX7bffPptuummS5BnPeEZuuOEG4RcAAIDRWHfddR/YfsxjHvPA/mMe85jce++9mTVrVj71qU9l6623XuVzz549O7/85S8f2L/77rtX+NrLv+7yrz1V3PMLAADAr9h///3zvve9L621JMmll16aJNlrr73ysY99LEly5ZVX5vLLL3/IsZtsskluvvnm3Hrrrfn5z3+ez372s9NX+MMQfgEAAPgVf/EXf5F77rknO+64Y7bffvv8xV/8RZLkj/7oj3LXXXdl2223zfHHH5/58+c/5Nh11lknxx9/fBYuXJj99tsv22yzzXSXv0J1f5LvyYIFC9r9nzUFwP+4/sR5q33s5sdfMcJKAGDtdPXVV2fbbbcddxkzyoq+Z1W1uLW2YFXOY+YXAACA7gm/AAAAdE/4BQAAoHvCLwAAAN0TfgEAAOie8AsAAED3hF8AAIC1yBOf+MRxlzAWs8ddAAAAwNrq+hPnjfR8mx9/xUjP1xMzvwAAAGuh1lqOPfbY7LDDDpk3b15OP/30JMnRRx+dRYsWJUle/OIX58gjj0ySnHLKKXnzm988tnofLeEXAABgLfTpT386l112Wb797W/n3HPPzbHHHpubbrope+65Z7761a8mSW688cYsWbIkSfLVr341e+211zhLflSEXwAAgLXQ1772tRx22GGZNWtWNtlkkzz3uc/NRRdd9ED4XbJkSbbbbrtssskmuemmm/KNb3wjz3nOc8Zd9mpzzy8AAAAP2GyzzXL77bfnC1/4Qvbaa6/cdtttOeOMM/LEJz4x66+//rjLW21mfgEAANZCe+65Z04//fTcd999ueWWW3L++edn4cKFSZJdd901J598cvbaa6/sueeeOemkk7LnnnuOueJHx8wvAADAWujFL35xvvGNb+RZz3pWqip/+7d/m1//9V9PMhGMzz777Dzzmc/Mb/zGb+S2226b8eG3WmvjrmHkFixY0C6++OJxlwHMQI/m4wZmwkcL9D4+AFjTXX311dl2223HXcaMsqLvWVUtbq0tWJXzuOwZAACA7gm/AAAAdE/4BQAAoHvCLwAAAN0TfgEAAOie8AsAAED3hF8AAIC1yNKlS7PDDjs8pP3444/Pueee+7DHnnDCCTnppJOmqrQpNXvcBQAAAKytdn/f7iM93wWvvWC1jz3xxBNHWMmax8wvAADAWua+++7LH/7hH2b77bfPC17wgvzsZz/LEUcckTPPPDNJ8rnPfS7bbLNN5s+fn9e97nU56KCDHjh2yZIl2XvvvfOMZzwj733ve8c1hFUm/AIAAKxlvvvd7+boo4/OVVddlQ022CCf+tSnHnju7rvvzqtf/ep8/vOfz+LFi3PLLbf8yrHXXHNNvvjFL+bCCy/MX/7lX+aee+6Z7vJXi/ALAACwltliiy2y0047JUnmz5+fpUuXPvDcNddck2c84xnZYostkiSHHXbYrxz7O7/zO1l33XWz0UYb5alPfWp++MMfTlfZj4rwCwAAsJZZd911H9ieNWtW7r333mk5dpymNPxW1dKquqKqLquqi4e2p1TVOVX13eHrk4f2qqr3VtW1VXV5Ve2y3HkOH/p/t6oOn8qaAQAA1mZbb711rrvuugdmg08//fTxFjQi0zHzu09rbafW2oJh/7gkX2qtbZXkS8N+kvx2kq2Gx1FJPpBMhOUkb03y7CQLk7z1/sAMAADAaD3ucY/L3//93+eAAw7I/Pnzs/766+dJT3rSuMt61MbxUUcHJ9l72P5okq8keePQflprrSX5ZlVtUFWbDn3Paa3dliRVdU6SA5J8fHrLBgAAGK1H89FEq2vu3Lm58sorH9h/wxve8JA+++yzT6655pq01nL00UdnwYKJucwTTjjhV/otf5413VTP/LYkZ1fV4qo6amjbpLV207D9gySbDNubJblhuWOXDW0rawcAAGAKfOhDH8pOO+2U7bffPnfccUde/epXj7ukR22qZ373aK3dWFVPTXJOVV2z/JOttVZVbRQvNITro5Jk8803H8UpAQAA1krHHHNMjjnmmHGXMVJTOvPbWrtx+HpzkrMycc/uD4fLmTN8vXnofmOSpy93+JyhbWXtD36tD7bWFrTWFmy88cajHgoAAAAz2JSF36p6QlWtf/92khckuTLJoiT3r9h8eJLPDNuLkvzBsOrzrknuGC6P/mKSF1TVk4eFrl4wtAEAAMw4E8scMRmj/F5N5WXPmyQ5q6ruf52Ptda+UFUXJTmjql6V5PtJXj70/1ySA5Ncm+SnSV6ZJK2126rqbUkuGvqdeP/iVwAAADPJeuutl1tvvTUbbrhhhqzESrTWcuutt2a99dYbyfmmLPy21q5L8qwVtN+aZN8VtLckR6/kXKckOWXUNQIAAEynOXPmZNmyZbnlllvGXcqMsN5662XOnDkjOdc4PuoIAABgrbTOOutkiy22GHcZa6Wp/qgjAAAAGDvhFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA92aPuwAAGIXrT5y32sdufvwVI6wEAFgTmfkFAACge8IvAAAA3RN+AQAA6J7wCwAAQPeEXwAAALon/AIAANA94RcAAIDuCb8AAAB0T/gFAACge8IvAAAA3RN+AQAA6J7wCwAAQPeEXwAAALon/AIAANA94RcAAIDuCb8AAAB0T/gFAACge8IvAAAA3RN+AQAA6J7wCwAAQPeEXwAAALon/AIAANA94RcAAIDuCb8AAAB0b8rDb1XNqqpLq+qzw/4WVfWtqrq2qk6vqscO7esO+9cOz89d7hxvGtq/U1X7T3XNAAAA9GU6Zn5fn+Tq5fb/Jsm7W2vPTPLjJK8a2l+V5MdD+7uHfqmq7ZIcmmT7JAck+fuqmjUNdQMAANCJKQ2/VTUnye8k+fCwX0mel+TMoctHk7xo2D542M/w/L5D/4OTfKK19vPW2veSXJtk4VTWDQAAQF+meub35CR/luSXw/6GSW5vrd077C9LstmwvVmSG5JkeP6Oof8D7Ss4BgAAAB7RlIXfqjooyc2ttcVT9RoPer2jquriqrr4lltumY6XBAAAYIaYypnf3ZO8sKqWJvlEJi53fk+SDapq9tBnTpIbh+0bkzw9SYbnn5Tk1uXbV3DMA1prH2ytLWitLdh4441HPxoAAABmrCkLv621N7XW5rTW5mZiwaovt9ZekeS8JC8duh2e5DPD9qJhP8PzX26ttaH90GE16C2SbJXkwqmqGwAAgP7MfuQuI/fGJJ+oqr9KcmmSjwztH0nyT1V1bZLbMhGY01q7qqrOSLIkyb1Jjm6t3Tf9ZQMAADBTTUv4ba19JclXhu3rsoLVmltrdyd52UqOf3uSt09dhQAAAPRsOj7nFwAAAMZK+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADo3uxxF8CKXX/ivNU+dvPjrxhhJQAAADOfmV8AAAC6J/wCAADQPeEXAACA7gm/AAAAdE/4BQAAoHvCLwAAAN0TfgEAAOie8AsAAED3hF8AAAC6J/wCAADQPeEXAACA7gm/AAAAdG/2uAsAAB7Z9SfOW+1jNz/+ihFWAgAzk5lfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRv9mQ6VdWXWmv7PlIb0L/rT5y32sdufvwVI6wEAAAm72HDb1Wtl+TxSTaqqicnqeGpX0uy2RTXBgAAACPxSDO/r07yx0melmRx/if8/neSv5u6sgAAAGB0Hvae39bae1prWyR5Q2vtGa21LYbHs1prDxt+q2q9qrqwqr5dVVdV1V8O7VtU1beq6tqqOr2qHju0rzvsXzs8P3e5c71paP9OVe3/6IcNAADA2mRS9/y21t5XVc9JMnf5Y1prpz3MYT9P8rzW2l1VtU6Sr1XV55P8SZJ3t9Y+UVX/f5JXJfnA8PXHrbVnVtWhSf4mySFVtV2SQ5Nsn4kZ6HOr6jdba/et6mABAABYO01qteeq+qckJyXZI8lvDY8FD3dMm3DXsLvO8GhJnpfkzKH9o0leNGwfPOxneH7fqqqh/ROttZ+31r6X5NokCydTNwAAACSTnPnNRNDdrrXWVuXkVTUrE/cKPzPJ+5P8Z5LbW2v3Dl2W5X8WztosyQ1J0lq7t6ruSLLh0P7N5U67/DEAAADwiCb7Ob9XJvn1VT15a+2+1tpOSeZkYrZ2m1U9x2RV1VFVdXFVXXzLLbdM1csAAAAwA0125nejJEuq6sJM3MubJGmtvXAyB7fWbq+q85LslmSDqpo9zP7OSXLj0O3GJE9PsqyqZid5UpJbl2u/3/LHLP8aH0zywSRZsGDBKs1QAwAA0LfJht8TVvXEVbVxknuG4Pu4JPtlYhGr85K8NMknkhye5DPDIYuG/W8Mz3+5tdaqalGSj1XVuzKx4NVWSS5c1XoAAABYe012ted/X41zb5rko8N9v49JckZr7bNVtSTJJ6rqr5JcmuQjQ/+PJPmnqro2yW2ZWOE5rbWrquqMJEuS3JvkaCs9AwAAsComFX6r6s5MrNScJI/NxMrNP2mt/drKjmmtXZ5k5xW0X5cVrNbcWrs7yctWcq63J3n7ZGoFAACAB5vszO/6928v9/FDu05VUQAAADBKk13t+QHD5/f+a5L9R18OAAAAjN5kL3t+yXK7j8nE5/7ePSUVAQAAwIhNdrXn/2u57XuTLM3Epc8AAACwxpvsPb+vnOpCAAAAYKpM6p7fqppTVWdV1c3D41NVNWeqiwMAAIBRmOyCV/+YZFGSpw2P/z20AQAAwBpvsuF349baP7bW7h0epybZeArrAgAAgJGZbPi9tap+r6pmDY/fS3LrVBYGAAAAozLZ8Htkkpcn+UGSm5K8NMkRU1QTAAAAjNRkP+roxCSHt9Z+nCRV9ZQkJ2UiFAMAAMAabbIzvzveH3yTpLV2W5Kdp6YkAAAAGK3Jht/HVNWT798ZZn4nO2sMAAAAYzXZAPu/knyjqj457L8sydunpiQAAAAYrUmF39baaVV1cZLnDU0vaa0tmbqyAAAAYHQmfenyEHYFXgAAAGacyd7zCwAAADOW8AsAAED3hF8AAAC6J/wCAADQPZ/VCwCM3fUnzlvtYzc//ooRVgJAr8z8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRv9rgLAGDVzD/2tNU+9qz1R1gIAMAMYuYXAACA7gm/AAAAdE/4BQAAoHvCLwAAAN0TfgEAAOie8AsAAED3hF8AAAC6J/wCAADQPeEXAACA7gm/AAAAdE/4BQAAoHvCLwAAAN0TfgEAAOie8AsAAED3hF8AAAC6J/wCAADQvSkLv1X19Ko6r6qWVNVVVfX6of0pVXVOVX13+Prkob2q6r1VdW1VXV5Vuyx3rsOH/t+tqsOnqmYAAAD6NHsKz31vkj9trV1SVesnWVxV5yQ5IsmXWmvvqKrjkhyX5I1JfjvJVsPj2Uk+kOTZVfWUJG9NsiBJG86zqLX24ymsHZjB5h972mofe9b6IywEAIA1xpTN/LbWbmqtXTJs35nk6iSbJTk4yUeHbh9N8qJh++Akp7UJ30yyQVVtmmT/JOe01m4bAu85SQ6YqroBAADoz7Tc81tVc5PsnORbSTZprd00PPWDJJsM25sluWG5w5YNbStrBwAAgEmZ8vBbVU9M8qkkf9xa++/ln2uttUxcyjyK1zmqqi6uqotvueWWUZwSAACATkxp+K2qdTIRfP+ltfbpofmHw+XMGb7ePLTfmOTpyx0+Z2hbWfuvaK19sLW2oLW2YOONNx7tQAAAAJjRpnK150rykSRXt9betdxTi5Lcv2Lz4Uk+s1z7HwyrPu+a5I7h8ugvJnlBVT15WBn6BUMbAAAATMpUrva8e5LfT3JFVV02tP15knckOaOqXpXk+0lePjz3uSQHJrk2yU+TvDJJWmu3VdXbklw09DuxtXbbFNYNAABAZ6Ys/LbWvpakVvL0vivo35IcvZJznZLklNFVBwAAwNpkWlZ7BgAAgHESfgEAAOie8AsAAED3hF8AAAC6J/wCAADQPeEXAACA7gm/AAAAdE/4BQAAoHvCLwAAAN0TfgEAAOie8AsAAED3hF8AAAC6N3vcBQDA8uYfe9pqHXfW+iMuBADoiplfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdE34BAADonvALAABA94RfAAAAuif8AgAA0L3Z4y4AANYW8489bbWPPWv9ERYCAGshM78AAAB0T/gFAACgey57BgCYYtefOG+1j938+CtGWAnA2svMLwAAAN0TfgEAAOie8AsAAED3hF8AAAC6J/wCAADQPeEXAACA7gm/AAAAdE/4BQAAoHvCLwAAAN0TfgEAAOie8AsAAED3hF8AAAC6J/wCAADQvdnjLgCYfvOPPW21jz1r/REWAgAA02TKZn6r6pSqurmqrlyu7SlVdU5VfXf4+uShvarqvVV1bVVdXlW7LHfM4UP/71bV4VNVLwAAAP2aysueT01ywIPajkvypdbaVkm+NOwnyW8n2Wp4HJXkA8lEWE7y1iTPTrIwyVvvD8wAAAAwWVMWfltr5ye57UHNByf56LD90SQvWq79tDbhm0k2qKpNk+yf5JzW2m2ttR8nOScPDdQAAADwsKb7nt9NWms3Dds/SLLJsL1ZkhuW67dsaFtZO6yxrj9x3mofu/nxV4ywEgAA4H5jW/Cqtdaqqo3qfFV1VCYumc7mm28+qtMCAJNkMT0A1mTT/VFHPxwuZ87w9eah/cYkT1+u35yhbWXtD9Fa+2BrbUFrbcHGG2888sIBAACYuaZ75ndRksOTvGP4+pnl2l9TVZ/IxOJWd7TWbqqqLyb56+UWuXpBkjdNc80AADwMt/wAM8GUhd+q+niSvZNsVFXLMrFq8zuSnFFVr0ry/SQvH7p/LsmBSa5N8tMkr0yS1tptVfW2JBcN/U5srT14ES0AAAB4WFMWfltrh63kqX1X0LclOXol5zklySkjLI0x89dhAABguk33Pb8AAAAw7YRfAAAAuif8AgAA0D3hFwAAgO4JvwAAAHRP+AUAAKB7wi8AAADdm7LP+QWgL7u/b/fVOu6C114w4koAAFadmV8AAAC6J/wCAADQPeEXAACA7gm/AAAAdE/4BQAAoHvCLwAAAN0TfgEAAOie8AsAAED3hF8AAAC6J/wCAADQPeEXAACA7gm/AAAAdE/4BQAAoHvCLwAAAN0TfgEAAOie8AsAAED3Zo+7AIBe7P6+3Vf72Atee8EIKwEA4MHM/AIAANA9M78ArPXM2gNA/4RfAABYS11/4rzVPnbz468YYSUw9YRfAABYCeEQ+uGeXwAAALon/AIAANA94RcAAIDuCb8AAAB0T/gFAACge8IvAAAA3RN+AQAA6J7wCwAAQPeEXwAAALon/AIAANA94RcAAIDuzR53AcDaY/f37b7ax17w2gtGWAmsXfy/BwDCLwDApMw/9rTVPvas9UdYCACrxWXPAAAAdE/4BQAAoHvCLwAAAN0TfgEAAOieBa8AgBnNatajYUEvoHdmfgEAAOie8AsAAED3hF8AAAC6J/wCAADQPQteAQAAXbr+xHmrfezmx18xwkpYE5j5BQAAoHtmfmEFfNwDAAD0xcwvAAAA3TPzCwAAM5gr1mByhF8AALq3ugFROGRNZkGvVSP8stq8iQAAADOF8AsAsAbb/X27r/axF7z2ghFWAjC9Hs3M9opY8AoAAIDumfmdQhYfAAAAWDMIv7AGcWkbAGub1X3v874HrCqXPQMAANA9M7/MKGZGAQDWLm4lZFSEXwAAYJWZlGCmmTHht6oOSPKeJLOSfLi19o4xl7TGcu8MAMD4CYczm59ff2ZE+K2qWUnen2S/JMuSXFRVi1prS8ZbGQAAwOrr/bLuNWl8M2XBq4VJrm2tXdda+0WSTyQ5eMw1AQAAMEPMiJnfJJsluWG5/WVJnj2mWgAAAGa0tfGy7mqtjbuGR1RVL01yQGvt/xn2fz/Js1trr1muz1FJjhp2t07ynWkvdPpslORH4y5iChnfzNbz+HoeW2J8M53xzVw9jy0xvpnO+GaunseWJFu31lbpwuiZMvN7Y5KnL7c/Z2h7QGvtg0k+OJ1FjUtVXdxaWzDuOqaK8c1sPY+v57ElxjfTGd/M1fPYEuOb6Yxv5up5bMnE+Fb1mJlyz+9FSbaqqi2q6rFJDk2yaMw1AQAAMEPMiJnf1tq9VfWaJF/MxEcdndJau2rMZQEAADBDzIjwmySttc8l+dy461hD9H55t/HNbD2Pr+exJcY30xnfzNXz2BLjm+mMb+bqeWzJaoxvRix4BQAAAI/GTLnnFwAAAFab8DvDVNUBVfWdqrq2qo4bdz2jVFWnVNXNVXXluGsZtap6elWdV1VLquqqqnr9uGsapapar6ourKpvD+P7y3HXNBWqalZVXVpVnx13LaNWVUur6oqqumx1Vk9ck1XVBlV1ZlVdU1VXV9Vu465pVKpq6+Fndv/jv6vqj8dd1yhV1THDvytXVtXHq2q9cdc0SlX1+mFsV/Xws1vRe3lVPaWqzqmq7w5fnzzOGh+NlYzvZcPP75dVNWNX1l3J2N45/Nt5eVWdVVUbjLHER2Ul43vbMLbLqursqnraOGt8NB7u9+iq+tOqalW10ThqG4WV/PxOqKobl3sPPPCRziP8ziBVNSvJ+5P8dpLtkhxWVduNt6qROjXJAeMuYorcm+RPW2vbJdk1ydGd/ex+nuR5rbVnJdkpyQFVtet4S5oSr09y9biLmEL7tNZ26vBjEd6T5AuttW2SPCsd/Qxba98ZfmY7JZmf5KdJzhpvVaNTVZsleV2SBa21HTKx6OWh461qdKpqhyR/mGRhJv7bPKiqnjneqh61U/PQ9/LjknyptbZVki8N+zPVqXno+K5M8pIk5097NaN1ah46tnOS7NBa2zHJfyR503QXNUKn5qHje2drbcfh39DPJjl+uosaoVOzgt+jq+rpSV6Q5PrpLmjETs2Kc8K7738fHNaIeljC78yyMMm1rbXrWmu/SPKJJAePuaaRaa2dn+S2cdcxFVprN7XWLhm278zEL9+bjbeq0WkT7hp21xkeXS0oUFVzkvxOkg+PuxYmr6qelGSvJB9JktbaL1prt4+1qKmzb5L/bK19f9yFjNjsJI+rqtlJHp/kv8Zczyhtm+RbrbWfttbuTfLvmQhRM9ZK3ssPTvLRYfujSV40nTWN0orG11q7urX2nTGVNDIrGdvZw3+bSfLNJHOmvbARWcn4/nu53SdkBv/u8jC/R787yZ9lBo8tGV1OEH5nls2S3LDc/rJ0FKDWFlU1N8nOSb415lJGargk+LIkNyc5p7XW1fiSnJyJN49fjrmOqdKSnF1Vi6vqqHEXM0JbJLklyT8Ol6x/uKqeMO6ipsihST4+7iJGqbV2Y5KTMjFjcVOSO1prZ4+3qpG6MsmeVbVhVT0+yYFJnj7mmqbCJq21m4btHyTZZJzFsNqOTPL5cRcxalX19qq6IckrMrNnfh+iqg5OcmNr7dvjrmUKvWa4dP2UydxSIfzCNKqqJyb5VJI/ftBfG2e81tp9w2VDc5IsHC7n60JVHZTk5tba4nHXMoX2aK3tkonbKo6uqr3GXdCIzE6yS5IPtNZ2TvKTzOxLLleoqh6b5IVJPjnuWkZp+EXm4Ez8EeNpSZ5QVb833qpGp7V2dZK/SXJ2ki8kuSzJfeOsaaq1iY8ZmdEzUGujqnpzJm7h+pdx1zJqrbU3t9aenomxvWbc9YzK8Ae1P09ngf5BPpBky0zccndTkv/1SAcIvzPLjfnVvwjPGdqYAapqnUwE339prX163PVMleGS0vPS1/3buyd5YVUtzcTtBs+rqn8eb0mjNcywpbV2cybuGV043opGZlmSZctdiXBmJsJwb347ySWttR+Ou5ARe36S77XWbmmt3ZPk00meM+aaRqq19pHW2vzW2l5JfpyJ+yp788Oq2jRJhq83j7keVkFVHZHkoCSvaH1/Ruq/JPndcRcxQltm4g+H3x5+f5mT5JKq+vWxVjVCrbUfDpMvv0zyoUzidxfhd2a5KMlWVbXF8Ff+Q5MsGnNNTEJVVSbuOby6tfaucdczalW18f0rQFbV45Lsl+SasRY1Qq21N7XW5rTW5mbi/7svt9a6mX2qqidU1fr3b2diYYwuVl1vrf0gyQ1VtfXQtG+SJWMsaaocls4ueR5cn2TXqnr88O/ovulowbIkqaqnDl83z8T9vh8bb0VTYlGSw4ftw5N8Zoy1sAqq6oBM3PLzwtbaT8ddz6hV1VbL7R6cvn53uaK19tTW2tzh95dlSXYZ3he7cP8f1QYvziR+d5k9deUwaq21e6vqNUm+mIkVL09prV015rJGpqo+nmTvJBtV1bIkb22tfWS8VY3M7kl+P8kVw32xSfLnk1mVbobYNMlHhxXJH5PkjNZadx8H1LFNkpw1kS0yO8nHWmtfGG9JI/XaJP8y/NHwuiSvHHM9IzX8wWK/JK8edy2j1lr7VlWdmeSSTFxyeWmSD463qpH7VFVtmOSeJEfP9AXZVvRenuQdSc6oqlcl+X6Sl4+vwkdnJeO7Lcn7kmyc5N+q6rLW2v7jq3L1rGRsb0qybpJzhveIb7bW/t+xFfkorGR8Bw5/HP1lJv7bnJFjS7r/PXplP7+9q2qnTNxKsTSTeB+svq9eAAAAAJc9AwAAsBYQfgEAAOie8AsAAED3hF8AAAC6J/wCAADQPeEXAACA7gm/ANCZqjqhqt6wCv03qKr/byprAoBxE34BgA2SCL8AdE34BYARqqq5VXV1VX2oqq6qqrOr6nFV9ZWqWjD02aiqlg7bR1TVv1bVOVW1tKpeU1V/UlWXVtU3q+opD/NaX6mq91TVZVV1ZVUtXO7p7Ybnr6uq1y13zJ8Mfa+sqj8emt+RZMvhPO+sCe8c+lxRVYcMx25aVecv93p7jvjbBwBTZva4CwCADm2V5LDW2h9W1RlJfvcR+u+QZOck6yW5NskbW2s7V9W7k/xBkpMf5tjHt9Z2qqq9kpwynCtJtkmyT5L1k3ynqj6QZMckr0zy7CSV5FtV9e9JjkuyQ2ttpySpqt9NslOSZyXZKMlFVXV+kv87yRdba2+vqllJHj/J7wcAjJ2ZXwAYve+11i4bthcnmfsI/c9rrd3ZWrslyR1J/vfQfsUkjv14krTWzk/ya1W1wdD+b621n7fWfpTk5iSbJNkjyVmttZ+01u5K8ukkK5q93SPJx1tr97XWfpjk35P8VpKLkryyqk5IMq+1ducj1AYAawzhFwBG7+fLbd+XiSut7s3/vO+u9zD9f7nc/i/zyFdptZXsr6iGR2UI2HsluTHJqVX1B4/2nAAwXYRfAJgeS5PMH7ZfOsLz3n8/7h5J7mit3fEwfb+a5EVV9fiqekKSFw9td2bi8ujl+x1SVbOqauNMBN4Lq+o3kvywtfahJB9OsssIxwEAU8o9vwAwPU5KckZVHZXk30Z43rur6tIk6yQ58uE6ttYuqapTk1w4NH24tXZpklTVBVV1ZZLPJ/mzJLsl+XYmZpL/rLX2g6o6PMmxVXVPkrsycT8yAMwI1dqDr5YCAGaCqvpKkje01i4edy0AsKZz2TMAAADdc9kzAKzhqur9SXZ/UPN7Wmt7j6EcAJiRXPYMAABA91z2DAAAQPeEXwAAALon/AIAANA94RcAAIDuCb8AAAB07/8AniwnmgDqAyIAAAAASUVORK5CYII="/>

------------------
사진의 갯수가 많을 수록 interest_level이 낮은 경우가 급격히 감소함을 알 수 있습니다.
따라서 num_photos column은 예측에 도움을 주는 column으로 볼 수 있습니다.

------------------


```python
display(alldata['display_address'].nunique(),alldata['street_address'].nunique(),alldata['building_id'].nunique(),alldata['manager_id'].nunique())
```

16068,25766,11635,4399

-------------
display_address와 street_address는 각 명칭으로 되어 있고, building_id와 manager_id는 일련번호로 표기되어 있습니다. (모두 train,test에 존재하는 column입니다)
alldata의 총 low 갯수는 124011인데 위에 언급한 각 칼럼의 nunique를 살펴보아 중복 여부를 확인하였습니다.
display_address : 16068 개
street_address : 25766 개
building_id : 11635개
manager_id : 4399개
따라서 위의 column들은 LabelEncoder를 사용하여 처리함으로써 숫자 형식으로 통일하려 합니다.

---------------


```python
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
alldata['display_address']=le.fit_transform(alldata['display_address'])
alldata['street_address']=le.fit_transform(alldata['street_address'])
alldata['building_id']=le.fit_transform(alldata['building_id'])
alldata['manager_id']=le.fit_transform(alldata['manager_id'])
alldata
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>bathrooms</th>
      <th>bedrooms</th>
      <th>building_id</th>
      <th>created</th>
      <th>description</th>
      <th>display_address</th>
      <th>features</th>
      <th>latitude</th>
      <th>listing_id</th>
      <th>longitude</th>
      <th>manager_id</th>
      <th>photos</th>
      <th>price</th>
      <th>street_address</th>
      <th>interest_level</th>
      <th>num_photos</th>
      <th>num_features</th>
      <th>num_description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>1.0</td>
      <td>1</td>
      <td>6083</td>
      <td>2016-06-16 05:55:27</td>
      <td>Spacious 1 Bedroom 1 Bathroom in Williamsburg!...</td>
      <td>1887</td>
      <td>[Dining Room, Pre-War, Laundry in Building, Di...</td>
      <td>40.7108</td>
      <td>7170325</td>
      <td>-73.9539</td>
      <td>2767</td>
      <td>[https://photos.renthop.com/2/7170325_3bb5ac84...</td>
      <td>2400</td>
      <td>3343</td>
      <td>medium</td>
      <td>12</td>
      <td>7</td>
      <td>75</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1.0</td>
      <td>2</td>
      <td>8417</td>
      <td>2016-06-01 05:44:33</td>
      <td>BRAND NEW GUT RENOVATED TRUE 2 BEDROOMFind you...</td>
      <td>10848</td>
      <td>[Doorman, Elevator, Laundry in Building, Dishw...</td>
      <td>40.7513</td>
      <td>7092344</td>
      <td>-73.9722</td>
      <td>2565</td>
      <td>[https://photos.renthop.com/2/7092344_7663c19a...</td>
      <td>3800</td>
      <td>9008</td>
      <td>low</td>
      <td>6</td>
      <td>6</td>
      <td>129</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1.0</td>
      <td>2</td>
      <td>9344</td>
      <td>2016-06-14 15:19:59</td>
      <td>**FLEX 2 BEDROOM WITH FULL PRESSURIZED WALL**L...</td>
      <td>10904</td>
      <td>[Doorman, Elevator, Laundry in Building, Laund...</td>
      <td>40.7575</td>
      <td>7158677</td>
      <td>-73.9625</td>
      <td>3458</td>
      <td>[https://photos.renthop.com/2/7158677_c897a134...</td>
      <td>3495</td>
      <td>16634</td>
      <td>medium</td>
      <td>6</td>
      <td>6</td>
      <td>117</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1.5</td>
      <td>3</td>
      <td>3797</td>
      <td>2016-06-24 07:54:24</td>
      <td>A Brand New 3 Bedroom 1.5 bath ApartmentEnjoy ...</td>
      <td>12282</td>
      <td>[]</td>
      <td>40.7145</td>
      <td>7211212</td>
      <td>-73.9425</td>
      <td>1568</td>
      <td>[https://photos.renthop.com/2/7211212_1ed4542e...</td>
      <td>3000</td>
      <td>23484</td>
      <td>medium</td>
      <td>5</td>
      <td>0</td>
      <td>93</td>
    </tr>
    <tr>
      <th>15</th>
      <td>1.0</td>
      <td>0</td>
      <td>8717</td>
      <td>2016-06-28 03:50:23</td>
      <td>Over-sized Studio w abundant closets. Availabl...</td>
      <td>10791</td>
      <td>[Doorman, Elevator, Fitness Center, Laundry in...</td>
      <td>40.7439</td>
      <td>7225292</td>
      <td>-73.9743</td>
      <td>790</td>
      <td>[https://photos.renthop.com/2/7225292_901f1984...</td>
      <td>2795</td>
      <td>14705</td>
      <td>low</td>
      <td>4</td>
      <td>4</td>
      <td>39</td>
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
    </tr>
    <tr>
      <th>124003</th>
      <td>1.0</td>
      <td>1</td>
      <td>8623</td>
      <td>2016-04-26 16:09:55</td>
      <td>BRAND NEW TO MARKET 1BDR \r107TH AND LEXINGTON...</td>
      <td>2008</td>
      <td>[]</td>
      <td>40.7925</td>
      <td>6928108</td>
      <td>-73.9454</td>
      <td>1210</td>
      <td>[https://photos.renthop.com/2/6928108_231eb983...</td>
      <td>1700</td>
      <td>4321</td>
      <td>NaN</td>
      <td>10</td>
      <td>0</td>
      <td>46</td>
    </tr>
    <tr>
      <th>124005</th>
      <td>1.0</td>
      <td>2</td>
      <td>6600</td>
      <td>2016-04-21 05:06:19</td>
      <td>Convertible 2BR apartment features a brand new...</td>
      <td>9608</td>
      <td>[Doorman, Elevator, Laundry in Building, Dishw...</td>
      <td>40.7456</td>
      <td>6906674</td>
      <td>-73.9797</td>
      <td>743</td>
      <td>[https://photos.renthop.com/2/6906674_9fe899a8...</td>
      <td>4195</td>
      <td>3117</td>
      <td>NaN</td>
      <td>4</td>
      <td>8</td>
      <td>107</td>
    </tr>
    <tr>
      <th>124006</th>
      <td>1.0</td>
      <td>0</td>
      <td>0</td>
      <td>2016-04-20 01:31:52</td>
      <td>Let's get you in to see this $2,400/mo, recent...</td>
      <td>12047</td>
      <td>[Dogs Allowed, Cats Allowed]</td>
      <td>40.7416</td>
      <td>6897967</td>
      <td>-73.9829</td>
      <td>3959</td>
      <td>[]</td>
      <td>2400</td>
      <td>24588</td>
      <td>NaN</td>
      <td>0</td>
      <td>2</td>
      <td>140</td>
    </tr>
    <tr>
      <th>124007</th>
      <td>2.0</td>
      <td>2</td>
      <td>9131</td>
      <td>2016-04-08 02:26:45</td>
      <td>CooperCooper.com :: Web ID #171357; Access 100...</td>
      <td>12687</td>
      <td>[Doorman, Elevator, Cats Allowed, Dogs Allowed]</td>
      <td>40.7485</td>
      <td>6842183</td>
      <td>-73.9800</td>
      <td>1883</td>
      <td>[https://photos.renthop.com/2/6842183_b1fe51f4...</td>
      <td>6895</td>
      <td>16768</td>
      <td>NaN</td>
      <td>8</td>
      <td>4</td>
      <td>100</td>
    </tr>
    <tr>
      <th>124010</th>
      <td>1.0</td>
      <td>3</td>
      <td>1205</td>
      <td>2016-04-18 02:51:21</td>
      <td>New renovated Bright 3Br Murray Hill. 3 QUEEN ...</td>
      <td>9622</td>
      <td>[Garden/Patio, Laundry in Unit, Dishwasher, Ha...</td>
      <td>40.7447</td>
      <td>6889319</td>
      <td>-73.9741</td>
      <td>3733</td>
      <td>[https://photos.renthop.com/2/6889319_79f186e7...</td>
      <td>4695</td>
      <td>13752</td>
      <td>NaN</td>
      <td>8</td>
      <td>6</td>
      <td>56</td>
    </tr>
  </tbody>
</table>
<p>124011 rows × 18 columns</p>
</div>

--------------
features는 1개의 특징내에 띄어쓰기가 들어가는 경우가 있으므로 이를 '-'로 이어준 후 다른 feature간 ' ' 띄어쓰기 처리하여 전처리 하였습니다.

-----------

```python
alldata['features']=alldata['features'].apply(lambda x : ' '.join(['_'.join(i.split()) for i in x]))
alldata['features'][0]
```


'Elevator Laundry_in_Building Laundry_in_Unit Dishwasher Hardwood_Floors Outdoor_Space'

-------------------------
features column은 텍스트 형식을 지니고 있는데, 텍스트 데이터의 특징을 추출함으로써 예측 정확도를 높일 수 있습니다
Vectorizer(n_components 인자 변경)와 차원 축소의 조합을 통해 예측의 정확성을 실험하려합니다.
총 15번의 실험을 진행하였는데, 제가 사용한 Vectorizer와 차원 축소 방식은 다음과 같습니다.

Vectorizer 1: CountVectorizer
-------------------------


```python
from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
features=cv.fit_transform(alldata['features'])
```
----------------
그러나 진행할 때, 데이터가 방대해짐에 따라 속도가 느려지게 되는 경우를 고민하게 되었습니다.
더 효율적인 Vectorizer 방식을 찾아보니 해시 함수를 사용하여 단어에 대한 인덱스 번호를 생성하는 Hashing Vectorizer가 있음을 알게되었습니다.

Vectorizer 2: HashingVectorizer
------------------

```python
from sklearn.feature_extraction.text import HashingVectorizer
hv=HashingVectorizer()
features=hv.fit_transform(alldata['features'])
```

------------
적합한 Vectorizer방식을 고민하였을 때, 중요치 않은 정보가 학습에 중점적으로 사용된다면 예측의 정확성을 떨어뜨릴 수 있다는 생각이 들었습니다.
따라서 한 column에는 많이 등장하나 다른 데이터에 해당하는 column에서는 적게 등장할 수록 분별력이 있음을 이용하는 TfidfVectorizer에 대해 알게되었고 이를 적극 활용하였습니다.

Vectorizer3 : TfidfVectorizer
-------------

```python
from sklearn.feature_extraction.text import TfidfVectorizer
tv=TfidfVectorizer(stop_words='english')
features=tv.fit_transform(alldata["features"])
features[2]
```
-----------------
또한 Vectorizer 각각에 맞는 차원 축소 방식을 고민하였고, PCA / LDA / TruncatedSVD / NMF 를 적용하려합니다.
그러나 PCA와 LDA 적용에 적합치 않은 데이터임을 알게 되었습니다.

PCA 차원축소기법을 시도하였을 때, 

'from sklearn.preprocessing import StandardScaler
features=StandardScaler().fit_transform(alldata['features'].iloc[:,:-1])
from sklearn.decomposition import PCA
pca=PCA(n_components=2)
features_dec=pca.fit_transform(features)
features_dec'

TypeError: PCA does not support sparse input. See TruncatedSVD for a possible alternative. 발생하였고 해결하고자 
PCA 차원 축소 바로 이전에 StandardScaler를 이용해 평균이 0, 분산이 1인 표준 정규 분포로 변경하고자 하였습니다.

'from sklearn.preprocessing import StandardScaler
features=StandardScaler().fit_transform(alldata['features'].iloc[:,:-1])'

'too many indexrs'라는 error가 발생하여 데이터가 많은 이 경우에는 적합치 않아 보입니다

LDA 차원축소 기법을 시도하였을 때,

'from sklearn.discriminant_analysis import LinearDiscriminantAnalysis
lda=LinearDiscriminantAnalysis(n_components=10)
features_dec=lda.fit_transform(features,train['interest_level'])
features_dec'

TypeError: A sparse matrix was passed, but dense data is required. Use X.toarray() to convert to a dense numpy array. 발생하였고
text데이터를 온전히 classification 처럼 기준을 잡기에 부적합해 보입니다. (데이터 또한 양이 방대하여 LDA를 적용하기 어렵습니다.)

# 따라서 TruncatedSVD와 NMF 두가지 차원축소 기법을 이용하여 실험하겠습니다.

-------------------------------

```python
from sklearn.decomposition import TruncatedSVD
svd=TruncatedSVD(n_components=10)
features_dec=svd.fit_transform(features)
features_dec
```

array([[ 0.64819358,  0.2268297 ,  0.43422181, ..., -0.19330316, 0.08684557, -0.05572787],
      [ 0.74925628, -0.48301106, -0.00998859, ...,  0.01122021,0.01288652, -0.10817629],
      [ 0.6759141 , -0.44965067,  0.00340276, ...,  0.28775837,0.30178022, -0.0861425 ],
      ...,-0.0645448 , -0.0791891 ]])

```python
from sklearn.decomposition import NMF
nmf=NMF(n_components=10)
features_dec=nmf.fit_transform(features)
features_dec
```

array([[3.53982969e-02, 3.64364794e-02, 5.62484688e-02, ..., 0.00000000e+00, 2.14662288e-02, 1.78256081e-04],
      [4.67000249e-02, 0.00000000e+00, 0.00000000e+00, ...,4.73919124e-02, 4.06890991e-03, 3.70018723e-04],
      [4.18874316e-02, 0.00000000e+00, 0.00000000e+00, ...,4.34924434e-02, 4.96008463e-02, 0.00000000e+00],...,
      [0.00000000e+00, 9.53027887e-02, 1.76697103e-05, ...,0.00000000e+00, 0.00000000e+00, 0.00000000e+00]
      [0.00000000e+00, 6.76456287e-02, 1.13973140e-05, ...,5.99124970e-02, 0.00000000e+00, 0.00000000e+00],
      [0.00000000e+00, 3.20661262e-02, 0.00000000e+00, ..., 0.00000000e+00, 5.43850286e-02, 0.00000000e+00]])

-------------------
이 데이터에 HashingVectorizer를 적용 후 NMF로 차원 축소를 하게 되면 
ValueError: Negative values in data passed to NMF (input X) 에러가 발생합니다.
'from sklearn.preprocessing import StandardScaler
features=StandardScaler().fit_transform(alldata['features'].iloc[:,:-1])' 코드를 사용하여 
HashingVectorizer를 정규화 하더라도 IndexingError: Too many indexers 가 발생합니다.
따라서 HashingVectorizer를 적용하였을 때, 이 데이터는 NMF로 차원 축소가 불가능 합니다.

vectorizer후 차원 축소된 10개의 값을 alldata의 column으로 넣어줍니다.
---------------

```python
for i in range(10):
    alldata["features_dec" + str(i)]=features_dec[:,i]
    
display(alldata,alldata.columns)
```

Index(['bathrooms', 'bedrooms', 'building_id', 'created', 'description',
'display_address', 'features', 'latitude', 'listing_id', 'longitude',
'manager_id', 'photos', 'price', 'street_address', 'interest_level',
 'num_photos', 'num_features', 'num_description', 'features_dec0',
'features_dec1', 'features_dec2', 'features_dec3', 'features_dec4',
'features_dec5', 'features_dec6', 'features_dec7', 'features_dec8',
'features_dec9'], dtype='object')

-----------------
alldata에서 list, 문자형 칼럼 제외하고 숫자형(int,float) column은 따로 학습이 필요합니다.
따라서 object가 아닌 int나 float 만 alldata2로 구분하였습니다.

----------------


```python
alldata2=alldata[alldata.columns[alldata.dtypes!=object]]
alldata2
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>bathrooms</th>
      <th>bedrooms</th>
      <th>building_id</th>
      <th>display_address</th>
      <th>latitude</th>
      <th>listing_id</th>
      <th>longitude</th>
      <th>manager_id</th>
      <th>price</th>
      <th>street_address</th>
      <th>...</th>
      <th>features_dec0</th>
      <th>features_dec1</th>
      <th>features_dec2</th>
      <th>features_dec3</th>
      <th>features_dec4</th>
      <th>features_dec5</th>
      <th>features_dec6</th>
      <th>features_dec7</th>
      <th>features_dec8</th>
      <th>features_dec9</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>1.0</td>
      <td>1</td>
      <td>6083</td>
      <td>1887</td>
      <td>40.7108</td>
      <td>7170325</td>
      <td>-73.9539</td>
      <td>2767</td>
      <td>2400</td>
      <td>3343</td>
      <td>...</td>
      <td>0.035398</td>
      <td>0.036436</td>
      <td>0.056248</td>
      <td>0.036522</td>
      <td>0.000000</td>
      <td>0.000467</td>
      <td>0.000078</td>
      <td>0.000000</td>
      <td>0.021466</td>
      <td>0.000178</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1.0</td>
      <td>2</td>
      <td>8417</td>
      <td>10848</td>
      <td>40.7513</td>
      <td>7092344</td>
      <td>-73.9722</td>
      <td>2565</td>
      <td>3800</td>
      <td>9008</td>
      <td>...</td>
      <td>0.046700</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.053283</td>
      <td>0.000000</td>
      <td>0.048019</td>
      <td>0.036013</td>
      <td>0.047392</td>
      <td>0.004069</td>
      <td>0.000370</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1.0</td>
      <td>2</td>
      <td>9344</td>
      <td>10904</td>
      <td>40.7575</td>
      <td>7158677</td>
      <td>-73.9625</td>
      <td>3458</td>
      <td>3495</td>
      <td>16634</td>
      <td>...</td>
      <td>0.041887</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.045007</td>
      <td>0.000000</td>
      <td>0.000192</td>
      <td>0.033307</td>
      <td>0.043492</td>
      <td>0.049601</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1.5</td>
      <td>3</td>
      <td>3797</td>
      <td>12282</td>
      <td>40.7145</td>
      <td>7211212</td>
      <td>-73.9425</td>
      <td>1568</td>
      <td>3000</td>
      <td>23484</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>15</th>
      <td>1.0</td>
      <td>0</td>
      <td>8717</td>
      <td>10791</td>
      <td>40.7439</td>
      <td>7225292</td>
      <td>-73.9743</td>
      <td>790</td>
      <td>2795</td>
      <td>14705</td>
      <td>...</td>
      <td>0.051911</td>
      <td>0.000432</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.037501</td>
      <td>0.000000</td>
      <td>0.041090</td>
      <td>0.059595</td>
      <td>0.000000</td>
      <td>0.000000</td>
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
    </tr>
    <tr>
      <th>124003</th>
      <td>1.0</td>
      <td>1</td>
      <td>8623</td>
      <td>2008</td>
      <td>40.7925</td>
      <td>6928108</td>
      <td>-73.9454</td>
      <td>1210</td>
      <td>1700</td>
      <td>4321</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>124005</th>
      <td>1.0</td>
      <td>2</td>
      <td>6600</td>
      <td>9608</td>
      <td>40.7456</td>
      <td>6906674</td>
      <td>-73.9797</td>
      <td>743</td>
      <td>4195</td>
      <td>3117</td>
      <td>...</td>
      <td>0.040795</td>
      <td>0.045499</td>
      <td>0.000000</td>
      <td>0.046602</td>
      <td>0.000000</td>
      <td>0.042004</td>
      <td>0.031500</td>
      <td>0.041239</td>
      <td>0.003567</td>
      <td>0.000321</td>
    </tr>
    <tr>
      <th>124006</th>
      <td>1.0</td>
      <td>0</td>
      <td>0</td>
      <td>12047</td>
      <td>40.7416</td>
      <td>6897967</td>
      <td>-73.9829</td>
      <td>3959</td>
      <td>2400</td>
      <td>24588</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.095303</td>
      <td>0.000018</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>124007</th>
      <td>2.0</td>
      <td>2</td>
      <td>9131</td>
      <td>12687</td>
      <td>40.7485</td>
      <td>6842183</td>
      <td>-73.9800</td>
      <td>1883</td>
      <td>6895</td>
      <td>16768</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.067646</td>
      <td>0.000011</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.045957</td>
      <td>0.059912</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>124010</th>
      <td>1.0</td>
      <td>3</td>
      <td>1205</td>
      <td>9622</td>
      <td>40.7447</td>
      <td>6889319</td>
      <td>-73.9741</td>
      <td>3733</td>
      <td>4695</td>
      <td>13752</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.032066</td>
      <td>0.000000</td>
      <td>0.028463</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.054385</td>
      <td>0.000000</td>
    </tr>
  </tbody>
</table>
<p>124011 rows × 23 columns</p>
</div>

-----------
alldata의 column과 비교하였을 때, alldata2에는 created column을 제외하고 모두 숫자형으로 반영 되었음을 알 수 있습니다. (ex. photos->num_photos..)

---------------


```python
alldata2.columns
```


Index(['bathrooms', 'bedrooms', 'building_id', 'display_address', 'latitude',
       'listing_id', 'longitude', 'manager_id', 'price', 'street_address',
       'num_photos', 'num_features', 'num_description', 'features_dec0',
       'features_dec1', 'features_dec2', 'features_dec3', 'features_dec4',
       'features_dec5', 'features_dec6', 'features_dec7', 'features_dec8',
       'features_dec9'],
      dtype='object')

-------------
alldata의 숫자형으로 반영된 column만 분석에 사용하고자 train2와 test2 set는 alldata2로 부터 분할합니다.

-----------------


```python
train2=alldata2[:len(train)]
test2=alldata2[len(train):]
```

```python
from catboost import CatBoostClassifier
cbc=CatBoostClassifier(verbose=100)
cbc.fit(train2,train["interest_level"])
result=cbc.predict_proba(test2)
```

Learning rate set to 0.096534
0:	learn: 1.0274068	total: 82.1ms	remaining: 1m 22s
100:	learn: 0.5924534	total: 2.57s	remaining: 22.8s
200:	learn: 0.5567272	total: 4.63s	remaining: 18.4s
300:	learn: 0.5352452	total: 6.85s	remaining: 15.9s
400:	learn: 0.5174206	total: 9.13s	remaining: 13.6s
500:	learn: 0.5025656	total: 11.2s	remaining: 11.2s
600:	learn: 0.4891692	total: 13.3s	remaining: 8.84s
700:	learn: 0.4775547	total: 15.4s	remaining: 6.56s
800:	learn: 0.4670123	total: 17.5s	remaining: 4.34s
900:	learn: 0.4566555	total: 19.6s	remaining: 2.15s
999:	learn: 0.4470241	total: 21.7s	remaining: 0us


```python
sub=pd.read_csv("/kaggle/input/two-sigma-connect-rental-listing-inquiries/sample_submission.csv.zip")
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>listing_id</th>
      <th>high</th>
      <th>medium</th>
      <th>low</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7142618</td>
      <td>0.077788</td>
      <td>0.227529</td>
      <td>0.694683</td>
    </tr>
    <tr>
      <th>1</th>
      <td>7210040</td>
      <td>0.077788</td>
      <td>0.227529</td>
      <td>0.694683</td>
    </tr>
    <tr>
      <th>2</th>
      <td>7174566</td>
      <td>0.077788</td>
      <td>0.227529</td>
      <td>0.694683</td>
    </tr>
    <tr>
      <th>3</th>
      <td>7191391</td>
      <td>0.077788</td>
      <td>0.227529</td>
      <td>0.694683</td>
    </tr>
    <tr>
      <th>4</th>
      <td>7171695</td>
      <td>0.077788</td>
      <td>0.227529</td>
      <td>0.694683</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>74654</th>
      <td>6928108</td>
      <td>0.077788</td>
      <td>0.227529</td>
      <td>0.694683</td>
    </tr>
    <tr>
      <th>74655</th>
      <td>6906674</td>
      <td>0.077788</td>
      <td>0.227529</td>
      <td>0.694683</td>
    </tr>
    <tr>
      <th>74656</th>
      <td>6897967</td>
      <td>0.077788</td>
      <td>0.227529</td>
      <td>0.694683</td>
    </tr>
    <tr>
      <th>74657</th>
      <td>6842183</td>
      <td>0.077788</td>
      <td>0.227529</td>
      <td>0.694683</td>
    </tr>
    <tr>
      <th>74658</th>
      <td>6889319</td>
      <td>0.077788</td>
      <td>0.227529</td>
      <td>0.694683</td>
    </tr>
  </tbody>
</table>
<p>74659 rows × 4 columns</p>
</div>

------------------
result의 값을 sub에 적용할 때는 column중 'listing_id'를 제외한 'high', 'medium', 'low'로 input 해주어야 합니다.
따라서 모든 row의 값을 적용하되, 'high' column부터 적용 될 수 있도록
sub.iloc[:,1:]=result로 적용합니다.

--------------


```python
sub.iloc[:,1:]=result
result
```

array([[0.06048403, 0.58370268, 0.35581329],
[0.01975243, 0.93237652, 0.04787105],
[0.00210448, 0.98662512, 0.01127041],
...,
[0.00142394, 0.98373856, 0.0148375 ],
[0.00139356, 0.98817259, 0.01043385],
[0.04733993, 0.63413075, 0.31852932]])

----------------
train과 test는 json 형식으로 비정형 데이터와 정형 데이터가 혼재 되어 있습니다. (column 고정이 되지 않는 문제가 발생할 수 있습니다.)
sub의 column을 고정하고자 할 때는 아래와 같이 진행할 수 있습니다.

----------------------


```python
sub.columns=["listing_id","high","medium","low"]
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>listing_id</th>
      <th>high</th>
      <th>medium</th>
      <th>low</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7142618</td>
      <td>0.060484</td>
      <td>0.583703</td>
      <td>0.355813</td>
    </tr>
    <tr>
      <th>1</th>
      <td>7210040</td>
      <td>0.019752</td>
      <td>0.932377</td>
      <td>0.047871</td>
    </tr>
    <tr>
      <th>2</th>
      <td>7174566</td>
      <td>0.002104</td>
      <td>0.986625</td>
      <td>0.011270</td>
    </tr>
    <tr>
      <th>3</th>
      <td>7191391</td>
      <td>0.206648</td>
      <td>0.272816</td>
      <td>0.520536</td>
    </tr>
    <tr>
      <th>4</th>
      <td>7171695</td>
      <td>0.016039</td>
      <td>0.854183</td>
      <td>0.129778</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>74654</th>
      <td>6928108</td>
      <td>0.534783</td>
      <td>0.154751</td>
      <td>0.310466</td>
    </tr>
    <tr>
      <th>74655</th>
      <td>6906674</td>
      <td>0.051431</td>
      <td>0.644605</td>
      <td>0.303964</td>
    </tr>
    <tr>
      <th>74656</th>
      <td>6897967</td>
      <td>0.001424</td>
      <td>0.983739</td>
      <td>0.014837</td>
    </tr>
    <tr>
      <th>74657</th>
      <td>6842183</td>
      <td>0.001394</td>
      <td>0.988173</td>
      <td>0.010434</td>
    </tr>
    <tr>
      <th>74658</th>
      <td>6889319</td>
      <td>0.047340</td>
      <td>0.634131</td>
      <td>0.318529</td>
    </tr>
  </tbody>
</table>
<p>74659 rows × 4 columns</p>
</div>



```python
sub.to_csv("submission.csv",index=0)
```
----------------------------
HashingVectorizer를 사용하였을 때 negative 값 발생 및 정규화 어려움으로 NMF는 적용치 못하였습니다.
이를 제외하고 총 15가지 CASE를 적용하였을 때 다음과 같은 score를 얻었습니다. (score가 작을 수록 순위가 개선됩니다.)

![image](https://user-images.githubusercontent.com/69743938/172099087-721c2deb-da6d-4879-ab40-a307a6288816.png)


TruncatedSVD의 경우 차원의 수를 증가(10에서20)함에 따라 score가 개선되는 듯 보였으나 30 이상에서 오히려 미개선 되는 것을 확인하였습니다.
차원의 수가 증가함에 따라 학습의 정교성은 향상될 수 있으나 오히려 과적합이 발생할 우려가 있기 때문으로 보입니다.
# 같은 조건이라면 TfidfVectorizer에서 점수 개선이 뚜렷하였는데, Data내의 각 단어의 중요성을 고려하는 것이 효과적임을 느꼈습니다.
# 따라서 Text 분석의 경우에는 문맥에 맞는 단어의 의미 유추와 중요 특징을 추출하는 과정이 반드시 필요함을 느꼈습니다.
# TfidfVectorizer와 CountVectorizer를 사용하면 음수값이 존재하지 않아 NMF를 사용할 수 있으나 오히려 예측의 정확성은 TruncatedSVD 보다 떨어지기 때문에 제 예상을 빗나갔습니다.
# 이 데이터에서 가장 적합한 조합은 TfidfVectorizer와 TruncatedSVD의 사용인데 Vectorizer의 특성에 따라 적합한 차원 축소 기법을 고찰해야함을 느꼈습니다.
