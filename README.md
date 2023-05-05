Download Link: https://assignmentchef.com/product/solved-dsc-450-database-processing-for-large-scale-analytics-assignment-4
<br>
<strong> </strong><strong>Part 1. Python (15 points)</strong>

<strong> </strong>

We are going to work with a small extract of tweets (about 200 of them), available on D2L as Tweet1_Assignment4.txt




Create a SQL table to contain the following few attributes of a tweet:

“created_at”, “id_str”, “text”, “source”, “in_reply_to_user_id”, “in_reply_to_screen_name”, “in_reply_to_status_id”, “retweet_count”, “contributors”. Please assign reasonable data types to each attribute (e.g., VARCHAR(10000) is a bad idea).




Use SQLite for this assignment.




<strong>NOTE 1</strong>: I do not recommend trying to copy-paste this text, because there is absolutely no knowing what might come out from paste on your system. You should download the Tweets1_Assignment4.txt file.

<strong> </strong>

<strong>NOTE 2</strong>: The input data is separated by a string “EndOfTweet” which serves as a delimiter. The text itself consists of a single line, so using readlines() will still only give you one row which needs to be split by the tweet delimiter.




<strong>NOTE 3:</strong>  Do not forget that you can use json.loads(OneTweetString.decode(‘utf8’)) to parse a tweet entity into a python dictionary. Don’t forget to add import json to your code.

<strong><u> </u></strong>

<strong>NOTE 4:</strong> Make sure your python code reads through the file and loads the data properly (including NULLs).




Write the following SQL queries:




<ol>

 <li>Count the number of iPhone users and android users. (based on “source” attribute)</li>

</ol>




<ol start="2">

 <li>Count the number of tweets with users who are not replying (“in_reply_to_user_id” is NULL).</li>

</ol>




Submit your Part1.py Python file. No need to submit JSON libraries.
















<strong>Part 2. Regex (15 points)</strong>

The Chicago.txt is the Wikipedia entry on Chicago available from <a href="https://en.wikipedia.org/wiki/Chicago">https://en.wikipedia.org/wiki/Chicago</a>. Chicago.txt is a bit outdated but follows the general heading section. Use Python regular expression library to find the following patterns in Chicago.txt:




<ol>

 <li>Count the number of sections in this text. Note sections begin with ‘[edit]’.</li>

 <li>In the Crime section, report all the years mentioned in sorted (ascending) order.</li>

 <li>Find all county names used in this Wikipedia article.</li>

</ol>




Submit your Part2.py Python code.

<strong> </strong>

<strong>Part 3.</strong> <strong>Comprehensive</strong> <strong>(25 points)</strong>

Now use a larger collection of tweets. Download Tweet2_Assignment4.txt. The tweets are all on separate lines, but <u>some of the tweets are intentionally damaged and will not parse properly</u>. You will need to store these tweets in a separate “error” file.




Write python code that is going to read and load the Tweet2_Assignment4.txt. file. For tweets that could not parse, simply store them in Assignment4_errors.txt file




Note1. :  Gracefully catch JSON errors.




Note2: As discussed in class, you can access the contents of the user dictionary after it was parsed by json like this:

dict[‘user’]   # user dictionary

dict[‘user’][‘id’]  # user’s ID




For tweets that parsed, create a new SQL table for the user dictionary. It should contain the following attributes “id”, “name”, “screen_name”, “description” and “friends_count”. Modify your SQL table from Part 1 to include “user_id” which will be a foreign key referencing the user table.

and populate both of your tables (Tweet table from Assignment4 and User table from this assignment), with data from Tweet2_Assignment4.txt.




<ul>

 <li>Write and execute a SQL query to do the following:  Find the user (“id” and “name”) with the highest “friend_count” in the database</li>

</ul>




<ul>

 <li>Write python code that is going to perform the same computation (find the user with the highest “friend_count”)</li>

</ul>




<ul>

 <li>Write and execute SQL query to do the following: Find the tweets without associated user id entry.</li>

</ul>




<ul>

 <li>Write python code that is going to perform the same computation as 3-c. (Requires Python DataFrames)</li>

</ul>




<ul>

 <li>Using Python, identify the top-3 most frequent terms (i.e. words separated by ‘ ‘) in the text of the tweets. It is up to you whether you prefer to use the contents of the loaded database (reading tweets from SQLite, which contains fewer tweets) or the contents of the original Tweet2_Assignment4.txt file (reading tweets directly from the file).</li>

</ul>










Submit Part3.py Python code.




<strong>Part 4.</strong> <strong>SQLAlchemy (10 points)</strong>




Perform PART1 using SQLALchemy. So the table within SQLite should be created using SQLAlchemy and data inserted into the table using pre-compiled statements from SQLAlchemy.




Then use SQLAlchemy to write the queries. You must determine how to filter NULLs in SQLAlchemy.




Submit Part4.py. No need to submit supporting libraries.