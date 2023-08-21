# Customer Single View
:pushpin: **Goal** :fire: : 
> Our goal is to create a clear "Customer Single View" or a visual representation that can describe customers :standing_person: with clear insights :chart_with_upwards_trend: that can be used for further planning, such as organizing promotions for customer retention or creating product recommendations.

#
**Tools & Others**

[![](https://img.shields.io/badge/tools-Power_BI-rgb(244,208,63)?style=f?style=flat-square&logo=powerbi&logoColor=white)](https://app.powerbi.com/)
[![](https://img.shields.io/badge/tools-miro-rgb(244,208,63)?style=f?style=flat-square&logo=miro&logoColor=white)](https://miro.com/)
[![](https://img.shields.io/badge/code-python3.9-green?style=f?style=flat-square&logo=python&logoColor=white&color=2bbc8a)](https://www.python.org/)
[![](https://img.shields.io/badge/tools-jupyter-orange?style=f?style=flat-square&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![](https://img.shields.io/badge/tools-VSCode-blue?style=f?style=flat-square&logo=visualstudiocode&logoColor=white)](https://code.visualstudio.com/)
[![](https://img.shields.io/badge/tools-SkLearn-green?style=f?style=flat-square&logo=scikitlearn&logoColor=white&color=2bbc8a)](https://scikit-learn.org/stable/)
[![](https://img.shields.io/badge/ML-KMeans-green?style=f?style=flat-square&logo=scikitlearn&logoColor=white&color=2bbc8a)](https://scikit-learn.org/stable/)
[![](https://img.shields.io/badge/ML-preprocessing-green?style=f?style=flat-square&logo=scikitlearn&logoColor=white&color=2bbc8a)](https://scikit-learn.org/stable/)
[![](https://img.shields.io/badge/tools-Pandas-green?style=f?style=flat-square&logo=pandas&logoColor=white&color=2bbc8a)](https://pandas.pydata.org/)
[![](https://img.shields.io/badge/OS-Mac-green?style=f?style=flat-square&logo=macos&logoColor=white)](https://www.apple.com/macos/ventura/)
[![](https://img.shields.io/badge/OS-Windows-green?style=f?style=flat-square&logo=windows&logoColor=white)](https://www.microsoft.com/)
[![](https://img.shields.io/badge/Git_Update-22_Jun_2023-brightgreen?style=f?style=flat-square&logo=github&logoColor=white)](https://github.com/)

#
**Raw data** : <br>

[![](https://img.shields.io/badge/Git-.CSV-rgb(208,211,212)?style=f?style=flat-square&logo=github&logoColor=white)](https://github.com/jrdegbe/AdvancedAnalytics-MADT8101/blob/main/Section01/Week02_CustomerSingleView/supermarket.csv)

*( Supermarket (Lotus) data from 2006 to 2008, US )*

**CODE** : <br>

[![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jrdegbe/AdvancedAnalytics-MADT8101/blob/main/Section01/Week02_CustomerSingleView/KMean_LostusAnalytic.ipynb)

To the result : [Click!](https://github.com/jrdegbe/AdvancedAnalytics-MADT8101/blob/main/Section01/Week02_CustomerSingleView/week02.md#results)

# <h4>STEP 1</h4>
> - EDA
> - Clean DATA

First inspection <br>

![outputff](https://github.com/jrdegbe/AdvancedAnalytics-MADT8101/assets/118663358/f456a7e9-847d-4661-9403-60214cf20f84)

In the above image, a histogram plot of each feature (column) is presented to provide a rough overview after cleaning the data :broom: (e.g., filling in NaN values). Notable observations include:

Customers tend to buy products close to store closing hours :no_entry_sign::convenience_store: (8pm until close), followed by the afternoon :sun_with_face: (1pm - 2pm).
Most customers purchase fewer than 10 items, with a total price not exceeding :dollar: 50 US Dollars.
The majority of customers have a "Mid Market" :label: income level.
Age information for most customers is not provided :question:, and those with specified ages are predominantly "Young Families" :family: (YF).
Most customers use large shopping carts :shopping_cart: and tend to fill their carts completely.
The majority of purchases are of fresh products :cut_of_meat:.


#
<br>

To achieve the initial goal :pushpin: Goal :fire:, we will utilize Analytics Engines :gear:.

Based on the initial data, we can establish goals and determine the Analytics Engines :gear: that will be used in the following diagram: <br>
<br>

![Personal visualization - cust single view0](https://github.com/jrdegbe/AdvancedAnalytics-MADT8101/assets/118663358/76e88671-81ff-4350-9f36-fb4262470659)

<br>

**Explanation:

Referring to the Balance contribution at the upper left corner, we set a goal to focus :triangular_flag_on_post: on customer retention. Then, we arrange the Analytics Engines :gear: to see which tools can be used with this dataset.

Subsequently, we set goals :dart: and select suitable Analytics Engines :gear: to accomplish those goals.

<br>
From the above diagram, we can extend the DATA Insights to:

Set timing for purchases :soon: using short promotion periods to generate anticipation and stimulate purchases.
Create loyalty programs :tickets: or rewards to encourage repeat purchases.
Offer personalized recommendations :shopping: to customers with a strong business relationship to build goodwill :muscle:.

# <h4>STEP 2</h4>
- DATA Transformation

Data Transformation
In this step, we will transform the features to be suitable for use according to the goals and Analytics Engines :gear: specified in the initial plan.

Before proceeding, the 'cust_id' column should be dropped.

:white_check_mark: Features Transformation results :

![Personal visualization - Frame 1](https://github.com/jrdegbe/AdvancedAnalytics-MADT8101/assets/118663358/6f15bccd-c8d3-421b-adff-8c3230c6b607)


<br>

**note** : <br>
```ruby

CLV = ( (Average spend per 12months)/(Average Quantity per 12months) )*(Time ( Year ) of being customer)

```

<br>

In the following steps, Machine Learning will be utilized to assist in the process of Segmentation.
We will need to begin by dropping the 'cust_id' column. <br>

--------------------------------------

**CODE** : <br>

[![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jrdegbe/AdvancedAnalytics-MADT8101/blob/main/Week02_CustomerSingleView/KMean_LostusAnalytic.ipynb)

--------------------------------------

"The process will consist of a few steps as follows:

🚦 DATA Transformation by preprocessing ➡️ Dimensionality Reduction By TruncatedSVD or PCA ➡️ KMeans 🏌️‍♂️

This will yield results in 4 clusters. We will then arrange them in order from the worst ➡️ the best.

We will start with Group 1." <br>


It will start from group 1.

![lotusReport1](https://github.com/jrdegbe/AdvancedAnalytics-MADT8101/assets/118663358/5b4da01e-8f7a-4417-a16e-04d82a48f5da)


For this group, the characteristics are as follows:

They often use size S baskets and rarely fill the basket completely (mostly).
Life stage: OT (Others) or OA (Old Adult), with a generally diverse profile.
They tend to shop on Mondays around 9pm.
They usually purchase fresh products like :cut_of_meat:, followed by Grocery items.
Overall, this group has the lowest average annual spending.

The next group is Group 2.


![lotusReport2](https://github.com/jrdegbe/AdvancedAnalytics-MADT8101/assets/118663358/409449aa-90b8-4c83-98a6-b99acf7fffb8)


For this group, the characteristics are as follows:

Often use size M baskets and do not fill the basket completely.
Life stage: Mixed or diverse age ranges.
Usually come to shop on Sundays around 1pm.
Overall, this group tends to make more purchases per year compared to the previous group, albeit not significantly different.

The next group is Group 3

![lotusReport3](https://github.com/jrdegbe/AdvancedAnalytics-MADT8101/assets/118663358/a23b9c47-f4f6-4646-9f00-5a1bf9ec3ad6)



For this group, the characteristics are as follows:

They often use size L baskets and buy them full.
Life stage: OT (Others) or YF (Young Family).
They tend to make the most purchases in the afternoon (1 pm) and at 9 pm on Mondays and Fridays.
They usually buy products at low to medium prices.
They often buy Mixed-type products or a variety of different types together.
Overall, this group tends to make a relatively high average annual spending on purchases.
The next group is Group 0 (the last group). <br>

![lotusReport4_Page_1](https://github.com/jrdegbe/AdvancedAnalytics-MADT8101/assets/118663358/17957303-0834-42e2-9a46-3e87d7b79145)


For this group, the characteristics are as follows:

They often use size L shopping baskets and tend to overfill them.
They exhibit a high SKU penetration, often purchasing products from almost every category in the store.
Life stage: XX or unable to specify.
They tend to shop on Tuesdays around 9 pm.
They usually make purchases at a mid-to-high price range.
They frequently purchase fresh produce, such as :cut_of_meat:.
Overall, this group has the highest average annual spending on purchases.

<br>

# RESULTS

Next, we will proceed to compare each cluster in order to describe the characteristics of each group.

![lotusReport4_Page_2](https://github.com/jrdegbe/AdvancedAnalytics-MADT8101/assets/118663358/1e5b6c0b-ca3f-428a-ad3e-4685525168d3)

<br>

For the purpose of comparing each cluster, we will arrange them based on the rate of purchasing products from least to most. We find that:

Cluster 1 :purple_circle: (Purple) represents a group that tends to purchase non-food and non-grocery items in small quantities but frequently.
Cluster 2 :large_orange_diamond: (Orange) represents a group with undefined characteristics and is a smaller group. They do not make frequent purchases, but when they do, they buy more compared to Cluster 1 🟣.
Cluster 3 :large_blue_diamond: (Dark Blue) represents a group that infrequently makes purchases, but when they do, they buy a variety of items and tend to fill their shopping carts. They are also inclined to buy items at low prices :label:.
Cluster 0 :large_blue_circle: (Blue) represents a group that purchases expensive items :gem: in high quantities and frequently. They often buy fresh produce :cut_of_meat:.

<br>

When observing the characteristics of all 4 customer groups, we will randomly select one customer as a sample to be used as an example of the Customer Single View. <br>

![Personal visualization - cust single view1](https://github.com/jrdegbe/AdvancedAnalytics-MADT8101/assets/118663358/51fc11f6-b722-4663-866b-124683c898f7)


<br>
We can use the collected data to pursue the initial objectives, which involve designing loyalty tiers and implementing actions that align with their spending patterns. We can also create personalized campaigns targeting individual :bust_in_silhouette: or group :family_man_woman_girl_boy: preferences.

# Actions

In the example provided, if we are going to design a campaign to retain customers in Group 1 :large_blue_diamond: (dark blue color), we might start by:

Presenting a "Buy 1 Get 1" Promotion or :red_envelope: offering discounts on paired products exclusively for Group 1 customers. This could include setting specific timing, perhaps only on weekends (Saturday - Sunday), to attract customers from this group to shop :shopping_cart: more frequently, and so on.

#
Go to top : [Top :world_map:](https://github.com/jrdegbe/AdvancedAnalytics-MADT8101/blob/main/Section01/Week02_CustomerSingleView/week02.md#customer-single-view) <br>
Go to home page ( contents ) : 
[Home :earth_asia:](https://github.com/jrdegbe/AdvancedAnalytics-MADT8101#advancedanalytics)

