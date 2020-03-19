# Ebay-Car-Sales-Data-Analysis
An exploratory analysis of car listings on Ebay's German classifieds site

The main aim of this project is to carry out an analysis of car sales from the classsifieds section of eBay Germany.

The data set entails data across these point:
- dateCrawled - When this ad was first crawled. All field-values are taken from this date.
- name - Name of the car.
- seller - Whether the seller is private or a dealer.
- offerType - The type of listing
- price - The price on the ad to sell the car.
- abtest - Whether the listing is included in an A/B test.
- vehicleType - The vehicle Type.
- yearOfRegistration - The year in which the car was first registered.
- gearbox - The transmission type.
- powerPS - The power of the car in PS.
- model - The car model name.
- kilometer - How many kilometers the car has driven.
- monthOfRegistration - The month in which the car was   first registered.
- fuelType - What type of fuel the car uses.
- brand - The brand of the car.
- notRepairedDamage - If the car has a damage which is   not yet repaired.
- dateCreated - The date on which the eBay listing was   created.
- nrOfPictures - The number of pictures in the ad.
- postalCode - The postal code for the location of the   vehicle.
- lastSeenOnline - When the crawler saw this ad last     online.

The data set is made of 50000 entries across 20 columns largely populated by strings. Some columns have null values, however non of te columns have more than 20% null values.
The columns names are in camelcase instead of snakecase which would make it a challenge to replace spaces with underscores.

The initial exploration to determine cleaing tasks to be done, focusing on:

- Text columns where all or almost all values are the same to determine which to drop since they lack useful information for analysis.
- Numeric data stored as text which can be cleaned and converted

There was contitnued exploraion of the data to identify data that doesn't fit. Conducting and analysis of price and odometer_km columns:
looking for any outlying values that are unrealistically high or low that should be removed.

The next step enatiled exploration of registration years where I found there were outlying values in terms of the regostration years of vehicles with some being far into the past before vehicles were invented and the rest being into the future beyond the present time period.
This was follwed by the removal of rows with vehicle registration dates earlier then when the cars were made and those beyond the latest dates of the dataset. Cars available for public use en masse existed largely during the onset of the 20th century so all registration years dates prior to 1900 are invalid as are those with registration dates beyond the latest date of the date set 2016.

The next step was the exploration of vehicle brands to determine the top brand of cars listed. These are brands that individually make up more than 5% of the car listings, along with determining the average prices for each brand of car along with the average milage for each brand.
THe last step entailed translating the test in german to english by mapping them to corresponding english names.
