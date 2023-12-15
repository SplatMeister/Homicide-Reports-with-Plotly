# Homicide-Reports-with-Plotly https://www.kaggle.com/datasets/murderaccountability/homicide-reports
Data Visualization with Python
Section 2
The data set ‘Homicide Reports’ is a comprehensive data base of homicide cases in the United States between 1980 to 2014. This database consists over 600,000 records. Which includes attributes of crimes committed by perpetrators and the victims with their race, ethnicity, age and sex. In addition, it includes the relationship and type of weapon used between the victim and perpetrator. 
2.1 Uploading the data set into Python
In order to visualize the ‘Homicide Reports’ using Plotly as a visualization library. Firstly, Plotly is installed in the Python environment through pip package installer. 
In order to load the data set and to carry out the preprocessing of the data ‘Pandas’ library is used. Thereafter, ‘Plotly’ library is imported to visualize the data. Under the ‘Plotly’ library, Plotly Express, Plotly Graph Objects and Plotly Figure Factory are imported under its alias. (Appendix 2.1.1)
Under the Pandas function ‘pandas.read_csv’, the data frame is imported and assigned to a new variable ‘df’ for easy access and all hidden attributes are expanded for better analyzing. (Appendix 2.1.2)
2.2 Data preprocessing using Pandas library
Before preprocessing the data, understanding the actual size of the data frame and what are the unique values for each attribute is important. (Appendix 2.2.1)
Prior to visualizing the data, the data types across all attributes should be in the correct data types in order to visualize. The data type in attribute ‘Perpetrator Age’ is an ‘object’ data type. Therefore, the data type must be converted from ‘object’ to ‘int64’ data type. 
In order to convert all the values in the column ‘Perpetrator Age’ from ‘object’ to ‘int64’ data type, the ‘to_numeric()’ method in Pandas can be utilized. This method allows the transformation of all values in the specified column to the desired data type. (Appendix 2.2.2)
To further preprocess the data, after checking if the data frame includes any null values and removing the relevant null value (One null value in Perpetrator Age attribute, which was dropped). 
Upon checking if there are any incorrect values in all columns. It was evident that in the ‘Victim Age’ column there are 974 rows with the age of victims as ‘998’ and 9,281 rows with victim age as 99. Therefore, removed all the rows which had incorrect values in the data frame. (Appendix 2.2.3)
As the final stage of creating the data frame, removed the columns that are not relvent for analyzing  and making the data frame more consized for better analysis. Thereafter, indexing the columns in a correct order that is easy to glance through. As the first index ‘Year’ followed by ’Month’ and grouping the victim related attributes in one section and perpetrator attributes in the last section of the data frame. (Appendix 2.2.4)
For further analysis created a new atribute and measurment in the data frame named ‘Age Difference’ in order to calculate the age difference between the victim and the perpetrator. (Appendix 2.2.5) 
2.3 Data Visualization and insight generation with Plotly library
Based on the attributes of both perpetrator and victim the respective columns for race, weapon and even the relationship there may be patterns for homicide cases. Based on the above insight, following visualizations will be developed. 
1.	Identify which age group is responsible for the highest number of homicides.
2.	Visually represent the reason behind the large number unsolved cases.
3.	Visualize if the crimes are committed due to racial violence.
4.	Visualize all homicide cases have a patter between 1980 and 2015 against each month.
5.	Scatter plot to visualize the most effective weapon used by perpetrators. 
6.	Visualize the relationship among the victim and perpetrator. 
7.	Relationship between number of perpetrators and number of victims over the years. 
Visualizing perpetrator age against the victim counts, over 184,000 murders have been committed by unknown perpetrators. Therefore, these numbers can be considered as unknown perpetrators who may not have been even prosecuted (Appendix 2.3.1)

Fig Histogram visualizing murder count of perpetrators by age.

In order to visualize which perpetrator race is responsible for each victim’s race and to further identify the type of weapon used by the perpetrator, a sunburst chart is used for visualization (Figure 2). (Appendix 2.3.2)
 
Figure 2 Sunburst Chart on Victim and Perpetrator Race and Weapon Type

The center node of the sunburst chart (Figure 2) represents the total victims by ethnicity and 64% are white in ethnicity. In relation to the ethnicity of perpetrators 67% are white.  Most of the killings were committed using handguns among both races. Therefore, there are no visible racial killings among each ethnic groups.
 
2.4 Visualizing the victim count and the respective year and month.
Visualizing the the victim counts between 1980 and 2015 against each month to idenftify if there are months with high victim counts (Figure 3). 
In April 1995, there were large number of deaths. It is important to determine the cause of these death (Appendix 2.4.1).
 
Figure 3 Histogram Chart on Victim count against year and month

To further analyze the reason for a high victim count in April 1995, created a new subset data frame and visualized it on a scatter plot (Figure 4). (Appendix 2.4.2)
 
Figure 4 Scatterplot Chart of victim and perpetrator age plotted against weapon type.

During April 1995 many deaths are caused due to explosives. Furthermore, the age of the perpetrator is 27 years old and a male. Upon further investigation on Google, this was the ‘Okahoma Bombings’.
2.5 Understanding the crime solving rate based on victim race. 
Visualizing the number of solved and unsolved cases across all victim races (Figure 5). (Appendix 2.5.1)
 
Figure 5 Histogram crime solved by victim race.
There is a significant number of unsolved cases among both white and black races, and it is necessary to determine the reasons why these cases remain unsolvable.
 In order to visually represent these cases a scatter plot is used (Figure 6). (Appendix 2.5.2)
 
Figure 6 Scatterplot for all unsolved cases against victim and perpetrator age.
The white highlighted area represents many unsolved cases clustered together in proximity with victims between 16 to 30 and perpetrators between 18 to 30 years. 
Thereafter, created a new subset of a data frame for the above-mentioned age group to identify what weapon type was used for these unsolved cases. Handguns can be seen as the most used weapon through the years by perpetrators. However, many handguns related killings were visible in 1993(Figure 7). (Appendix 2.5.3)

 
Figure 7Density heat map on unsolved cases year-on-year against type of weapon used.
To check if handguns are the primary use of weapon type among sex of perpetrator using a heatmap (Figure 8). (Appendix 2.5.4)
 
Figure 8 Density heat map on unsolved cases perpetrator race type of weapon used
It is evident that handguns are the most used weapon in crimes, and it is highly unlikely that crimes involving the use of handguns as the weapon will be solved.
2.6 Exploring the Relationship Between Victims and Perpetrators in Homicide Cases over time. 
The attribute ‘Weapon’ consits 16 unique weapon types used by perptrators. Therefore, examining the relationship between ‘Drowning’ and ‘Poison’ as the weapon of choice to find insights. (Appendix 2.6.1)
 
Figure 9 Animated scatterplot perpetrator weapon type drowning and victim relationship.

In the above scatterplot (Figure 9), when the selected weapon type is ‘Drowning’. Most victims are unborn or below the age of 10 years. In most cases the perpetrators and victims’ relationship are either son, daughter, or a family member. Furthermore, it is evident that drowning is the most used method by perpetrators who are parents. Furthermore, drowning related crimes has gradually reduced since 1980. 
 
Figure 10 Animated scatterplot perpetrator weapon type poison and victim relationship.

As per the figure 10, in the year 1987 was a year that many of the elderly victims were killed by a 34-year-old perpetrator by poison. This could be one isolated incident, since all the killings took place in September. 
Poison is the second most used method for killing victims, although the number of victims is lower than those killed by drowning. Many perpetrators have been using poison to kill victims in the same age group.
In conclusion, there are many cases that are unsolved and most of these crimes are committed using a handgun by the perpetrator. Furthermore, the use of poison or drowning is common among victims who are aged below 10 years and these types of murders are done by family members. In relation to the ethnicity of victims, it is visible that the crimes are not predominantly due to racial killings. 
