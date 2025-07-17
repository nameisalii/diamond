# Diamond 

## Project Idea: 
After dating his girlfriend since their college years, Tom decides to propose and begins searching for the perfect diamond. However, he is unsure about which diamond to choose. Our project develops a model that, based on Tom’s budget, recommends the best diamond for his engagement ring.


## Bio: 
Diamonds are formed deep within the Earth's mantle, under extreme heat and pressure, where carbon atoms crystallize over millions of years. Most diamonds originate 100-200 miles below the surface and are brought closer to the Earth’s crust through volcanic eruptions via kimberlite pipes. These natural processes create the sparkling gems prized for their rarity and beauty. Some diamonds are also lab-grown, created in controlled environments using high-pressure, high-temperature (HPHT) or chemical vapor deposition (CVD) methods, replicating natural conditions.

## How Diamond Prices Are Set:

The price of a diamond is determined by evaluating several key factors, commonly known as the "Four Cs":

Carat: The weight of the diamond, with larger diamonds generally being more expensive due to their rarity.
Cut: The quality of the diamond’s cut affects its brilliance and sparkle. A well-cut diamond reflects light better, increasing its value.
Clarity: This measures the presence of inclusions or blemishes. Flawless diamonds are rarer and command higher prices.
Color: Diamonds are graded on a scale from D (colorless) to Z (light yellow). Colorless diamonds are typically more valuable.
Key Factors Influencing Price

Beyond the Four Cs, other factors impact diamond pricing:

Shape: Popular shapes like round brilliants often cost more than less common shapes like marquise or pear due to demand and cutting complexity.
Fluorescence: Some diamonds glow under UV light, which can lower or increase value depending on intensity and market preferences.
Certification: Diamonds certified by reputable organizations like GIA or AGS are priced higher due to verified quality.
Market Demand and Trends: Consumer preferences, economic conditions, and trends (e.g., lab-grown vs. natural diamonds) influence pricing.
Source and Ethical Considerations: Conflict-free or sustainably sourced diamonds may carry a premium due to ethical demand.
By analyzing these factors, your ML diamond predictor model can help estimate diamond prices accurately, aiding buyers and sellers in making informed decisions.

<img width="660" height="402" alt="Screenshot 2025-07-16 at 8 13 09 PM" src="https://github.com/user-attachments/assets/13e5eb09-3511-4935-83bf-0818dc9851ed" />


<img width="622" height="495" alt="Screenshot 2025-07-16 at 8 13 24 PM" src="https://github.com/user-attachments/assets/882c872f-4694-45b8-9244-0bb40e69af18" />
<img width="524" height="367" alt="Screenshot 2025-07-16 at 8 13 33 PM" src="https://github.com/user-attachments/assets/d659ac8d-41fa-49b2-a398-61272f205904" />

## Creating ML Model
1. Before creating the model: we need to understand what is the client want from us? What kind of problem we need to solve?
2. This will be supervised, because we have the datasets (but our job is not just predict the price, but choose the best diamond in the range of budget)
3. This is Linear Regressor (we need to find continuous data)
4. Metrcices: (NOT: Accuracy, Pression, or Recal) we gonna test: R^2, MSE (Mean Squared Error) and MAE (Mean Absolute Error) to know for how many % we are close to exact numbers

### Uploading the datasets: Train and Test
<img width="703" height="274" alt="Screenshot 2025-07-16 at 8 16 03 PM" src="https://github.com/user-attachments/assets/0a6d6ffd-1541-42ae-ad16-3f76a23374e1" />

### Check the dataset and cleaning the datas 
1. Check for the value counts to see the imbalance 
<img width="572" height="711" alt="Screenshot 2025-07-16 at 8 39 45 PM" src="https://github.com/user-attachments/assets/f326a31f-f1e4-4064-bc4b-dcf7fa9ecc48" />

### Checking for correlation 
<img width="902" height="715" alt="Screenshot 2025-07-16 at 8 19 55 PM" src="https://github.com/user-attachments/assets/3618caee-ccfa-4827-97b9-23758256c0ea" />


### Encoding 
This is really important, if you do wrong encoding you project is gonna die and you cannot reach the high accuracy. So before choosing encoding tools, try to learn them and which one is good for your case.
Personally me using OrdinalEncoder, because it is not creating addition columns, it just changes everything in one column 
<img width="990" height="705" alt="Screenshot 2025-07-16 at 8 40 03 PM" src="https://github.com/user-attachments/assets/f83d7d7b-87de-4443-a98f-9a227cb1fd85" />
#### Before encoding
<img width="394" height="200" alt="Screenshot 2025-07-16 at 8 40 25 PM" src="https://github.com/user-attachments/assets/bca9171f-ea63-42a3-8a61-e27775fccea8" />
#### After Encoding
<img width="417" height="149" alt="Screenshot 2025-07-16 at 8 41 01 PM" src="https://github.com/user-attachments/assets/4c5dd83f-b9d1-4101-9c2d-0124c67ea864" />

### Training the model 
1. Divide into test and train (only use df_train dataset not test)
2. <img width="936" height="434" alt="Screenshot 2025-07-16 at 8 42 37 PM" src="https://github.com/user-attachments/assets/f2978ed1-58ab-4cde-875c-83cb04e2d86a" />
3. Using Cross Validation to get the better result
  <img width="904" height="398" alt="Screenshot 2025-07-16 at 8 43 04 PM" src="https://github.com/user-attachments/assets/76746e5b-7d48-48f3-9127-b1f4f6343655" />

### Checking the features for importance
1. this method helps to reduce and delete useless features and keep most important. BUT be carefull, most of the time low feature important features can be correlated and deleting them will cause to your whole dataset
  <img width="1311" height="711" alt="Screenshot 2025-07-16 at 8 44 56 PM" src="https://github.com/user-attachments/assets/f0e6c015-9eac-43cf-be83-589808aa511c" />
2. Used Grid Search | Random Forest as tool kit to train and test the model 
<img width="1184" height="696" alt="Screenshot 2025-07-16 at 8 45 37 PM" src="https://github.com/user-attachments/assets/f4d23786-7046-462f-bd34-1769da64b185" />
3. Created a graph that shows how the model choose the diamond
<img width="1216" height="540" alt="Screenshot 2025-07-16 at 8 46 19 PM" src="https://github.com/user-attachments/assets/7e6e2ad0-685f-41ec-9f66-06deb3ca6542" />

## Finalizing
1. Setting the budget min and max requirements

<img width="1226" height="474" alt="Screenshot 2025-07-16 at 8 47 00 PM" src="https://github.com/user-attachments/assets/f98651c6-7aff-4bfa-b631-c3b8af96e3c8" />

### Downloading the file to see it and it recommends 5 diamonds
<img width="994" height="155" alt="Screenshot 2025-07-16 at 8 47 55 PM" src="https://github.com/user-attachments/assets/f5207ca6-8097-436e-a142-6a302b4b5c2c" />


# Scores: 
Best CV score: 0.9818880004414441
Final Model Mean Squared Error: 95286945.58124174
Final Model R2 Score: 0.031935560452844625
Mean Squared Error: 1746395.6386835002
R2 Score: 0.9822575536987035


Author: Mukhammadzhon (Ali) Sirozhdinov
