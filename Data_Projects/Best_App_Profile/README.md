## About this project:

The strategy implemented in the document to find profitable app profiles for the App Store and Google Play markets can be summarized into the following structured steps:

### 1. **Objective Definition**
   - The primary goal is to identify app profiles that are likely to attract more users and generate revenue through in-app ads.
   - The analysis focuses on free apps, as the company's revenue depends on user engagement with ads.

---

### 2. **Data Collection**
   - Two datasets were selected for analysis:
     - **Google Play** dataset with approximately 10,000 apps.
     - **App Store** dataset with around 7,000 apps.
   - The datasets were obtained from external sources like Kaggle.

---

### 3. **Data Exploration and Cleaning**
   - Initial exploration of the datasets was conducted to understand their structure and identify useful columns.
   - Several cleaning tasks were performed:
     - **Error Removal**: For instance, the Google Play dataset had a row with a rating of 19 (out of a max 5), which was deleted.
     - **Duplicate Removal**: Apps with multiple entries were filtered, retaining the entry with the highest number of reviews to ensure data reliability.
     - **Filtering for English Apps**: Non-English apps were removed using a function that checks for the presence of non-ASCII characters.
     - **Filtering for Free Apps**: Only free apps were retained for the analysis.

---

### 4. **Frequency Analysis**
   - **App Store**: The most common genres were analyzed using the `prime_genre` column. It was observed that games dominated the market, followed by entertainment and photo & video apps.
   - **Google Play**: The `Category` and `Genres` columns were analyzed. Family-oriented and tool apps were found to dominate, though the family category largely consisted of children’s games.

---

### 5. **Popularity Analysis**
   - **App Store**: Since install data is unavailable, the total number of user ratings was used as a proxy for popularity. Genres like social networking, navigation, and reference apps had the highest average user ratings, though the averages were often skewed by a few highly popular apps (e.g., Facebook, Waze, Bible).
   - **Google Play**: Install numbers provided a direct measure of popularity. However, these values were categorized (e.g., "1,000+", "10,000+") rather than precise, requiring adjustments for analysis.

---

### 6. **Insights and Recommendations**
   - **App Store**:
     - Practical apps (e.g., reference apps) could stand out in a market dominated by entertainment apps.
     - Developing an app with practical utility (e.g., a book app with additional features) might have strong potential.
   - **Google Play**:
     - The platform supports a more balanced mix of practical and fun apps, suggesting opportunities for diverse app profiles.
     - Categories like tools and family-oriented apps may offer significant potential due to their high representation.

---

### 7. **Validation Strategy**
   - A three-step validation approach was proposed:
     1. Launch a minimal viable product (MVP) on Google Play.
     2. Enhance the app based on user feedback.
     3. If successful, release an iOS version.

This structured strategy ensures a data-driven approach to identifying promising app profiles while minimizing risks and development costs.


In the document, both built-in system functions and user-defined functions have been used to perform tasks such as cleaning, exploring, and analyzing the data. Below is a detailed explanation of these functions, their origin (system or user-defined), and their role in the workflow:

---

### **System Functions**
These are built-in Python functions or modules used in the document:

1. **`open()`**  
   - **Task**: Open CSV files to process the datasets.  
   - **Role**: Load external data files into the program so they can be read and converted into lists.

2. **`csv.reader`**  
   - **Task**: Read the content of CSV files and convert them into lists.  
   - **Role**: Handle structured data from the datasets and make them accessible as Python lists.

3. **`print()`**  
   - **Task**: Display rows or information on the console for data exploration or verification.  
   - **Role**: Allow manual inspection of data at different stages of the process.

4. **`ord()`**  
   - **Task**: Get the ASCII value of a character.  
   - **Role**: Identify non-ASCII characters to filter out apps not intended for English-speaking audiences.

5. **`len()`**  
   - **Task**: Count the number of rows or columns in a dataset or list.  
   - **Role**: Validate the size of the data after cleaning or filtering operations.

---

### **User-Defined Functions**
These are custom functions created specifically to structure and automate parts of the analysis:

1. **`explore_data(dataset, start, end, rows_and_columns=False)`**  
   - **Task**: Explore a subset of the dataset.  
   - **Role**: Display selected rows of the dataset in an organized manner and optionally show the total number of rows and columns.  
   - **Example Use**: It was used to view the first rows of the dataset to understand its structure.

---

2. **`is_english(string)`**  
   - **Task**: Check if the name of an app is primarily written in English.  
   - **Role**: Filter out non-English apps by evaluating the characters in the app name and checking their ASCII values.  
   - **Refined Version**: Added tolerance to allow up to three non-ASCII characters (e.g., emojis or symbols).

---

3. **`freq_table(dataset, index)`**  
   - **Task**: Generate a frequency table (in percentages) for a specific column in the dataset.  
   - **Role**: Calculate the percentage distribution of categories in columns like `prime_genre` (App Store) or `Category` (Google Play).  
   - **Example Use**: Used to identify the most common app genres in both markets.

---

4. **`display_table(dataset, index)`**  
   - **Task**: Display a frequency table in descending order.  
   - **Role**: Provide a clear and organized view of the most frequent app categories, making it easier to interpret the data.

---

5. **`reviews_max`** (a dictionary)  
   - **Task**: Store the highest number of reviews for each app in the dataset.  
   - **Role**: Help remove duplicate entries by keeping only the most reliable (highest reviews) version of each app.

---

6. **`android_clean` and `already_added`** (helper lists)  
   - **Task**: Filter out duplicates and create a clean dataset for Google Play apps.  
   - **Role**: Ensure that each app appears only once, retaining the most reliable entry for each.

---

### **General Tasks of the Functions**
- **Data Exploration**:  
   - `explore_data`, `print()` were used to inspect the structure and content of datasets.

- **Data Cleaning**:  
   - Identifying errors: Manual inspection and `print()` were used to find errors.  
   - Removing duplicates: Utilized `reviews_max`, `android_clean`, and loops.  
   - Filtering relevant apps: Used `is_english` to filter non-English apps and loops to select free apps.

- **Data Analysis**:  
   - Distribution analysis: `freq_table` and `display_table` helped identify dominant app categories.  
   - Genre popularity: Calculated averages to evaluate user ratings or install counts by genre.

---

