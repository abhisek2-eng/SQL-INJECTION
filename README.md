
![sql-injection-logo](https://user-images.githubusercontent.com/84139300/187015622-0f3bf6d6-ba58-4654-bf99-ec7363e66864.jpg)

What is sql injection ?
= SQL injection (SQLi) is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database.
yedi web application ma sql vulneribility xa vane sql injection ko use gari hamro target ko information normally aru le herna nasakne information haru hami sql injection ko help le attack garera nikalna sakxau.
sql injection ko help le hami le web application ma code inject garera user ko data modify garne ani data haru delete garna pani sakxau sathai content haru pani change garna sakxau
ani yes ko help le hamile dos attack pani web application ma perform garna sakxau.


What is SQL injection (SQLi)?
SQL injection (SQLi) is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database. It generally allows an attacker to view data that they are not normally able to retrieve. This might include data belonging to other users, or any other data that the application itself is able to access. In many cases, an attacker can modify or delete this data, causing persistent changes to the application's content or behavior.

In some situations, an attacker can escalate an SQL injection attack to compromise the underlying server or other back-end infrastructure, or perform a denial-of-service attack.


What is the impact of  SQL injection attack?
= SQL injection attack helps to get unauthorized access to sensitive data, such as passwords, credit card details, or personal user information leading to reputational damage of any organization or groups.

Examples of SQL injection :

1) retrival of hidden data = 
suppose euta shopping garne websites xa jas ma giftharu xa ani  hamile category ma gift ma click gare paxi browser le url lai request garxa 
ani something  https://shopping-website.com/products?category=Gifts yesto url open hunxa.
This causes the application to make an SQL query to retrieve details of the relevant products from the database:
= SELECT * FROM products WHERE  category = 'Gifts' AND released = 1
yesle chai websites lai database return garna request garxa

aba yedi websites sql injection vulnereble xa vane attacker le yesto injection halera https://shopping-website.com/products?category=Gifts'--

This results in the SQL query :

SELECT * FROM products WHERE category = 'Gifts'--' AND released = 1

'-- = ani -- (hyfen) chahi common indicator ho SQL ma

 released = 1 vaneko chahi yesle hidden data ani sabai  products haru display gardinxa including released navako products.

ani aba attacker can cause the application to display all the products in any category, including categories that they don't know about:
using this url or injection :https://shopping-website.com/products?category=Gifts'+OR+1=1--

This results in the SQL query:

SELECT * FROM products WHERE category = 'Gifts' OR 1=1--' AND released = 1

The modified query will return all items where either the category is Gifts, or 1 is equal to 1. 
 1=1 is always true, the query will return all items now.

so aba yo chahi hami practical garna burp suite chahinxa burpsuite hami burp suite batw intercept gari tes ko request haru modify garne ani product category filter sets gari  parameter lai change garera '+OR +1=1-- yo value add gardine ani request lai submit gardine ani hami le response lai verify garera  aru kei chij vayera aako dekhna sakinxa   

aba voli ko toipc chahi (Subverting application logic) hune xa rw voli yesko barema sab explain garne xu
