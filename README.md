### Project 2 - Ames Housing Data and Kaggle Challenge
---
This project examines a comprehensive housing dataset from the city of Ames in Iowa, USA. The model, and our understanding of the key features will be beneficial to existing home owners who might be considering selling their property to have a gauge of what prices their property could fetch. Also, people looking to buy houses want to get the best house possible given a budget. The goal of this project is hence to develop a predictive model that will be able to predict the house prices in Ames, Iowa.

**Problem statement:** Given a set of house features, what is the expected sale price of a house?

To answer this question, I fitted four different linear regression models to the housing data provided on Kaggle. The performance of the models is evaluated using the R2 metric, which is a measure of how much the model is able to explain the variance in the dataset, and the root mean square error (RMSE) metric, which is a measure the variance, or spread of the data.

Due to the scale of this project, it is split into three Jupyter notebooks: data cleaning, exploratory data analysis and feature engineering, and modelling and insights. This is the data cleaning notebook.

### Summary of Findings & Recommendations
---
Of the four models, linear regression, lasso regression, ridge regression and elastic net regression, that were used to model and make predictions, the **elastic net** and **ridge regression models** had the best predictive performance on housing sale price in Ames USA. As regularised regression methods, their ability to lend to reveal which features affect sale price the most made them superior to simple linear regression. 

People looking to buy houses would be able to use the model to see if their prospective purchases was going to be value for money given the listed features in an advertisement. Features such as square feet area, condition, age, and the location of the house are the most important determinant factors of how much a house is priced.
Buyers with limited or specific budgets will be able to find out what features they would be able to afford, e.g. how big a house they can buy in Northridge with a $ 50,000 budget. 
The model also allows buyers to identify the 'expensive' neighbourhoods such as Northridge Heights, Stone Brook, and Northridge. It also indicates areas where houses should be avoided, such as areas gazetted as commercial zones and places close to hte Iowa DOT and Rail Road

Conversely, people looking to sell their house would be able to use the model to get an estimate of how much they would be able to sell their house for, given the features of the house. Furthermore, to receive a higher valuation, house owners should strive to sell their houses sooner rather than later, as the age of the house is the biggest contributing factor to the decrease in value. Unsurprisingly, if the house is severely damaged, its value drops. Sellers looking to increase the value of their home could consider:

- repainting the interior and exterior of the house to improve overall material and finish quality
- renovating the kitchen to improve kitchen quality
- installing a fireplace 
- renovating the garage if it is in bad condition

However, as the model was developed using data on houses sold between 2006 - 2010 in Ames, USA, it may have limited applicabilities. Firstly, it captures only a small time frame of four years which is not enough to capture any annual patterns in sale price that could arise as a result of external factors, such as policy changes and the current economy. It is also unknown whether or not the sale prices had been adjusted for inflation within those years, which would have been a source of variation in saleprice otherwise. 
It would also be inaccurate to generalise it to 2020 as house prices may have changed due to one or more of these factors or even with Covid-19. 

There may also be other factors affecting house price, since the model only accounted for 83-84 \% of the variation in sale price. The remaining 16-17\% could be due to the fact that the model is apparently not very accurate when it comes to larger and more expensive houses exceeding 400,000 in price. This could possibly explained by the RMSE of around 32,000 which means that our best linear prediction of the sale price based on all of the attributes are off by around $ 32,000 on the test set. The first Kaggle submission appears to confirm the RMSE with a score of 32962.60954. 

It must also be noted that the model is specific to Ames and may not be as accurate when applied to data from another city or country. Variations in cultures mean people in different countries look for different things in a house, which would in turn affect sale price. For example, having a fireplace in a house in Singapore (or anywhere in the tropics) is unlikely to bring the value of the house up, as few people in these places want a fireplace in their house. To make the model more universal, data should be extracted from a sample of the entire world or even just a region so that distributions form a bell curve. This would allow us to generalise our findings to different regions other than Ames. 

There are many steps to improve the applicability and ability of the model. Apart from increasing the population from just Ames, Iowas to perhaps the state, the USA or even the entire world, we can consider adding more data from a wider time frame, from different locations, and on more universal features. 

To improve the accuacy of the model, we could also improve the feature engineering step of modelling as shown in the second workbook. Greater care can be taken in further reducing the number of features that have been fed into the modelby amalgamating information, such as combining 2 features such as `fireplace` and `fireplace_qu` into a single feature that just indicates the presence of a fireplace. As proven in the two Kaggle submissions, it is better to drop features altogether as opposed to dropping single values, leaving 'data holes' in the dataset.  

House prices are by their very nature difficult to predict as it is also affected by buyers' psychology, the economic climate, and other factors not included in the present dataset. It is unlikely we will be able to construct a perfect model and the aim of this model is therefore only present as a guideline to inform buyers ans sellers of how to snag the best deals and improve selling prices. 

Two Kaggle submissions were made from this project. The first submission scored an RMSE of 32962.60954 and the second submission scored an RMSE of 325139.15805.

### Data Dictionary
---
       SalePrice - the property's sale price in dollars. This is the target variable.
       MSSubClass: The building class
           20 1-STORY 1946 & NEWER ALL STYLES
           30 1-STORY 1945 & OLDER
           40 1-STORY W/FINISHED ATTIC ALL AGES
           45 1-1/2 STORY - UNFINISHED ALL AGES
           50 1-1/2 STORY FINISHED ALL AGES
           60 2-STORY 1946 & NEWER
           70 2-STORY 1945 & OLDER
           75 2-1/2 STORY ALL AGES
           80 SPLIT OR MULTI-LEVEL
           85 SPLIT FOYER
           90 DUPLEX - ALL STYLES AND AGES
           120 1-STORY PUD (Planned Unit Development) - 1946 & NEWER
           150 1-1/2 STORY PUD - ALL AGES
           160 2-STORY PUD - 1946 & NEWER
           180 PUD - MULTILEVEL - INCL SPLIT LEV/FOYER
           190 2 FAMILY CONVERSION - ALL STYLES AND AGES
       MSZoning: Identifies the general zoning classification of the sale.
           A Agriculture
           C Commercial
           FV Floating Village Residential
           I Industrial
           RH Residential High Density
           RL Residential Low Density
           RP Residential Low Density Park
           RM Residential Medium Density
       LotFrontage: Linear feet of street connected to property
       LotArea: Lot size in square feet
       Street: Type of road access to property
           Grvl Gravel
           Pave Paved
       Alley: Type of alley access to property
           Grvl Gravel
           Pave Paved
           NA No alley access
       LotShape: General shape of property
           Reg Regular
           IR1 Slightly irregular
           IR2 Moderately Irregular
           IR3 Irregular
       LandContour: Flatness of the property
           Lvl Near Flat/Level
           Bnk Banked - Quick and significant rise from street grade to building
           HLS Hillside - Significant slope from side to side
           Low Depression
       Utilities: Type of utilities available
           AllPub All public Utilities (E,G,W,& S)
           NoSewr Electricity, Gas, and Water (Septic Tank)
           NoSeWa Electricity and Gas Only
           ELO Electricity only
       LotConfig: Lot configuration
           Inside Inside lot
           Corner Corner lot
           CulDSac Cul-de-sac
           FR2 Frontage on 2 sides of property
           FR3 Frontage on 3 sides of property
       LandSlope: Slope of property
           Gtl Gentle slope
           Mod Moderate Slope
           Sev Severe Slope
       Neighborhood: Physical locations within Ames city limits
           Blmngtn Bloomington Heights
           Blueste Bluestem
           BrDale Briardale
           BrkSide Brookside
           ClearCr Clear Creek
           CollgCr College Creek
           Crawfor Crawford
           Edwards Edwards
           Gilbert Gilbert
           GrnHill Green Hill
           IDOTRR Iowa DOT and Rail Road
           MeadowV Meadow Village
           Mitchel Mitchell
           Names North Ames
           NoRidge Northridge
           NPkVill Northpark Villa
           NridgHt Northridge Heights
           NWAmes Northwest Ames
           OldTown Old Town
           SWISU South & West of Iowa State University
           Sawyer Sawyer
           SawyerW Sawyer West
           Somerst Somerset
           StoneBr Stone Brook
           Timber Timberland
           Veenker Veenker
       Condition1: Proximity to main road or railroad
           Artery Adjacent to arterial street
           Feedr Adjacent to feeder street
           Norm Normal
           RRNn Within 200' of North-South Railroad
           RRAn Adjacent to North-South Railroad
           PosN Near positive off-site feature--park, greenbelt, etc.
           PosA Adjacent to postive off-site feature
           RRNe Within 200' of East-West Railroad
           RRAe Adjacent to East-West Railroad
       Condition2: Proximity to main road or railroad (if a second is present)
           Artery Adjacent to arterial street
           Feedr Adjacent to feeder street
           Norm Normal
           RRNn Within 200' of North-South Railroad
           RRAn Adjacent to North-South Railroad
           PosN Near positive off-site feature--park, greenbelt, etc.
           PosA Adjacent to postive off-site feature
           RRNe Within 200' of East-West Railroad
           RRAe Adjacent to East-West Railroad
       BldgType: Type of dwelling
           1Fam Single-family Detached
           2FmCon Two-family Conversion; originally built as one-family dwelling
           Duplx Duplex
           TwnhsE Townhouse End Unit
           TwnhsI Townhouse Inside Unit
       HouseStyle: Style of dwelling
           1Story One story
           1.5Fin One and one-half story: 2nd level finished
           1.5Unf One and one-half story: 2nd level unfinished
           2Story Two story
           2.5Fin Two and one-half story: 2nd level finished
           2.5Unf Two and one-half story: 2nd level unfinished
           SFoyer Split Foyer
           SLvl Split Level
       OverallQual: Overall material and finish quality
           10 Very Excellent
           9 Excellent
           8 Very Good
           7 Good
           6 Above Average
           5 Average
           4 Below Average
           3 Fair
           2 Poor
           1 Very Poor
       OverallCond: Overall condition rating
           10 Very Excellent
           9 Excellent
           8 Very Good
           7 Good
           6 Above Average
           5 Average
           4 Below Average
           3 Fair
           2 Poor
           1 Very Poor
       YearBuilt: Original construction date
       YearRemodAdd: Remodel date (same as construction date if no remodeling or additions)
       RoofStyle: Type of roof
           Flat Flat
           Gable Gable
           Gambrel Gabrel (Barn)
           Hip Hip
           Mansard Mansard
           Shed Shed
       RoofMatl: Roof material
           ClyTile Clay or Tile
           CompShg Standard (Composite) Shingle
           Membran Membrane
           Metal Metal
           Roll Roll
           Tar&Grv Gravel & Tar
           WdShake Wood Shakes
           WdShngl Wood Shingles
       Exterior1st: Exterior covering on house
           AsbShng Asbestos Shingles
           AsphShn Asphalt Shingles
           BrkComm Brick Common
           BrkFace Brick Face
           CBlock Cinder Block
           CemntBd Cement Board
           HdBoard Hard Board
           ImStucc Imitation Stucco
           MetalSd Metal Siding
           Other Other
           Plywood Plywood
           PreCast PreCast
           Stone Stone
           Stucco Stucco
           VinylSd Vinyl Siding
           Wd Sdng Wood Siding
           WdShing Wood Shingles
       Exterior2nd: Exterior covering on house (if more than one material)
           AsbShng Asbestos Shingles
           AsphShn Asphalt Shingles
           BrkComm Brick Common
           BrkFace Brick Face
           CBlock Cinder Block
           CemntBd Cement Board
           HdBoard Hard Board
           ImStucc Imitation Stucco
           MetalSd Metal Siding
           Other Other
           Plywood Plywood
           PreCast PreCast
           Stone Stone
           Stucco Stucco
           VinylSd Vinyl Siding
           Wd Sdng Wood Siding
           WdShing Wood Shingles
       MasVnrType: Masonry veneer type
           BrkCmn Brick Common
           BrkFace Brick Face
           CBlock Cinder Block
           None None
           Stone Stone
       MasVnrArea: Masonry veneer area in square feet
       ExterQual: Exterior material quality
           Ex Excellent
           Gd Good
           TA Average/Typical
           Fa Fair
           Po Poor
       ExterCond: Present condition of the material on the exterior
           Ex Excellent
           Gd Good
           TA Average/Typical
           Fa Fair
           Po Poor
       Foundation: Type of foundation
           BrkTil Brick & Tile
           CBlock Cinder Block
           PConc Poured Contrete
           Slab Slab
           Stone Stone
           Wood Wood
       BsmtQual: Height of the basement
           Ex Excellent (100+ inches)
           Gd Good (90-99 inches)
           TA Typical (80-89 inches)
           Fa Fair (70-79 inches)
           Po Poor (<70 inches)
           NA No Basement
       BsmtCond: General condition of the basement
           Ex Excellent
           Gd Good
           TA Typical - slight dampness allowed
           Fa Fair - dampness or some cracking or settling
           Po Poor - Severe cracking, settling, or wetness
           NA No Basement
       BsmtExposure: Walkout or garden level basement walls
           Gd Good Exposure
           Av Average Exposure (split levels or foyers typically score average or above)
           Mn Mimimum Exposure
           No No Exposure
           NA No Basement
       BsmtFinType1: Quality of basement finished area
           GLQ Good Living Quarters
           ALQ Average Living Quarters
           BLQ Below Average Living Quarters
           Rec Average Rec Room
           LwQ Low Quality
           Unf Unfinshed
           NA No Basement
       BsmtFinSF1: Type 1 finished square feet
       BsmtFinType2: Quality of second finished area (if present)
           GLQ Good Living Quarters
           ALQ Average Living Quarters
           BLQ Below Average Living Quarters
           Rec Average Rec Room
           LwQ Low Quality
           Unf Unfinshed
           NA No Basement
       BsmtFinSF2: Type 2 finished square feet
       BsmtUnfSF: Unfinished square feet of basement area
       TotalBsmtSF: Total square feet of basement area
       Heating: Type of heating
           Floor Floor Furnace
           GasA Gas forced warm air furnace
           GasW Gas hot water or steam heat
           Grav Gravity furnace
           OthW Hot water or steam heat other than gas
           Wall Wall furnace
       HeatingQC: Heating quality and condition
           Ex Excellent
           Gd Good
           TA Average/Typical
           Fa Fair
           Po Poor
       CentralAir: Central air conditioning
           N No
           Y Yes
       Electrical: Electrical system
           SBrkr Standard Circuit Breakers & Romex
           FuseA Fuse Box over 60 AMP and all Romex wiring (Average)
           FuseF 60 AMP Fuse Box and mostly Romex wiring (Fair)
           FuseP 60 AMP Fuse Box and mostly knob & tube wiring (poor)
           Mix Mixed
       1stFlrSF: First Floor square feet
       2ndFlrSF: Second floor square feet
       LowQualFinSF: Low quality finished square feet (all floors)
       GrLivArea: Above grade (ground) living area square feet
       BsmtFullBath: Basement full bathrooms
       BsmtHalfBath: Basement half bathrooms
       FullBath: Full bathrooms above grade
       HalfBath: Half baths above grade
       Bedroom: Number of bedrooms above basement level
       Kitchen: Number of kitchens
       KitchenQual: Kitchen quality
           Ex Excellent
           Gd Good
           TA Typical/Average
           Fa Fair
           Po Poor
       TotRmsAbvGrd: Total rooms above grade (does not include bathrooms)
       Functional: Home functionality rating
           Typ Typical Functionality
           Min1 Minor Deductions 1
           Min2 Minor Deductions 2
           Mod Moderate Deductions
           Maj1 Major Deductions 1
           Maj2 Major Deductions 2
           Sev Severely Damaged
           Sal Salvage only
       Fireplaces: Number of fireplaces
       FireplaceQu: Fireplace quality
           Ex Excellent - Exceptional Masonry Fireplace
           Gd Good - Masonry Fireplace in main level
           TA Average - Prefabricated Fireplace in main living area or Masonry Fireplace in basement
           Fa Fair - Prefabricated Fireplace in basement
           Po Poor - Ben Franklin Stove
           NA No Fireplace
       GarageType: Garage location
           2Types More than one type of garage
           Attchd Attached to home
           Basment Basement Garage
           BuiltIn Built-In (Garage part of house - typically has room above garage)
           CarPort Car Port
           Detchd Detached from home
           NA No Garage
       GarageYrBlt: Year garage was built
       GarageFinish: Interior finish of the garage
           Fin Finished
           RFn Rough Finished
           Unf Unfinished
           NA No Garage
       GarageCars: Size of garage in car capacity
       GarageArea: Size of garage in square feet
       GarageQual: Garage quality
           Ex Excellent
           Gd Good
           TA Typical/Average
           Fa Fair
           Po Poor
           NA No Garage
       GarageCond: Garage condition
           Ex Excellent
           Gd Good
           TA Typical/Average
           Fa Fair
           Po Poor
           NA No Garage
       PavedDrive: Paved driveway
           Y Paved
           P Partial Pavement
           N Dirt/Gravel
       WoodDeckSF: Wood deck area in square feet
       OpenPorchSF: Open porch area in square feet
       EnclosedPorch: Enclosed porch area in square feet
       3SsnPorch: Three season porch area in square feet
       ScreenPorch: Screen porch area in square feet
       PoolArea: Pool area in square feet
       PoolQC: Pool quality
           Ex Excellent
           Gd Good
           TA Average/Typical
           Fa Fair
           NA No Pool
       Fence: Fence quality
           GdPrv Good Privacy
           MnPrv Minimum Privacy
           GdWo Good Wood
           MnWw Minimum Wood/Wire
           NA No Fence
       MiscFeature: Miscellaneous feature not covered in other categories
           Elev Elevator
           Gar2 2nd Garage (if not described in garage section)
           Othr Other
           Shed Shed (over 100 SF)
           TenC Tennis Court
           NA None
       MiscVal: $Value of miscellaneous feature
       MoSold: Month Sold
       YrSold: Year Sold
       SaleType: Type of sale
           WD Warranty Deed - Conventional
           CWD Warranty Deed - Cash
           VWD Warranty Deed - VA Loan
           New Home just constructed and sold
           COD Court Officer Deed/Estate
           Con Contract 15% Down payment regular terms
           ConLw Contract Low Down payment and low interest
           ConLI Contract Low Interest
           ConLD Contract Low Down
           Oth Other
