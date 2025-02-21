# Hacker News Post


It is intended to make a brief study of the community [Hacker news](https://news.ycombinator.com/news)

### 1. Objective Definition

Through the posts as well as the type of users that make it up to know:

- Which are the most frequent posts
- Which are the most voted by the community
- Who are the users who have more relevance in the community
- What are their interventions in it.

---

### 2. Data Collection

One dataset were selected for analysis:

- Dataset with 20100 rows
- Columns: ['id', 'title', 'url', 'num_points', 'num_comments', 'author', 'created_at']

---

### 3. Data Exploration and Cleaning

- Initial exploration of the datasets was conducted to understand their structure and identify useful columns.
- Separate the name of the columns in the Dataset data into a variable.

---

### 4. Filtering and getting the average of posts

Extracting posts that refer to ask a show is possible thanks to the use of combined methods such as:

- lower()
- startswith()
- append()

Once we have separated the `Ask` of the `Show` posts into different lists, we use the function ´avg_comments()´ to obtain the percentage.

---

### 5. Titles of the highest score for Ask and Show posts

Using the `max_comment()` function it allows you to find the posts with the highest number of comments and displays the results

---

### 6. Finding the average number of Ask and Show Posts by hour created.


The function analyzes the behavior of comments based on time, returns an ordered list of times with their respective stockings and can display a readable result in human format.

---

### 7. Best times to make a post

The strategy that has been followed to determine which are the best times to upload a post, both in one group and in the other, is very simple. It is based on making an average of what are the comments spread over 24 hours, that average will be a threshold that will determine which hours are above that value and therefore will be likely to be the right ones to write or which are the ones to avoid.

---

### 8. The most relevant authors in Ask_posts and in Show post and the activity

Finally, what is done is to obtain who are those authors who have the most representation within the community and which are the publications with the most votes.

---

### System Functions:

These are built-in Python functions or modules used in the document:


### 1. `lower()`
**Task:** Convert all characters in a string to lowercase letters.

**Role:** Ensure uniformity in text by standardizing case, which is useful for tasks like searching, comparing, or formatting data without worrying about case differences. For example, converting user input to lowercase to match against predefined keys in a dictionary.

---

### 2. `startswith()`
**Task:** Check if a string begins with a specified substring.

**Role:** Filter or identify specific strings based on their starting characters or patterns. This is useful for parsing file names, URLs, or other structured text data where certain formats need to be recognized.

---

### 3. `append()`
**Task:** Add an item to the end of a list.

**Role:** Build lists dynamically by adding new elements as needed. This is helpful when processing data incrementally, such as appending rows from multiple files into a single list or adding items to a shopping cart.

---

### 4. `datetime.strptime()`
**Task:** Parse a date string (e.g., "2023-10-05") into a datetime object using a specified format.

**Role:** Convert unstructured date strings into structured datetime objects, which can then be used for calculations, comparisons, or formatting. This is essential for working with time-series data or scheduling tasks.

---

### User-Defined Functions

<br>

These are custom functions created specifically to structure and automate parts of the analysis:


### 1 . **`def avg_comments(list)`:**

<br>

- **Task**: Calculate the average number of comments across all rows in a dataset.

- **Role**: Sum the total number of comments from each row and compute the average percentage of comments per row.

- **Example Use**: It was used to analyze the average number of comments per app in a dataset of app reviews or ratings.

---

### 2 . **`def max_comments(list):`**

<br>

- **Task**:

    The function identifies the posts with the highest number of comments and prints them in descending order.


- **Role**:

    Iterates through a list of posts.

    Tracks the maximum number of comments using max_comments.

    Updates a dictionary (most_important_questions) to store posts and their comment    counts.

    Sorts the results and prints them in descending order of comment count.



- **Example Use**:

    This function is useful for analyzing social media posts, articles, or any platform where comments are tracked. It helps identify the most engaging content based on the number of comments it receives.



- **Additional Notes**:

    Modifies the global dictionary most_important_questions.

    Prints results by default, but can be adjusted to return a sorted list instead.

    The function focuses on extracting and visualizing the most relevant posts based on comment count.

---

###  3 . **`def comments_byhour(posts, output = 0)`**

<br>

- **Task**:


    - Process a list of posts to extract timestamps and comment counts.

    - Calculate the average number of comments per post for each hour.

    - Return or display the results based on the specified output format.


-  **Role**:

    The function serves as an analytical tool to understand how commenting behavior varies throughout the day. It provides insights into peak hours for comments, which can be useful for content scheduling or community engagement strategies.


- **Arguments**:


- 1 posts:

    - Type: List of posts (e.g., Ask or Show posts).

    - Description: Each post should have the following structure:
[title, author, url, points, num_comments, id, created_at]  


    - Example: posts = [[...], [...]]



- 2 output (optional):

    - Type: Integer (0 or 1).

    - Description: Determines the output format:

        0: Returns a sorted list of tuples containing hours and their average comments.

        Other value (e.g., 1): Prints formatted messages with the calculated averages.


Summary:

The function processes a list of posts to extract timestamps and comment counts. It calculates the average number of comments per post for each hour and can return or display the results in different formats. This allows users to analyze commenting behavior throughout the day.

---

###  4 .  **`threshold(data,average,selector = 1)`**

- **Task**:


    - Print a message showing the specified average.

    - Compare each entry in the dataset with the average.

    - Display entries that meet the criteria defined by the selector parameter.


-  **Role**:

The function acts as a filtering tool to identify values (hours or entries) in a dataset that are either above or below a specified average. It is useful for identifying outliers or trends in the data.



- **Arguments**:


- ### 1 **Data**:

    - **Type**: List of tuples or lists.

    - **Description**: Each entry should have at least two elements, where the second element represents the value to be compared with the average.

        Example: data = [[index0, value0], [index1, value1], ...

- ###  2 **Average**:

    - **Type**: Numeric (int or float).

    - **Description**: The threshold value used for comparison.


- ### 3 **Selector** (optional):

    - **Type**: Integer (0 or 1).

    - **Default Value**: 1.

    - **Description**: Determines the comparison logic:

        - 1: Displays entries where the value is greater than the average (>).

        - 0: Displays entries where the value is less than the average (<).




- **Return Value**:


    The function does not return any value. It prints formatted messages to the console.



- **Summary**:

The function prints a message showing the specified average and then iterates over the dataset to compare each entry's value with the average. Based on the selector parameter, it displays entries that meet the comparison criteria (either greater than or less than the average).


---

### 5 .  **`def most_relevant_authors`**

<br>

**Description**: This function analyzes a dataset of posts to identify the most relevant authors based on their posting frequency. It counts how many times each author appears in the dataset and returns a sorted list of the top authors.


- **Task**:


- Count the number of posts made by each author.

- Sort the authors based on their posting frequency.

- Return the top limit number of authors or all authors if no limit is specified.


- **Role**:

The function acts as an analytics tool to identify the most active or relevant authors in a dataset of posts. It helps in understanding which authors contribute the most to the content.


---

### 6 .  **`def all_activity_post(name, posts)`**



- Summary

    The all_activity_post feature aims to analyze the activities and posts of a specific user (name) in a list of posts. The feature prints the details of each user's post, including the title, date and time, as well as the score of the posts. In addition, it calculates and displays metrics such as the total number of posts and the average score.



- Arguments

    The function accepts two arguments:


    - **name**: A string that represents the name of the user whose activity is to be analyzed.

    - **posts**: List of tuples or dictionaries where each entry represents a post, with at least the following fields:

        - row[5]: Post author name (string)

        - row[3]: Post rating (whole number).

        - row[6]: Date and time of publication in %m/%d/%Y format %H:%M.




- **Main variables**

    Within the function, the following variables are defined:



    - **datum_format**: Format used to interpret the date and time of the post.

    - **time_format**: Format used to format the date in the output.

    - **time**: Counter for the user's total number of posts.

    - **num_points**: Variable that stores the value of row (post score).
    
    - **post_published**: Diccionario para almacenar los detalles de las publicaciones.

    - **scoring**: Accumulator for the total sum of post scores.





