# ASP.NET MVC Web Project

## Introduction
A summary of my two-week internship with Prosper IT Consulting.
Here I participated in the building out of an ASP.NET MVC and Entity Framework content management service (aka CMS) website. 

The project involved the creation of an interactive website for managing the content and productions for a theater/acting company. 
The website was created with users in mind who are not technically savvy and want to easily manage what displays on their website.

I came into the project mid development, initially reviewing code and documentation before beginning work. My contribution to the team involved setting up and styling the About page, then setting up the Rental Histories specific areas of the website, Index page, Create and Edit pages that I was assigned to in our sprint. By the end of the sprint, I had completed two important sections and six story board items of the website project.

The first story I completed was creating and styling the About Page. I was given a reference and specific images and text to work with, approved by the product owner. Using Bootstrap 4 and CSS, I created a professionally designed web page and afterwards was assigned to the Rental Histories section of the website where the CRUD (create, read, update, delete) components were addressed.


## About Page

Relevant files/folders: [About.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Home/About.cshtml), [Site.css](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Areas/Site.css)

My first story was to create the necessary HTML skeleton and CSS styling to create the About page according to the Client's design including specific images and existing text from their current site.

Below is an animated visual example of the About page I constructed.

![gif](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Summary%20Gif%20FIles/About.gif)


Jump to: [Introduction](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#introduction), [About Page Styling](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#introduction), [Create and Edit Stories](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#rental-histories---create-and-edit-pages-and-functions), [Index page](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#rental-histories----index-page-view-sort-accordian-dropdown-edit-delete-and-detail-functions), [Other Details](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#other-relevant-project-details), [Page Top](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#aspnet-mvc-web-project)

    @{
        ViewBag.Title = "About";
    }

    @* This about page is going to show the Mission Statement, Ensemble (including the images),
        Company History, and Board.  Copy the text from Theatre Vertigos about page and use the
        same images they are using for the Ensemble.
        The font-family for the title is called 'broadway' *@
    <style>
        .body-content {
            width: 100vw;
            margin: 0;
            padding: 0;
            max-width: 100vw;
        }
    </style>
    <div class="home-about--page">

    <div class="home-about--title_logo_text">
        <h1>About Us</h1>

    </div>
    
    <div>
        <img src="~/Content/images/theater.jpg" alt="About us" class="home-about--title_img" />

      </div>

      @* MISSION STATEMENT *@

      <div class="home-about--mission_statement_text">
          <div class="text-center">
              <h3 class="home-about--title">WHO WE ARE</h3>
              <p>
                  To engage audiences through ensemble-driven productions with a focus on developing new works
              </p>
          </div>
      </div>



      @* COMPANY HISTORY *@

      <div class="home-about--company_history">
          <div class="text-center">
              <h3 class="home-about--title">COMPANY HISTORY</h3>
              <p class="home-about--company_history_text">
                  In 1997, Theatre Vertigo was founded by Paul Floding, Nanette Pettit and Jeff Meyers. Since then, Theatre Vertigo has performed in numerous spaces
                  including The Russell Street Theater, The Electric Company, Theater!Theatre!, and The Shoebox Theater. 
                  <p>From 2003 to 2014, Theatre Vertigo produced Anonymous Theatre as a summer fundraiser in
                  collaboration with The Anonymous Theatre Company.  Other past collaborations include defunkt theatre, 
                  Stark Raving Theater, and Tears of Joy Theatre.</p>
                  <p> Theatre Vertigo has worked on world premieres
                  including Faust.Us by Joseph Fisher, 99 Ways to Fuck a Swan by Kim Rosenstock, and The End of Sex by Craig Jessen.</p>
                  <p> In 2016, Theatre Vertigo produced its first officially commissioned work from a
                  playwright, I Want To Destroy You, by Rob Handel.
              </p>

          </div>
      </div>



      @* ENSEMBLE *@
      <div class="text-center">
          <div class="home-about--ensemble">
              <h3 class="home-about--title">ENSEMBLE</h3>

              <img src="~/Content/images/ensemble.jpg" alt="Ensemble" class="home-about--ensemble_img" />

              <p class="home-about--ensemble_text">
                  Alexander Buckner, Victoria Alvarez-Chacon, Heath Hyun Houghton
              </p>


              @* BOARD *@

              <div class="text-center">
                  <div class="home-about--board">
                      <h3 class="home-about--title">BOARD</h3>
                      <p class="home-about--board_text">
                      <p> Jamie Floyd (President) </p>
                      <p>Tom Mounsey</p>
                      <p>Marcia Reyes</p>
                      <p>Lena-Liis-Kiesel</p>

                  </div>

              </div>
          </div>
      </div>
  </div>


## Rental Histories - Create and Edit pages and functions
Relevant files/folders: [Create.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Views/RentalHistories/Create.cshtml), [Edit.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Views/RentalHistories/Edit.cshtml) [Rent.css](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Areas/Rent.css)

I was tasked there with creating and styling the Create and Index pages of the Rental Histories section. I created the database model and created a scaffold of the model to create the CRUD (create, read, update, delete) pages needed to continue building. 
I then created and styled a sort function for the database to be viewed as chosen by the user's sorting needs.

Below is an animated visual example of the Create and Edit pages and functionality I constructed.

![CreateGif](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Summary%20Gif%20FIles/Create%20and%20Edit.gif)


Jump to: [Introduction](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#introduction), [About Page Styling](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#introduction), [Create and Edit Stories](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#rental-histories---create-and-edit-pages-and-functions), [Index page](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#rental-histories----index-page-view-sort-accordian-dropdown-edit-delete-and-detail-functions), [Other Details](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#other-relevant-project-details), [Page Top](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#aspnet-mvc-web-project)

## Rental Histories -  Index page: *view, sort, accordian dropdown, edit, delete and detail functions*
Relevant files/folders: [Index.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Views/RentalHistories/Index.cshtml), [Rent.css](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Areas/Rent.css)

Relevant MVC files/folders: [Rent Folder](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/tree/main/Rent), [Controller - RentalHistories.cs](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Controllers/RentalHistoriesController.cs), [Model - RentalHistory.cs](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Models/RentalHistory.cs), [View - Index.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Views/RentalHistories/Index.cshtml)

Below is an animated visual example of the Index page sorting, edit, create and accordian detail collapse features I constructed.

![Index Sorting Gif](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Summary%20Gif%20FIles/Index%20Sorting.gif)


Jump to: [Introduction](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#introduction), [About Page Styling](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#introduction), [Create and Edit Stories](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#rental-histories---create-and-edit-pages-and-functions), [Index page](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#rental-histories----index-page-view-sort-accordian-dropdown-edit-delete-and-detail-functions), [Other Details](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#other-relevant-project-details), [Page Top](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#aspnet-mvc-web-project)

## Other relevant project details

The project was accomplished using Microsoft's Visual Studio, pushing newly coded story modules to the master stored on Azure.
We utilized a specific naming convention ( [Model]-[Page]-[Element/Name] ) for newly created code modules for all css styling class and id's to keep sections organized for other team members. 

I gained more experience using Git and the Azure DevOps cloud services platform which was setup to coordinate the team's efforts. The project was managed using the Agile Scrum Framework having a Sprint Planning Session, Daily Stand-ups and Weekly Code Retrospectives. 

