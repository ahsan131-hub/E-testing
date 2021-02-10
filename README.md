#E-Testing
***
    A modern way of taking and creating e-quizzes.
***

### Why did I make E-Testing?
    As it is the 2nd wave of the pandemic in Pakistan, every one has switched to working from home, classes are held online 
    as well as the tests and exams so I decided to make my contribution by creating E-Testing.
    E-Testing saves time and is easy to use for testing purpose on a web-based platform.
    
    
#### How my project is different from others in this course?
     All the other projects that I have done so far in this course, were simple or one can say they were not that much 
     complex, as they were to design a webpage, design a networking and/or communication websites, like mail, Wiki, 
     Search etc and were a little less complex unlike Capstone. I tranferred json formatted data, included a timer that 
     was not so easy to mention. Besides that, I have also used SQL database in this project created in models.py
     that was somethimng different than the previous projects of this course. In addition to that, this web page is 
     more user-friendly, having a better GUI than the previous ones.
      
      
###Functionality of my project:
E-Testing is a web-based platform where a user can perform the following tasks:
* Registering or logging in with the previously registered IDs
* Creating a quiz
* Creating a new category for the questions to add in
* Specifying the date, time, and time limit for the attempt of the quiz by other users
* Creating and adding new questions to the quiz
* Attempting the quiz (on the date and within the time limit specified by the creator of the quiz)
* Reviewing their attempted quizzes, correct options in case they selected wromng previously and their score
* Seeing the names of the users who have attempted the quiz created by them, and seeing who passed/failed       


### **Implementation (what my files are and what they contain)**
    I have used Javascript python Html and CSS. and the i have used the Django for the backend of the my applicaation javascript
    for the frontend. after creating the project with the name of the Capstone i created the applcation with name of the E-testing 
    and the entry point to run the Application is the file manage.py. and the django have by default bunch of the files i have manupulated 
    following files:
    
* **models.py** 
  In model.py file I have created the database for my application which includes following table:
  * **User** stores the name of the users
  * **Question** used to store the information of the Questions' data, for example statements, options, correct option.
  * **Quiz** used to store information for Quiz, like the Question, total score and availability time for the quiz etc.
  * **Question_result** stores the result of each particular quiz attempted by the particular user.
  * **Quiz_attempts** stores the information of the quiz result e.g.status, how many questions were attempts
  * **Profile** stores quizzes created by the user and number of the quizzes attempted by them.
  
* **views.py**
    In this python file, I have coded all the backend logic used to manipulate the data. I have created some following methods
    * **creation** This method is called when user clicks on the link in the navbar to create quiz and question. It renders the quiz  
      with the Pagination, 9 quizzes on each page.
    * **create_quiz** on creation.html, when the user clicks the "create quiz" button, this method is called to  
      create the quiz and save it to the database as well.
    * **add_question_quiz** if you click on the "add question to quiz" then this method is called to takes the question id as an argument 
      of the method and add the question into a particular quiz.
    * **create_question** when user fills the field with the create question label, and clicks on the button add question then this method submits the form having 
      bunch of the fields and create the question. Every question have its unique id.
    * **my_profile** when user clicks the username button on the nav bar, this method is called, renders a page by taking all 
      quizzes created by current user and in the reverse order so that last created quiz should come on top.
    * **evaluation** This method is called when user clicks the evaluate button to evaluate that particular quiz. This method then renders
     a page with Quiz_attempt and question_result which stores all the information of the attempt of the quiz.
    * **view_all_quiz** this method is used to render the page with all quizzes available in the database reagardless whether user has  
      already attempted the quiz or not.
    * **attemp_quiz** this method is called when user clicks on the attempt quiz button. This method does two things; it renders the page with all  
      questions, and here I used **Javascript** to check whether the answer is right and wrong. It then submits to the 
      database  and then this method is again redirected with the result of last attempted questions.
    * **review_my_quiz** this method is called when you click on the review button, it renders a page with user Question_attempt which was saved while user  
      attempted the question and it also renders the result of each question.
    * **save_question_result** this method is used to save the answer of each question.
    * **view_all_questions** this method renders page with all the questions and with the list of the category.
    * **show_relevant_question** when user selects the question category in show_all_question, this method renders the
      question with the selected category.
    * **login_view** this is called the when the user logs in .
    * **logout_view** this when the user logs out
    * **register** when the user clicks on the register button, this methd is used to register the new user.
    
* **eTesting/Templates**
    In this package I have the all my html files that are used to manipulate the frontend of the webpages and manage 
    their structure, their backend code is inside the methods by the names, same as the following files inside views.py.
    Each html page renders a specific page which is used for a specific function. All the files and their main 
    functionality are described as follows:
    * **viewAllQuiz.html** This is the entry page where you will see all the quizzes displayed with the attempt button. 
    Pagination is also used here as well, to make user-friendly and to make it easy to use . 
    * **creation.html** used for the interface for the creation of new quizzes and questions. 
    * **evaluation.html** used for seeing who has attempted your quizzes and who has passed/failed.
    * **index.html**  this file is used for attempting the quiz, it shows all the questions with their options.
    * **layout.html** this page defines the layout of the all pages.
    * **login.html**  used for logging in.
    * **message.html** used to display the message "Time UP!!" when time of the quiz is up while attempting.
    * **myProfile.html** used to show all the quizzes created by the user.
    * **questions.html** used to show all the questions that can be added in the quiz. Also, includes fields for 
    finalizing the quizzes like giving time, score and passing score etc.
    * **register.html** used to register the new user.
    * **review.html** used to display the result of quiz.
    * **viewAllQuestions.html** This will show all of the questions. Pagination is also used so to make it user-friendly 
    and to ensure ease of use.
