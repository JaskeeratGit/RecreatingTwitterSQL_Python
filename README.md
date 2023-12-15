# RecreatingTwitterSQL_Python
Recreating twitter with simple terminal menu interface by integrating SQL in python.

DataBase Specifications: (schema)
users(<ins>usr</ins>,pwd, name,email,city,timezone)\n
follows(<ins>flwer</ins>,<ins>flwee</ins>,start_date)\n
tweets(<ins>tid</ins>tid,writer,tdate,text,replyto)\n
hashtags(<ins>term</ins>)\n
mentions(<ins>tid</ins>,<ins>term</ins>)\n
retweets(<ins>usr</ins>,<ins>tid</ins>,rdate)\n
lists(<ins>lname</ins>,owner)\n
includes(<ins>lname</ins>,<ins>member</ins>)\n

Login Screen
The first screen should provide options for both registered and unregistered users. There must be also an option to exit the program. Registered users should be able to login using a valid user id and password, respectively referred to as usr and pwd in table users. After a registered user signs in, the system should list all tweets or retweets from users who are being followed; the tweets should be ordered based on date from the latest to the oldest. If there are more than 5 such tweets, only 5 would be shown and the user would be given an option to see more but again 5 at a time. The user should be able to select a tweet and see some statistics about the tweet including the number of retweets and the number of replies. Also the user should be able to compose a reply to it (see the section on composing a tweet), or retweet it (i.e. repost it to all people who follow the user).

Unregistered users should be able to sign up by providing a name, email, city, timezone and password. The user id (i.e. the field usr in table users) should be provided by the system and be unique. After a successful login or signup, users should be able to perform the subsequent operations (possibly chosen from a menu) as discussed next.

System Functionalities
After a successful login, users should be able to perform all of the following tasks.

Search for tweets. The user should be able to enter one or more keywords and the system should retrieve every tweet that match at least one of the keywords. A tweet matches a keyword if (1) the keyword has the prefix # and it is mentioned by the tweet as a hashtag in mentions table, or (2) the keyword doesn't have the prefix # and it appears in the tweet text. (The symbol # is not part of any keyword and only indicates that the keyword that follows is expected to appear as a hashtag. Also tweets can have hashtags (in mentions table) which do not explicitly appear in the tweet text.) The tweets should be ordered based on date from the latest to the oldest. If there are more than 5 matching tweets, only 5 would be shown and the user would be given an option to see more but again 5 at a time. The user should be able to select a tweet and see some statistics about the tweet including the number of retweets and the number of replies. Also the user should be able to compose a reply to a tweet (see the section on composing a tweet), or retweet it (i.e. repost it to all people who follow the user).
Search for users. The user should be able to enter a keyword and the system should retrieve all users whose names or cities contain the keyword. The result would be sorted as follows: first, all users whose name match the keyword would be listed and these users would be sorted in an ascending order of name length. This would be followed by the list of users whose city but not name match the keyword and this result would be sorted in an ascending order of city length. If there are more than 5 matching users, only 5 would be shown and the user would be given an option to see more but again 5 at a time. The user should be able to select a user and see more information about him/her including the number of tweets, the number of users being followed, the number of followers and up to 3 most recent tweets. The user should be given the option to follow the user or see more tweets.
Compose a tweet. The user should be able to compose a tweet. A tweet can have hashtags which are marked with a # before each hashtag. Information about hashtags must be stored in tables mentions and if needed in hashtags.
List followers. The user should be able to list all users who follow them. From the list, the user should be able to select a follower and see more information about the follower including the number of tweets, the number of users being followed, the number of followers and up to 3 most recent tweets. The user should be given the option to follow the selected user or see more tweets.
Logout. There must be an option to log out of the system. 
String matching. Except the password which is case-sensitive, all other string matches (including searches for tweets and users) are case-insensitive. This means the keyword "edmonton" will match Edmonton, EDMONTON, and EdMoNton, and you cannot make any assumption on the case of the strings in the database. The database can have strings in uppercase, lowercase or any mixed format.

SQL injection attacks and password entry. You are expected to counter SQL injection attacks and make the password non-visible at the time of typing.

Error checking.
