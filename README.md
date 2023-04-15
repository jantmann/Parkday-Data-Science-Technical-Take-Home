# Parkday-Data-Science-Technical-Take-Home

This is the README.md file for this project. I'll update this by the final submission to detail my process of taking on this task, what I learned, and what could be done or improved in the future.

For this project, the objective was described as such:
"Analyze a set of user and meal data and 1) characterize the data for insights, 2) implement meal recommendations, and 3) suggest next steps in a data science pipeline buildout"

With this, the focus of the project was clarified to be fine-grained preference information, meaning information regarding ingredients. 

I analyzed two datasets, one containing user data with liked ingredients and another containing meal data with various data points including ingredients, recipe names, and cuisine type among others. My approach involved data cleaning, exploratory data analysis, and the use of term frequency-inverse document frequency (tf-idf) to calculate the similarity scores between user's liked ingredients and meal ingredients. The resulting meal recommendation system provides users with a list of top 5 recommended recipes based on their liked ingredients.

To begin this task, I first asked some questions to help better understand the wants and needs of a Parkday user. What would I want as a user of this app? What can make Parkday more valuable as a meal recommendation service? What features are critical in making accurate meal recommendations?

By answering these questions, I was able to gain a better understanding of what a good meal recommendation service should aim to accomplish. It should provide personalized recommendations based on preferences and restrictions, it should provide better recommendations over time as it acquires more data on the user, and it should be easy and simple to use.

I started by examining the data to see what I was working with. The user data set contained 186 different user IDs, user names, and their liked ingredients. The meal data contained more information for over 16000 meals-- recipe names, meal IDs, ingredients, flavors with flavor scores, cuisine type, prep times and images for each respective meal. 

The meal dataset required a fair amount of cleaning/manipulation. I first trimmed down the meal IDs such that they only contained their respective integers, and removed the img column as it would not be serving much purpose for this assignment. After attempting to access the values within the ingredients column, I quickly became aware that what appeared to be lists of ingredients were actually strings. I used the 'ast' module to convert these strings to lists such that each individual ingredient of each meal could be accessed for use in the recommendation model. I observed that the same issue was present in the flavor column and acted accordingly, as what appeared as dictionaries for each value were actually strings. After this, I also added a column identifying the number of ingredients within each meal. 

