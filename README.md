#The notebook Individual Project provides you details about how I created this picture. 
#It provides you also additionnals informations and plots (dynamics plots and explanations).


# The objective is to compare clustering methods on meteorological data
The analysis we be made with the Agglomerative and KMeans Clustering for all the data and for data transform with a PCA (Principal Componant Analysis).

Data sources: 

https://www.data.gouv.fr/fr/datasets/indices-annuels-de-precipitations-et-nombre-de-jours-de-precipitations-issus-du-modele-aladin-climat/#_ 
https://www.data.gouv.fr/fr/datasets/indices-annuels-de-temperature-et-nombre-de-jours-de-temperature-issus-du-modele-aladin-climat/

The uploaded data are in text format. For 8602 land points in France, the means of meteorologicals annuals data from 1976 to 2005 has been collected.

![Part on the 8602 points around France](https://github.com/MarcJ94/NEOMA-Project/blob/master/Screen%20Files/Screen%201.png)

After fews data preparation (data transformation and normalization, ...), we obtain a dataframe of around 25k rows and 32 columns.
Each columns is a meteorological caracteristic. 

Below, examples of data collected : 

     APAV : Anomalie de Précipitations journalières moyennes (mm/jour)
     APINT : Anomalie de Précipitation moyenne les jours pluvieux (mm/jour)
     ARR : Anomalie de Cumul de précipitation (mm)
     APFL90 : Anomalie de Fraction des précipitations journalières intenses (%)
     ARR1MM : Anomalie de Nombre de jours de pluie (jour)
     APXCWD : Anomalie de Nombre maximum de jours pluvieux consécutifs (jour)
     APN20MM : Anomalie de Nombre de jours de fortes précipitations (jour)
     APXCDD : Anomalie de Période de sécheresse (jour)
     
# Clustering Data

Our dataframe has more than 30 columns with potentialy biais between our columns. 
An PCA has been made on data in order to get less columns. 

Sources : 
https://towardsdatascience.com/an-approach-to-choosing-the-number-of-components-in-a-principal-component-analysis-pca-3b9f3d6e73fe

![Define numbers of components for the PCA](https://github.com/MarcJ94/NEOMA-Project/blob/master/Screen%20Files/PCA.png)

The links explain in detail how to choose the number of columns for the PCA.

For row data and data with PCA, we compute dendrogram and the Elbow Method to determine the number of cluster.

![Compute dendrogram](https://github.com/MarcJ94/NEOMA-Project/blob/master/Screen%20Files/Dendrogram.png)
![The Elbow Method](https://github.com/MarcJ94/NEOMA-Project/blob/master/Screen%20Files/Elbow%20Method.png)

As it is a data visualization courses, more clusters than the optimal number has been choosen. ALl parameters can be change in the notebook.

After computing clusters, we obtain with the librairy Geopandas this dataframe : 

![Final DataFrame](https://github.com/MarcJ94/NEOMA-Project/blob/master/Screen%20Files/Clustering%20DataFrame.png)


# Plotting Clusters

The clusters are plot with : 
- Matplotlib
- Plotly 

![Plotting with Matplotlib](https://github.com/MarcJ94/NEOMA-Project/blob/master/Screen%20Files/Clustering%20Matplotlib.png)
![Plotting with Plotly](https://github.com/MarcJ94/NEOMA-Project/blob/master/Screen%20Files/Clustering%20Plotly.png)

4 plotly graphics are available on the notebook.

# Conclusion

For the 4 clustering methods, it can be observed that the high-altitude areas are well listed. 
After reducing the number of columns, we see a loss of information, especially on the coastal areas. These zones are well defined for the clustering methods without PCA.  

The Agglomerative Clustering method seems to be the most adapted for these data but many parameters have to be taken into account such as the non-optimal number of clusters here.

The 4 graphs made with Plotly allow to see in detail the zones of each cluster and are much more adapted to this type of visualization.

