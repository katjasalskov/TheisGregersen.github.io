# COVID-19 Germany

This page will investigate the spread of COVID-19 in Germany.
The first case of the coronavirus in Germany were registered on Januray 28, 2020 in the state of Bavaria. 

etc.
etc.
etc.


Flot plot
![image](https://user-images.githubusercontent.com/60900143/80474990-7e6dd800-8948-11ea-8ea9-9ee43e9ab953.png) PAS PÅ!!


Flottere plot

Uhh,-nu-bliver-det-lækkert-plot


## "WOW!! HOLD NU OP" siger Sune om dette plot


![MEGA FEED](https://github.com/fertin/Random/blob/master/Assignment2P3.gif?fbclid=IwAR1XvovCVwFiMBrr2b-X-YPQyQpec-bzlBPhB8W44WzQpMigvvyP-9Nlkqo)Welcome to the TheisGregersen.github.io wiki!

https://raw.githubusercontent.com/fertin/Random/master/Assignment2P3.gif


{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "# Heatmap"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "import pandas as pd\n",
    "import numpy as np\n",
    "from sklearn.tree import DecisionTreeClassifier # Import Decision Tree Classifier\n",
    "from sklearn.model_selection import train_test_split # Import train_test_split function\n",
    "from sklearn import metrics #Import scikit-learn metrics module for accuracy calculation\n",
    "from sklearn.ensemble import RandomForestClassifier\n",
    "from sklearn.datasets import make_classification\n",
    "from sklearn.metrics import confusion_matrix,classification_report\n",
    "from sklearn.metrics import confusion_matrix, classification_report\n",
    "from sklearn.model_selection import KFold\n",
    "import datetime as dt\n",
    "import warnings\n",
    "from random import sample \n",
    "warnings.filterwarnings('ignore')\n",
    "from folium.plugins import MarkerCluster\n",
    "from folium.plugins import FastMarkerCluster\n",
    "\n",
    "import random\n",
    "import seaborn as sns\n",
    "import matplotlib.pyplot as plt\n",
    "%matplotlib inline\n",
    "import folium\n",
    "from folium.plugins import HeatMap\n",
    "from folium import plugins\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_covid = pd.read_csv(\"covid_de.csv\")\n",
    "df_demo = pd.read_csv(\"demographics_de.csv\")\n",
    "df_des = pd.read_excel(\"location.xlsx\")\n",
    "\n",
    "#drop NaN and change to datetime\n",
    "df_covid = df_covid.dropna()\n",
    "df_covid['date'] = pd.to_datetime(df_covid.date)\n",
    "\n",
    "\n",
    "#Changing gender in demografic to have same values as covid data set. \n",
    "df_demo['gender'] = df_demo['gender'].map({'female': 'F','male':'M'})\n",
    "\n",
    "\n",
    "#Merging the two dataset on state, age_group and gender. \n",
    "merged = pd.merge(df_covid,df_demo,how='inner', on=[\"state\",\"age_group\",\"gender\"])\n",
    "#And merging latitude and longtitude on the full dataset\n",
    "df = pd.merge(merged,df_des,how='inner',on=['county'])"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "#We start by plotting the map of Germany. \n",
    "map_DE=folium.Map([51, 9.8], zoom_start=6,tiles='Stamen Toner')\n",
    "folium.Marker([51, 9.8], popup='Germany').add_to(map_DE)\n",
    "map_DE"
   ]
  }
