<img align='right' src="https://www.inderdhillon.com/files/logo-gray.png" alt="InderDhillon.com" height="120" width="120">

<h1>Report - Opening an Establishment</h1><br>
<b>Inder Dhillon</b><br>
<i>inderdhillon.com</i><br>

### Description:
Using clustering to find localities in Vancouver to suggest a business strategy for opening an establishment (in this case a pizza place) tailored to the locality.
<hr>

### 1. Introduction
When entering a market by opening a business, it is important to pay attention to the external factors as evident by Porter's Five Forces Model. So it is vital to know the barriers of entry and existing competition when opening a new establishment in a location to select a business strategy. This project attempts to answer this question: <br><br>
<i>"What business strategy to use when opening a pizza restaurant in a locality in Vancouver?"</i>


We take the example of a pizza place to simplify the question but really it applies to opening any type of establishment which has a goal of staying profitable. 
The answer to this question would be useful to potential investors, people looking to buy a franchise of a restaurant, entrepreneurs looking to start a business and more.

### 2. Data
The data used is the localities defined by city of Vancouver from their official website. 
This data will then be used to make requests from the Foursquare API to get a dataset of what kind of venues exist in this locality. That data will then be used to cluster localities based on their similarity to provide us with groups to which the same business strategy would apply.<br>

<img src='https://github.com/Inder-Dhillon/Where-To-Open-Establishment/raw/master/files/Vancouver.PNG'>

### 3. Methodology
Pandas has been used in this project to wrangle data to get it in a useable form. The dataset from City of Vancouver is used to get venues for each locality from Foursquare's Places API. Then one-hot encoding is used to get it in a numerical form so it can be used for K-means clustering. We use K-means clustering because this is a classification problem with unlabelled data. So, unsupervised learning is appropriate for this dataset. To select the optimal number of clusters we use the elbow method for K-Means clustering as follows.<br>
<img src='https://github.com/Inder-Dhillon/Where-To-Open-Establishment/raw/master/files/kmeans.png'><br><br>

<p style="clear:both;">
We observe the elbow point occurs at k=3. We then cluster the dataset using k = 3 to obtain three clusters.</p>

### 4. Results
The resultant clusters from our Machine Learning cycle is visualized below using Folium.<br>

<img src='https://github.com/Inder-Dhillon/Where-To-Open-Establishment/raw/master/files/Cluster.PNG' >
<p style="clear:both;">
<br>We observe that a bigger part of the City of Vancouver falls in one cluster which is made up of diversified markets with the exception of two localities. The clusters contain the following localities:</p>

#### Green Cluster:<br>

1                     Downtown<br>
2                     Fairview<br>
3           Grandview-Woodland<br>
4             Hastings-Sunrise<br>
5                      Marpole<br>
6                   Riley Park<br>
7                  Shaughnessy<br>
8                   Strathcona<br>
9                     West End<br>
10           Dunbar-Southlands<br>
11                  Kerrisdale<br>
12                   Killarney<br>
13                   Kitsilano<br>
14                South Cambie<br>
15         Victoria-Fraserview<br>
16    Kensington-Cedar Cottage<br>
17              Mount Pleasant<br>
18                    Oakridge<br>
19         Renfrew-Collingwood<br>
21             West Point Grey<br>

##### Composition:
![Composition](https://github.com/Inder-Dhillon/Where-To-Open-Establishment/raw/master/files/plot2.PNG)

#### Red Cluster:<br>
1                       Sunset<br>

##### Composition:
![Composition](https://github.com/Inder-Dhillon/Where-To-Open-Establishment/raw/master/files/plot3.PNG)
#### Purple Cluster:<br>
1                Arbutus-Ridge<br>

##### Composition:
![Composition](https://github.com/Inder-Dhillon/Where-To-Open-Establishment/raw/master/files/plot1.PNG)
### 5. Discussion
#### Green Cluster:
​
These seem to be well established localities with a lot of options where the barriers of entry might be high.
​

#### Red Cluster:
​
This cluster seems to be more residential with less barriers of entry.
​
#### Purple Cluster:
​
The foursquare API gives us the top 100 venues in the locality. We take the presence of an established shopping mall into consideration.
### 6. Conclusion

#### Green Cluster:

A differentiation strategy must be applied in these localities if a pizza place is to be opened. A lot of investment will be required due to high barriers of entry and to provide differentiated value to attract customers.

#### Red Cluster:

Localities in this cluster are appropriate for small mom and pop stores which don't require a lot of investment and marketing. Stores here can remain profitable just off the basis of a lack of competition and having a market stronghold.

#### Purple Cluster:

Opening a franchise pizza store (like Pizza Hut) is opt for this cluster due to the presense of a prominent shopping mall.
### 7. Future Implications

The insights provided by this project is limited to the type of enviornment the establishment is looking to move into and the forces of competition. It doesn't take into account other indicators which might predict the success of a new business like population, traffic, landmarks and crime statistics. While those factors are out of the scope of this project for now, data for these indicators is readily available and can be used to enhance this model to cluster localities based on their socio-cultural conditions and demographics as well.
