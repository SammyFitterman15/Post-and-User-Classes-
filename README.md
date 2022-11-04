# Post-and-User-Classes-

This Project combines a post class and user class to create a BuffChat app that allows users to interact with both post and user objects. In part one the User and Post classes are implemented and standlone functions are created to manipulate class objects. In part two the functions are implemented as Buffchat member functions. 


Post class: 
- Four data members: a string for the body of post, a string for the post author, an integer for amount of like, and a string for the date 
- Each date member has a getter and setter member function 
- There is both a default constructor that sets all the strings to empty and the number of likes to 0 and a parameterizerd constructor

User class: 
- Four data members: a string for the username, an array of integers for the likes, an integer for the amount of posts, and a constant integer for the size of the array which is 50
- Each data member has a getter and setter member function 
- getLikesAt gets the number of likes at a specific post id in the array and returns -2 if the post id inputed is less than 0 or larger than the size of the likes array 
- setLikesAt takes in a specific post id and the number of likes to set at the given index, the number of likes must be between -1 and 10 and the post id must be greater than 0 and not exceed the size of the likes array 
- There is a default constructor that sets the username to an empty string and all the elements of the likes array to -1 meaning that the user has not viewed any posts 

The connection of the Post and User class: 
- The index of the of the post in the post array is the index of the amount of likes in the likes array of each user 
- In the likes array of the user a -1 means they have not viewed the post at that index, a 0 means they have not liked it and any number 1-10 is the number of likes they gave to that post 


int readPost Function: 
- this fucntion fills an array of Post obejcts 
- In part one this is a standalone function, in part two it is implemented as a member function of Buffchat class 
-  readPost takes in four parameters as a standalone function: the file name which it reads in, an array of posts, the number of posts stored, and the size of the array 
-  This function utilizes a helper function split that populates an array based on a delimeter and splits up the line/string between each delimeter and returns the amount of times it split the string 
-  readPosts returns the number of post objects stored in the array 

void printPostByYear Function: 
- this fucntion prints all posts in the given array of posts that were posted during a given year
- In part one this is a standalone function, in part two it is a member function of buffchat class 
- It takes three parameters an array of posts, a string for the year in question and a the number of posts stored in the array 
- The readPost function is used to populate arrays of posts objects inorder to test this function 

int readLikes Function:
 - this functions fills an array of User objects and their likes for Posts 
 - Each line in the file used to fill the array consists of a username followed by a sequence of likes, each line corresponds to a single user object 
 - In part one this is a standalone function and in part two it is a member function of the buffchat class 
 - There are four parameters: the file name to be read in, an array of user objects, the number of users stored, the capacity of the users array, and the maximum amount of likes stored on each line in the file ie the number of posts available to the user, the number of likes on a given line can be less than max posts available to the user but will never exceed the maximum size of the likes array which is 50
 - This function also uses the same helper function split used in readPost 
 - Each line is split to populate a likes array and create a user object 
 - readLikes returns the number of user objects stored in the array 

int getLikes function: 
- This function, given a lists of users, returns the number of times a given user has likes a post by a given author 
- This function finds the first post in the posts array by the author 
- This is a standalone function in part 1 and in part two is a member function of the buffchat class 
- The function has 6 parameters: a post author in question, a posts array, the number of posts stored, the username in question, an array of user objects, and the number of users stored 
- A username search is case sensitive 
- The function behavior is as follows: 
- returns the value of likes from the user for post posted by a post author 
- returns -3 if the user  or the post author are not found in the arrays 
- returns -2 if the number of users or number of posts stored are less than or eqaul to 0

void fingTagUser function: 
- this functions prints all the users with a given tag included in their username
- This function has three parameters: username tag in question, an array of user objects and the number of users stored
- This username tag search is case sensitive 
- This is a void function and does not return anything, it prints out all the users containing the tag in question 


Part 1 Menu: 
- The post class and User class are combined with the standalone functions to create a menu with 6 options 
- 1. Calls the readPost function 
- 2. Calls the printPostByYear function 
- 3. Calls the readLikes function 
- 4. Calls the getLikes function 
- 5. Calls the fingTagUser function 
- 6. Quits the menu 

- The menu runs on a loop continually offering the user options until they quit 


Utilize the posts.txt and users.txt files to test the functions
*Note you need to call readPost and readlikes before the other functions can be called because they utilize arrays of user and post objects 

Part one contains all the following files: 
- Post.h
- Post.cpp
- postDriver.cpp
- readPostsDriver.cpp
- printPostsByYear.cpp
- User.h
- User.cpp
- userDriver.cpp
- readLikesDriver.cpp
- getLikesDriver.cpp
- findTagUserDriver.cpp
- project2pt1.cpp


Buffchat Class: 
- Data members:
  - const static integer for the size of the post array (50)
  - const static integer for the size of the users array (50)
  - An array of posts objects 
  - An array of users objects 
  - the number of posts stored in the database
  - The number of users stored in the datebase 
- Member functions:
   - A getter function for the number of posts, the number of users, and the size of the post and user arrays 
   - int readPost is implemented as a member function with only one paraemeter for the file to be read in 
   - int readLikes is implemeneted as a member function with one one parameter for the file to be read in
   - void printPostByYear is implemented as member function with only one parameter for the year in question 
   - int getLikes is implemented as a member function with only two parameters for the username and post author in question
   - void findTagUser is implememneted as a member function with only one parameter for the username tag in question 
   - A new bool function addPost is implemented in the Buffchat class, takes three parameters a post body, a post author and a post date (all strings) 
   - A new void function printPopularPosts is implemented in the Buffchat class, takes in an integer for the number of posts to print for a given a year and a string for the year in question 
   - A new User function findLeastActiveUser is implemented in the Buffchat class, takes no parameters and returns a User object 
   - A new integer function countUniqueLikes in implemented in the Buffchat class, takes in one parameter for the post author in question and returns the number of users who likes the posts posted by the author
     
     
bool addPost function:
 - Takes in three strings (post body, post author and date respectively) and adds a post to the post array at the last index 
      - The post is added to the first unused position in the posts array 
      - The number of likes for the new post object will be set to 0
      - The values in the likes array for the this post will be set to -1 meaning the user has not viewesd this new post 
- The function behavior matches as follows:
      - returns false if the post array is full 
      - Returns true if the post is succesfully added to the array 

void printPopularPosts function:
- This functions prints the requested number of posts with the highest likes for the given year
- The functions accepts 2 parameters: the number of posts to be pritned and the year in question 
- The function matches the following behavior:
   - If the number of posts stored in the array is 0 or less than 0 the function prints "No posts are stored" 
   - If there is no post matching the given year the function prints "No posts stored for year <year>"
   - If there are at least the requested number of posts to be printed matching the given year, the function prints "Top <num of posts> posts for year <year>" followed by each post (number of likes: content of post) on a new line
   - If there are less than the requested number of posts matching the given year the function prints "There are fewer than <num of posts> for year <year>. Top <actual number of posts found> posts for <year>" followed by each post (number of likes:content of post) on a new line. Only the top posts are printed and in order of how they appear in the post array 
 

User findLeastActiveUser function:
 - This member function for the Buffchat class finds the least active user and returns that user object
 - Activity is recored by the amount of posts a user has liked, an entry of -1 in the likes array means the user has not viewed the post at that index 
 - The function takes no parameters 
 - The function behavior matches the following:
   - Returns an empty User object if there are no users stored in the database 
   - Returns the user with the least activity recoreded in the database
 - The user with the least activity is determined by the one who has the most -1 entries in their likes array 
 
 
int countUniqueLikes function:
 - This function returns the number of users who likes the posts posted by the author in question, each user can like the same post a maxiumu of 10 times 
 - The function accepts one parameter for the post author in question 
 - Each post a user has liked by the post author if they have mulitiple posts counts towards the unique likes 
 - The functions behavior matches the following: 
    - Returns the number of unique likes recieved across all the posts posted by the author in question 
    - Returns 0 if no user has liked their posts 
    - Returns -1 if no user has viewed their posts
    - Returns -2 if the posts array or the users array is empty 
 

 
Part 2 Menu: 
 - This menu combines the Post and User class through the Buffchat class and gives the user 10 options 
- 1. Calls the readPosts function 
- 2. Calls the printPostByYear function
- 3. Calls the readLikes function 
- 4. Calls the getLikes function
- 5. Calls the findUserTag function
- 6. Calss the addPost function 
- 7. Calls the printPopularPost function 
- 8. Calls the findLeastActiveUser function 
- 9. Calls the findUniqueLikes function
- 10. Quits the loop 
 
*Utilize the posts.txt and users.txt files to test the functions
*Note you need to call readPost and readlikes before the other functions can be called because they utilize arrays of user and post objects 
 

Part two contains all the following files: 
- Post.h (from Project 2 Part 1)
- Post.cpp (from Project 2 Part 1)
- postDriver.cpp (from Project 2 Part 1)
- User.h (from Project 2 Part 1)
- User.cpp (from Project 2 Part 1)
- userDriver.cpp (from Project 2 Part 1)
- Buffchat.h
- Buffchat.cpp
- buffchatDriver.cpp
- project2pt2.cpp
