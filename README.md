# Python-Live-Project
This live project was an appbuilder that held multiple apps of varying hobbies and activities that the user could choose from. Our purpose for this project was to create an app of our choosing (so long as the app we selected wasn't already implemented) that allowed users to create, update, read, and delete items from a database (also known as CRUD functions). Our project management was done through Microsoft Azure and covered a 2-week span. 

## Languages Used:
* HTML/CSS
* Python/Django

## Other Tools Used
* Bootstrap
* Beautiful Soup
* PyCharm (IDE)

For this code summary, I will provide three sections of code snippets and images to highlight key aspects of my overall tasks performed during the 2-week sprint.

## Code Snippets
* [Members](./Code-Snippets/MembersCodeSnippet.txt)
* [Edit](./Code-Snippet/EditCodeSnippet.txt)
* [Beautiful Soup](./Code-Snippet/BeautifulSoupCodeSnippet.txt)

## App Images
* [Members](./App-Images/python-members.png)
* [Edit](./App-Images/python-edit.png)
* [Beautiful Soup](./App-Images/python-beautiful-soup.png)

### Members
The [members template](./App-Images/python-member.png) was designed to display all items/records that were currently stored in the database by each members' username. I decided to place all of the records into a list-group and added a functioning scrollbar for quick navigation. Each item in the list was an action link that when clicked would display a details page of that member's information (everything EXCEPT the user's password). The [code snippet](./Code-Snippets/MembersCodeSnippet.txt) begins with the models.py file which creates the database that stores all member's account information. Following this file is the view.py file which has logic that sends all records from the database - stores it in a dictionary - and sends them back to the members html template for display to the user.

### Edit Page
It's important to note that all CRUD pages (create, update/edit, read/details, and delete) were created for this app but I'm only highlighting the edit page for the code summary. The [edit page](./App-Images/python-edit.png) displays a form that was modeled from the database which shows the current information of the user selected in each editable field. This page allows the user to make any edits to the specified account and save their changes by pressing the save button. The [code snippet](./Code-Snippets/EditCodeSnippet.txt) begins with the views.py file which has logic that uses the primary key of the selected item to locate that record in the database. It then checks to see if the information in the form had been posted (request.method == POST) and if all of the information in the form has met all the requirements (form.is_valid()). If successful, all changes will be saved. However, if the request is not a POST, the views.py file will render the edit html template and pass in a dictionary value of the UserForm for that particular account.

### Beautiful Soup
The [Beautiful Soup](./App-Images/python-beautiful-soup.png) page displays web content that was 'scraped' from another website. This allowed me to leverage some helpful tips to improve users' study habits while not having to retype it all. The [code snippet](./Code-Snippets/BeautifulSoupCodeSnippet.txt) shows how to use Beautiful Soup and the requirements needed to do so. Once I had access to the website I wanted to data scrape from, I had to dissect each particular element I wanted to display on my page by first getting all heading (h4) and paragraph (p) elements and then getting the text of each indexed element I wanted to share. Each element was stored as a tuple in a variable named top_ten. From there, the views.py file passed all values as a dictionary {'top_ten':top_ten} into the html template. Lastly, the html template displayed each value by indexing each tuple value using django variables {{ top_ten.1 }}.

