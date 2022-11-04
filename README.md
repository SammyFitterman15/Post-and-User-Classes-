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


readPost Function: 
- this fucntion fills an array of Post obejcts 
- In part one this is a standalone function, in part two it is implemented as a member function of Buffchat class 
-  readPost takes in four parameters as a standalone function: the file name which it reads in, an array of posts, the number of posts stored, and the size of the array 
-  This function utilizes a helper function split that populates an array based on a delimeter and splits up the line/string between each delimeter and returns the amount of times it split the string 
-  readPosts returns the number of post objects stored in the array 

printPostByYear Function: 
- this fucntion prints all posts in the given array of posts that were posted during a given year
- In part one this is a standalone function, in part two it is a member function of buffchat class 
- It takes three parameters an array of posts, a string for the year in question and a the number of posts stored in the array 
- The readPost function is used to populate arrays of posts objects inorder to test this function 

readLikes Function:
 - this functions fills an array of User objects and their likes for Posts 
 - Each line in the file used to fill the array consists of a username followed by a sequence of likes, each line corresponds to a single user object 
 - In part one this is a standalone function and in part two it is a member function of the buffchat class 
 - There are four parameters: the file name to be read in, an array of user objects, the number of users stored, the capacity of the users array, and the maximum amount of likes stored on each line in the file ie the number of posts available to the user, the number of likes on a given line can be less than max posts available to the user but will never exceed the maximum size of the likes array which is 50
 - This function also uses the same helper function split used in readPost 
 - Each line is split to populate a likes array and create a user object 
 - readLikes returns the number of user objects stored in the array 

getLikes function: 
- This function, given a lists of users, returns the number of times a given user has likes a post by a given author 
- This function finds the first post in the posts array by the author 
- This is a standalone function in part 1 and in part two is a member function of the buffchat class 
- The function has 6 parameters: a post author in question, a posts array, the number of posts stored, the username in question, an array of user objects, and the number of users stored 
- A username search is case sensitive 
- The function behavior is as follows: 
- returns the value of likes from the user for post posted by a post author 
- returns -3 if the user  or the post author are not found in the arrays 
- returns -2 if the number of users or number of posts stored are less than or eqaul to 0

fingTagUser function: 
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

