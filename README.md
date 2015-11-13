# DataRepresentationProject

## Main concept

* Penalty points issued in Ireland

The idea behind this project is to create a working API for a dataset without esentially having to implement it. I was provided with a list of API's on the website of [data.gov.ie](https://data.gov.ie/data)  by the lecturer. After having a throught look at the datasets avaliable I have decided to go with one from [**RSA**](http://www.rsa.ie/) .ie's website who are the **R**oad **S**afety **A**utority.

The initial dataset was created in a way where the correct audience will be able to manage to browse it easily.

More data about the dataset itself can be found in the second last part of the readme file. 

-----------------------------------------------------------------
## Main Queries
***GET*** - this method will return a cell, row colum or a table from the dataset

Depending on the amount of data you wish to accquire you can change it up.


**Example:**

| JSON data returned|
|---------|
| ID = Year|
| Year |
| 1 - 12 = Category number of points |
| Cumulative points for a given category |
| Kind of request|
| URL access to the request |


```json
[{"id": "14_5",
"Year": 2015, 
"Category(1-12)": 5, 
"Total points": , 
"type" : "Get",
"url" : "https://rsa.ie/documents/penaltypointsstats/2014/penaltypoints?id=5"}]
```

-----------------------------------------------------------------
##Years

In order to display the following information we need to have a correct URL supporting it such as  https://rsa.ie/documents/penaltypointsstats/2015

We can change **2015** with any other year that is covered for example:

https://rsa.ie/documents/penaltypointsstats/2014

-----------------------------------------------------------------

##Months
Then we can start building upon it by adding additional infomration for instance **months**

after the year we add on month eg.

https://rsa.ie/documents/penaltypointsstats/2015/May

This will further allow us to localize part of data that we are more interested in.


-----------------------------------------------------------------
## More advanced - Pentalty points by category

In this specific case we take the standard url and add on "pentaltypoints?id=x" at the end where x is a value from 1 to 12 depending on offense we're looking for, here is an example:

https://rsa.ie/documents/penaltypointsstats/2015/penaltypoints?id=9

It is worth noting that the code will be slightly altered aswell as in this case we need to  change "id" by which we search to 15_9 or esentially 15'th year of current Century and ninth month


-----------------------------------------------------------------

## Post

Post method will allow us to update a cell in a chosen dataset.

```html
POST /penaltypointsstats/2014/May/penaltypoints?id=9 HTTP/1.1
User-Agent: Firefox/38.0.5 (compatible; Windows NT)
Host: localhost
Content-Type: text/html; charset=utf-8
Accept-Language: en-us
Connection: Keep-Alive

<html>
<body>
<p>1337</p>
</body>
</html>
```

At this point we should be expecting a response from Apache server detailing drtails like last modified, Etag and date of current access.

-----------------------------------------------------------------

##Delete

Deleting of a specific information contained within a cell can be very beneficial.

```html
DELETE /penaltypointsstats/2014/May/penaltypoints?id=9 HTTP/1.1
User-Agent: Firefox/38.0.5 (compatible; Windows NT)
Host: localhost
Content-Type: text/html; charset=utf-8
Accept-Language: en-us
Connection: keep-alive
```

From then on we should be expecting a response from the Apache server claiming that a Cell Value was erased from a given URI.

-----------------------------------------------------------------

##Dataset details 

The [dataset itself](http://www.rsa.ie/Documents/PenaltyPointsStats/2015/Jan/Analysis%20of%20Penalty%20Points%20(Current)%20Issued%20-%20(Cumulative)%20January%20%202015.pdf) consists of a wide number of drivers from all of Irelands Counties split down by Counties and Penalty Points obtained from various offenses commited as well as a total column. It is also important to mention that there is "Unknown" and "Foreign Licence Holders" under Counties which needed to be accounted for.

-----------------------------------------------------------------

**Columns:**

| County | Number of Drivers | Total |
|---------|-----------|---------|

| 1P.P. | 2P.P. | 3P.P. | 4P.P. | 5P.P. | 6P.P. | 7P.P. | 8P.P. | 9P.P. | 10P.P. | 11P.P. | 12P.P. |
|---------|-----------|---------|-----------|---------|-----------|---------|-----------|---------|-----------|-----------|-----------|

| Total |
|---------|

-----------------------------------------------------------------

##Few Final words

Throught the course of this project I started to really appreciate the markdown for editing and will try to improve on it for second Semmester project to make reporsitories easier to read and absorb.








