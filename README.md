# WeRate_Dog_Analysis
# Introduction
The dataset is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs Brent." WeRateDogs has over 4 million followers and has received international media coverage.
# Data Gathering
The datasets for this analysis are not all in one place, they were gathered as described below;

- The first part of the data called twitter-archive-enhanced.csv has been given to Udacity and was made available to us.
- Image-prediction.csv file which is the second part was stored in Udacity server and was downloaded programmatically through https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv using requests command. The file contains three types of predictions of dog's breed from the images uploaded by the users.
- For the last part, I querried twitter API using the tweet_id present in the twitter-archive-enhanced.csv file, and each tweet's JSON data was stored in tweet_json.txt. The text file was read line by line to extract needed informations into pandas dataframe.
# Data Assessment
Having gathered the three datasets, I assessed them visually and programtically using pything packages like info(), describe(), isnull() and others. The following issues is documented

# Quality Issues
- In_reply_to_status_id, retweeted_status_timestamp, retweeted_status_user_id in_reply_to_user_id columns has null values
- Timestamp not in correct datatype
- Name is not accurate in all cases. some names are picked from the third word of the tweet
- Some tweets do not contain the dog's name
- Rating_numerator is not accurate in all cases
- Some values in rating_numerator and rating_denominator are outrageous
- Some outrageous values in rating_numerator and rating_denominator are actually values after decimal point
- Rating_numerator should be float datatype
- Some values in rating_numerator and rating_denominator are meant for more than one dog
- Missing values in name, doggo, floofer, pupper and puppo are represented by none.
- Dog breed could not be established with the predictions
- Tweet_id is of int datatype instead of string
- Some tweets are retweets
# Tidiness issues
- Doggo, floofer, pupper and puppo are stages/sizes of dogs and should be in one column
- The three datasets should be in one dataset
# Data Cleaning
The first step taken here was to duplicate all the three datasets. This is a standard procedure. The cleaning part is divided into three steps; define, code and test. Each of the documented issues is made to pass through the stages: define how the issue is to be rectified, write the code and then test to make sure it worked fine. Some rows with missing values were dropped and columns not useful for my analysis were dropped too. Lastly, the three datasets was merged.

# Conclusion
After proper cleaning, the merged dataset is now ready for further exploration.
