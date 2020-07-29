# agilelab
1. Anagram Tester
<?php
    function anagram($first_word, $second_word)
    {
        if (count_chars($first_word, 1) == count_chars($second_word, 1)){
           return "This two strings are anagram";
        } else {
           return "This two strings are not anagram";
        }
    }
    print_r(anagram('listen','silent')."\n");
    print_r(anagram('cat','rat')."\n");
?>

2. Rewrite Pow

<?php

    function my_pow($base, $exponent) {

        $result = 1;

        for($x = 1; $x <= $exponent; $x++){
            $result *= $base;
        }   

        return $result;
    }

    echo my_pow(3,3);

?>

3 Knowledge base

3.1 SQL Injections

SQL injection is a code injection technique that might destroy our database.
SQL injection is one of the most common web hacking techniques.
SQL injection is the placement of malicious code in SQL statements, via web page input.

We should use PDO and prepared queries to prevent from SQL injection.

$conn = new PDO('mysql:dbname=dbtest;host=127.0.0.1;charset=utf8', 'user', 'password');

$conn->setAttribute(PDO::ATTR_EMULATE_PREPARES, false);
$conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

($conn is a PDO object)

$stmt = $conn->prepare("INSERT INTO tbl VALUES(:id, :name)");
$stmt->bindValue(':id', $id);
$stmt->bindValue(':name', $name);
$stmt->execute();




3.2 N+1 query

For example, lets say you have a table of Blog posts, called posts.
You can fetch all the posts in 1 SQL query (eg SELECT * FROM posts). 
Lets say this returns 100 rows of data. Now, for each post, you want to find the author of the post, so you might choose to loop over all the posts you got back from the first query and make a separate SQL query for each one (eg SELECT * FROM users WHERE user_id = ?). 
You'd end up making 100 queries to get the authors, plus 1 query to get the posts.

I suggest to use laravel PHP framework for N+1 query


3.3 === vs ==
== is check need to be same value 
=== is check need to be same value and same type also.


3.4 Server Variable
<?php
echo $_SERVER['PHP_SELF'];
echo "<br>";
echo $_SERVER['SERVER_NAME'];
echo "<br>";
echo $_SERVER['HTTP_HOST'];
echo "<br>";
echo $_SERVER['HTTP_REFERER'];
echo "<br>";
echo $_SERVER['HTTP_USER_AGENT'];
echo "<br>";
echo $_SERVER['SCRIPT_NAME'];
?>


3.5 Test Unit / Unit Testing
UNIT TESTING is a type of software testing where individual units or components of a software are tested. The purpose is to validate that each unit of the software code performs as expected. Unit Testing is done during the development (coding phase) of an application by the developers. Unit Tests isolate a section of code and verify its correctness. A unit may be an individual function, method, procedure, module, or object.

In SDLC, STLC, V Model, Unit testing is first level of testing done before integration testing. Unit testing is a WhiteBox testing technique that is usually performed by the developer. Though, in a practical world due to time crunch or reluctance of developers to tests, QA engineers also do unit testing.


4. First I listen to customers what they mean about the issues. And then I apologize to them if the issues happen.
And then I solve the problems for quickly. 


5. I'll make sure check for the old project what programming language use, what concepts and what method are using.
When I facing some problems for the new features I will search on Google.
