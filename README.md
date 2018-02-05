# CNNTwitterCrawler
CNNTwitterCrawler is a web crawler that crawls CNN and Twitter for the latest updates on Donald Trump.
This application was developed using Asp.Net(C#).

It retrieves:
1) From CNN, the 25 most recent articles containing the word "Trump". 
If the articles are less than 25, it retrieves the available articles that match this criteria.
2) From Twitter, any tweet containing the word "Trump"
If the tweets are less than 25, it retrieves the available tweets that match this criteria.

It then displays the results of (1) or (2) above, depending on which page the user accessed.



**PROJECTS IN SOLUTION**
1) CNNTwitterCrawler.Base - Contains the logic class (CrawlerLauncher.cs) and methods for the CNN Crawler and Twitter Crawler.

2) CNNTwitterCrawler - This is the web application.
Paths to relevant pages and classes here are:
2a) CNNTwitterCrawler\CNNTwitterCrawler\ThePages\Start\GetCNNUpdates.aspx - the page that gets the most recent articles about Trump from CNN
2b) CNNTwitterCrawler\CNNTwitterCrawler\ThePages\Start\GetTwitterUpdates.aspx - the page that gets the most recent tweets about Trump from Twitter

3) CNNTwitterCrawler\CNNTwitterCrawler\QueryController.cs - API that contains methods which the pages in 2a and 2b call to get the latest updates about Trump from CNN and Twitter, and parse it in JQueryDataTables which are displayed on the user's browser

NOTE: You can launch the solution to view the code in visual studio by clicking the 'CNNTwitterCrawler.sln' file.



**FEATURES**

**.** Crawls the latest 25 articles about Trump from CNN website and his latest 25 tweets
**.** Displays the titles of the crawled information in the pages of the web application described in the "PROJECTS IN SOLUTION" section
**.** Displays the whole article in a new window when the "View Details" button is clicked
**.** fields below the Table displayed in page, with the relevant details, and quick "Submit Query" button in order to perform this action.



**KNOWN ISSUES**



**Issue 1:**
Page has loaded and about 10 seconds after loading, the Table still shows no data.

**Solution:**
Note that the speed of getting and loading data to table depends on your internet connection speed.
However, after 10 seconds, the data must have likely been retrieved but JQuery data table failed to auto display the data.

To view the data, just click the table in the browser.



**Issue 2:**
After clicking on "View Details", I get alerted that article or tweet has been opened in a new window, but there's no such window

**Solution:**
This would likely happen to if you are using Google Chrome browser, as chrome has features which inherently disable popup viewing.

Use Internet Explorer or Microsoft Edge instead, and you'll be fine.



**Issue 3:**
After filling the form below, I clicked the "Submit Query" button to send the mail, but got the error like the one in popup below:
![alt text](https://github.com/daify01/CNNTwitterCrawler/blob/master/EmailSenderError.jpg)

**Solution:**
1) Check to see if you got a saying google blocked sending of that mail, and you need to enable "less secure applications settings" on google to allow the mail send. If you got this mail, click the link in the mail to go to the page where you need to enable less secure applications, and enable it there.

2) If you still get the popup error image above after doing (1), then check for the mail telling you that google blocked suspicious sign in from a remote server, click the link button in the mail, and confirm that you tried to send the mail.

You will be able to send mails after this



**Issue 4:**
I was got a "Mail Sent Successfully" response, but the recipient cannot see the mail in their inbox

**Solution:**
Advise them to check their Spam folder.