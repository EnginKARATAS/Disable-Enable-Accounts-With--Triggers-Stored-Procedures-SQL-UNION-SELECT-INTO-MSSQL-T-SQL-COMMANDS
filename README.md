# Disable-Enable-Accounts-With--Triggers Stored Procedures SQL UNION SELECT INTO MSSQL-T-SQL COMMANDS
 
 <h1>tables: log, Activeusers , Passiveusers</h1>

 <h1>3 Social Media Users Database</h1>
3.1 Basics
We have a database where they can freeze their user accounts at any time and open the frozen account whenever they want. This data includes 3 different tables (activeusers, passiveuser and logs).
Active accounts (non-frozen accounts) in the system in the activeus table, passive users
The table contains data belonging to passive accounts (frozen accounts) in the system.
From the logs table, we have done to deactivate (freeze) and activate (re-open) accounts.
keep the data of the times. When a new account is opened, it is evaluated as if that account was activated at that moment.
Data usage will be made to the logs table.
When an account is deactivated, data belonging to that account is deleted from the activeusers table and transferred to the passiveusers table.
will be transferred. A similar situation will be the case for account activation.
• Our social media site does not allow account deletion (not deactivation).
Although there are PK relations between the tables in the given database, please avoid making any PK definition in the database so that you can make Application encodings.


<h1>3.3 Trigger Applications</h1>
Define the following triggers on the database.
When a user is deleted from the Activeusers table, this user will be added to the passiveusers table and data will be entered into the logs table.
When a user is deleted from the Passiveusers table, this user will be added to the activeusers table and data will be entered into the logs table.
• When there is a new user login to the Activeusers table, data will be entered into the logs table.
While entering data into the Activeusers table, email data can be obtained from a simple control using Regular expressions.
will be passed. Email that does not contain the @ character and contains the @ character but is the first and / or last character
entries will not be accepted by the database. Database will not enter data into activeusers table and same
will give an error message in time.

<h1>
3.4 Applications to Stored Procedure
The emailfind function will take an email address as a parameter and the active user belonging to this email address.
will return data. If no such user is found, it will return a blank line.
• The ausercnt procedure will not take parameters and will return a number of how many active users there are.
• allusers procedure will not take parameters and will return information about all active and passive users.
</h1>