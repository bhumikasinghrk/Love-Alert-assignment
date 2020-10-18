## Love-Alert-assignment
#### This ipython notebook scrapes all the emails in an email account, and filters out emails having a specific provided subject. This notebook works only on gmail accounts since [imap.gmail.com](imap.gmail.com) is used. The link that contains list of IMAP servers for most commonly used email providers. Those servers can be used in case of any other gmail account. But let's do it for gmail now.

#### To execute the code-
 1.The variable username takes the emailId of a gamil account and password takes the password for that account as input respectively. Enter these details before running the cell.
 
 2. Make sure you [allow secure apps access](https://myaccount.google.com/lesssecureapps?pli=1) in the security section of your gmail account, otherwise you won't be able to login and code would throw an error saying "login failes".
 
 3. After logging in, let's start getting email. "N" refers to the top N emails you want to scrape, in case you want to scrape top 10 emails N=10, but since we want to scrape all emails, N=messages, denoting all emails.
 
 4. I have used range(messages, messages-N, -1), which means going from the top to the bottom, the newest email messages got the highest id number.
 
 5. I have used the imap.fetch() method, which fetches the email message by ID using the standard format specified in RFC 822.
 
 6. decode_header() function from email.header module to decode the subject of the email address to human readable unicode.
 
 7. While checking the condition of subject == "Thank you for applying" or any other phrase, make sure your gmail account has emails having this subject otherwise the output will be empty.
 
 8. The filtered out emails are stored in a list and that list is exported to a csv file, containing header sender of the mail, email message Id and subject of the email.
 
 9. Logout the email account.
 
 10. Last cell imports pandas and reads the csv file, showing the filtered out emails in form of a dataframe.
