# Owasp Top 10

###  Open `Web Application` Security Project

<br>

> #### A1: Injection

<img src="https://www.researchgate.net/profile/Ali-Fathi-Sawehli/publication/330934873/figure/fig2/AS:723707425198080@1549556704159/SQL-injection-process-Pantheon-2017.ppm">
<br>
Refer the Image For the Actual Post from where it is taken
<hr>


<b> What is it ? </b>
#### `#Explanation`

Different Types of Explanation
- User input is taken directly and then evaulted as system, sql/nosql command.
- A User making use of some specially crafted URL query/Post Payload to interact with the SQL/NoSQL Database, OS, LDAP etc. via the Front facing Application (Generally a Web Application)



<b> Examples </b>
Using Input in Username as `' or 1=1 -- -`
<details>
    <summary>
        How it works in this case then ?
    </summary>

    A Typical Example, over here we are talking about SQL Injection
    On the Server Side the Code is as Follows

    The below code is kindof the worst code, but generally as per what i know, a select command is fired and the result count check is done so if their is a user with that password in database then the count will return 1 else 0.
    -- 
    <?php
        $db_conn = database_conn(); // We are not interested in how it is implemented
        $user_name = $_GET['user_name'];
        $pass_word = $_GET['pass_word'];
        // No Sanitization, No Checking any input is accepted
        $sql_query  = "SELECT count(*) FROM users_table WHERE username = '$user_name' and password = '$pass_word'";
        $user_exists = check_if_user_exits($db_conn, $sql_query);
        if ($user_exists) {
            // Login etc etc.... Code, We are not conserned about it
        }
    ?>
    -- 

    Over here when the user does the above as input in user name
    the `$sql_query` command looks like this:
    SELECT count(*) FROM users_table WHERE username = '' or 1=1 -- -' and password = '$pass_word'
    When you run this command on your own using php you will see you results.
    Over here the attacker has privlidge to even add `limit 1` to get the count as 1
    [To Be Added]
<br>


</details>
<br>

<b> Types </b>
- SQL / NoSQL Injection
- LDAP Injection
- OS Injection

<b> Mitigation </b>
- Sanitization on Both Client as well as Server Side
    - Because Client Side (Javascript Validation & Sanitization) can be easily Bypassed.
- Source Code Review 
    - It is very Important to do a White Box Testing uncover areas and places where the Injection could happen later at some time.
    - Thorough automated testing of all parameters, headers, URL, cookies, JSON, SOAP, and XML data inputs
- Use Predefined Language Specific Injection Defense
    - Using Prepared Statement in Java


<b> Final Thoughts </b>



<b> How to Get hands-on Practical </b>


<b> Research, Important Links </b>

> #### A2: Broken Authentication

<b> What is it ? </b>
#### `#Explanation`

<b> Examples </b>


<b> Types </b>


<b> Mitigation </b>


<b> Final Thoughts </b>


<b> How to Get hands-on Practical </b>


<b> Research, Important Links </b>

> #### A3: Sensitive Data Exposure

<b> What is it ? </b>
#### `#Explanation`

<b> Examples </b>


<b> Types </b>


<b> Mitigation </b>


<b> Final Thoughts </b>


<b> How to Get hands-on Practical </b>


<b> Research, Important Links </b>


> #### A4: XML Xternal Entity [XXE] Injection

<b> What is it ? </b>
#### `#Explanation`

<b> Examples </b>


<b> Types </b>


<b> Mitigation </b>


<b> Final Thoughts </b>


<b> How to Get hands-on Practical </b>


<b> Research, Important Links </b>

> #### A5: Broken Access Control

<b> What is it ? </b>
#### `#Explanation`

<b> Examples </b>


<b> Types </b>


<b> Mitigation </b>


<b> Final Thoughts </b>


<b> How to Get hands-on Practical </b>


<b> Research, Important Links </b>



> #### A6: Security Mis-Configuration

<b> What is it ? </b>
#### `#Explanation`

<b> Examples </b>


<b> Types </b>


<b> Mitigation </b>


<b> Final Thoughts </b>


<b> How to Get hands-on Practical </b>


<b> Research, Important Links </b>



> #### A7: Xross-Site Scripting [XSS]


<b> What is it ? </b>
#### `#Explanation`

<b> Examples </b>


<b> Types </b>


<b> Mitigation </b>


<b> Final Thoughts </b>


<b> How to Get hands-on Practical </b>


<b> Research, Important Links </b>


> #### A8: Insecure De-Serialization

<b> What is it ? </b>
#### `#Explanation`

<b> Examples </b>


<b> Types </b>


<b> Mitigation </b>


<b> Final Thoughts </b>


<b> How to Get hands-on Practical </b>


<b> Research, Important Links </b>



> #### A9: Using Components with Known Vuln


<b> What is it ? </b>
#### `#Explanation`

<b> Examples </b>


<b> Types </b>


<b> Mitigation </b>


<b> Final Thoughts </b>


<b> How to Get hands-on Practical </b>


<b> Research, Important Links </b>


> #### A10: Insufficent Logging & Monitoring

<b> What is it ? </b>
#### `#Explanation`

<b> Examples </b>


<b> Types </b>


<b> Mitigation </b>


<b> Final Thoughts </b>


<b> How to Get hands-on Practical </b>


<b> Research, Important Links </b>

