# NEOMA-Project
Data Vizualization 

The notebook Individual Project provides you details about how I created this picture. 
It provides you also additionnals informations and plots (dynamics plots and explanations).


# The objective is to compare clustering methods on meteorological data
The analysis we be made with the Agglomerative and KMeans Clustering for all the data and for data transform with a PCA (Principal Componant Analysis).

Data sources: 

https://www.data.gouv.fr/fr/datasets/indices-annuels-de-precipitations-et-nombre-de-jours-de-precipitations-issus-du-modele-aladin-climat/#_ 
https://www.data.gouv.fr/fr/datasets/indices-annuels-de-temperature-et-nombre-de-jours-de-temperature-issus-du-modele-aladin-climat/

The uploaded data are in text format. For 8602 land points in France, the means of meteorologicals annuals data from 1976 to 2005 has been collected.


the means of the various annual precipitation indices and number of days of precipitation, on the 8602 land points in mainland France over the reference period (1976-2005) 

![Part on the 8602 points around France](https://github.com/MarcJ94/NEOMA-Project/blob/master/Screen%20Files/Screen%201.png)

After fews data preparation, we obtain a dataframe of around 25k rows and 32 columns.
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
