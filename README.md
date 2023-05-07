# ASP.NET MVC Web Project
 
A summary of my two-week internship with Prosper IT Consulting.
Here I participated in the building out of an ASP.NET MVC and Entity Framework content management service (aka CMS) website. 

The project involved the creation of an interactive website for managing the content and productions for a theater/acting company. 
The website was created with users in mind who are not technically savvy and want to easily manage what displays on their website.

I came into the project mid development, initially reviewing code and documentation before beginning work. My contribution to the team involved setting up and styling the About page, then setting up the Rental Histories specific areas of the website, Index page, Create and Edit pages that I was assigned to in our sprint. By the end of the sprint, I had completed two important sections and six story board items of the website project.

The first story I completed was creating and styling the About Page. I was given a reference and specific images and text to work with, approved by the product owner. Using Bootstrap 4 and CSS, I created a professionally designed web page and afterwards was assigned to the Rental Histories section of the website where the CRUD (create, read, update, delete) components were addressed.


## About Page

Relevant files/folders: [About.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Home/About.cshtml), [Site.css](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Areas/Site.css)

My first task was to create the necessary HTML skeleton and CSS styling to create the About page according to the Client's design including specific images and existing text from their current site. We utilized a specific naming convention ( [Model]-[Page]-[Element/Name] ) for all styling class and id's to keep sections organized for other team members. 

Below is an animated visual example of the entire About page I constructed.
![gif](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Summary%20Gif%20FIles/About.cshtml.gif)


Jump to:

## Rental Histories - Create and Edit pages and functions
Relevant files/folders: [Create.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Views/RentalHistories/Create.cshtml), [Edit.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Views/RentalHistories/Edit.cshtml) [Rent.css](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Areas/Rent.css)

I was tasked there with creating and styling the Create and Index pages of the Rental Histories section. I created the database model and created a scaffold of the model to create the CRUD (create, read, update, delete) pages needed to continue building. 
I then created and styled a sort function for the database to be viewed as chosen by the user's sorting needs.



Jump to:

## Rental Histories -  Index page: *view, sort, accordian dropdown, edit, delete and detail functions*
Relevant files/folders: [Index.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Views/RentalHistories/Index.cshtml), [Rent.css](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Areas/Rent.css)

Relevant MVC files/folders: [Rent Folder](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/tree/main/Rent), [Controller - RentalHistories.cs](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Controllers/RentalHistoriesController.cs), [Model - RentalHistory.cs](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Models/RentalHistory.cs), [View - Index.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Views/RentalHistories/Index.cshtml)


Jump to:

## Other relevant project details

The project was accomplished using Microsoft's Visual Studio, pushing newly coded story modules to the master stored on Azure.
I gained more experience using Git and the Azure DevOps cloud services platform which was setup to coordinate the team's efforts. The project was managed using the Agile Scrum Framework having a Sprint Planning Session, Daily Stand-ups and Weekly Code Retrospectives. 

