# Logbook
| Date | Used Hours | Subject(s) | Output |
| :-------- | :-------: | :--------- | :---------    |
| 17.01.2025 | 2 | kick-off lecture | Lecture recording |
| 23.01.2025 | 2 | kick-off lecture | Lecture recording |
| 24.01.2025 | 2 | Cisco 1-3 | module exam |
| 25.01.2025 | 2 | Cisco 4,5,exam | module exam |
| 30.01.2025 | 2 | Lab: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data <br> Lab: SQL injection vulnerability allowing login bypass <br> Lab: Username enumeration via different responses  <br> Lab: 2FA simple bypass | I struggled to get used to Burp Suite operations. However, I learned how SQL injection can manipulate queries to reveal hidden data by modifying parameters. <br> I didn't know that it's possible to log in as an administrator using SQL injection like this. It was an insightful experience to understand how easily such vulnerabilities can be exploited. <br> I learned how username enumeration and password brute-forcing work together in an attack. Identifying the valid username first makes the brute-forcing process much more efficient. <br> I learned how to bypass two-factor authentication by manipulating the URL, accessing the account page without needing the verification code. This showed how URL manipulation can sometimes bypass security measures. |
| 31.01.2025 | 2 | Lab: Unprotected admin functionality <br> Lab: Unprotected admin functionality with unpredictable URL <br> Lab: SQL injection attack, querying the database type and version on Oracle <br> Lab: Password reset broken logic  | I learned how to access the admin panel through the robots.txt file and delete a user. It showed the importance of securing admin pages properly. <br> In this lab, I struggled to find the URL for the admin panel. Eventually, I discovered it in the html file. It taught me the importance of inspecting the source code to find hidden links. <br> In this lab, I learned how to exploit a SQL injection vulnerability using the UNION attack. I used it to retrieve the database version and practice SQL injection techniques for security testing. <br> The instructions said to remove the token, but it actually had to be kept. This taught me that understanding how the system truly works is key to solving the lab.|
| 08.02.2025 | 4 | Lab: User role controlled by request parameter <br> Lab: User role can be modified in user profile <br> Lab: User ID controlled by request parameter <br> Lab: Username enumeration via subtly different responses | In this lab, I learned how to change cookies to access the admin panel. Every time I sent a request, the server set Admin=false, so I had to change it to Admin=true again. After that, I accessed /admin and deleted Carlos. <br> At first, I made a mistake because I forgot to add a comma when adding "roleid": 2 to the request. The server did not accept my request. After fixing it, I successfully changed my role to admin, accessed /admin, and deleted Carlos. <br> Using Burp Suite, I could change "id" to "carlos" and accessed his account. I got his API key and solved the lab. This showed weak access control. <br> In this lab, I struggled to find the subtly different error messages. Eventually, I realized I had to focus on small differences, such as period, to identify the valid username. It was a challenging but rewarding exercise.|
| 12.02.2025 | 2.5 | Lab: User ID controlled by request parameter, with unpredictable user IDs <br> Lab: User ID controlled by request parameter with data leakage in redirect <br> Lab: User ID controlled by request parameter with password disclosure | I learned how to exploit a horizontal privilege escalation vulnerability by manipulating user IDs in the URL to access another user's data. <br> I learned how to exploit an access control vulnerability by manipulating the "id" parameter and observing sensitive data in redirect responses. <br> I had difficulty finding the password in the HTML code, but this challenge taught me valuable skills and improved my problem-solving abilities.|

<img width="1440" alt="Screenshot 2025-02-12 at 17 08 22" src="https://github.com/user-attachments/assets/5232637d-471d-4685-bc01-dc9a57cbcc5a" />
