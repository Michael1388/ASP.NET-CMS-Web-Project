# ASP.NET MVC Web Project

## Introduction
A summary of my two-week internship with Prosper IT Consulting.
Here I participated in the building out of an ASP.NET MVC and Entity Framework content management service (aka CMS) website. 

The project involved the creation of an interactive website for managing the content and productions for a theater/acting company. 
The website was created with users in mind who are not technically savvy and want to easily manage what displays on their website.

I came into the project mid development, initially reviewing code and documentation before beginning work. My contribution to the team involved setting up and styling the About page, then setting up the Rental Histories specific areas of the website, Index page, Create and Edit pages that I was assigned to in our sprint. By the end of the sprint, I had completed two important sections and six story board items of the website project.

I completed the creation and styling of the About Page. I was given a reference and specific images and text to work with, approved by the product owner. Using Bootstrap 4 and CSS, I created a professionally designed web page and afterwards was assigned to the Rental Histories section of the website where the CRUD (create, read, update, delete) components were addressed.


## About Page

Relevant files/folders: [About.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Home/About.cshtml), [Site.css](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Areas/Site.css)

My first story was to create the necessary HTML skeleton and CSS styling to create the About page according to the Client's design including specific images and existing text from their current site.

Below is an animated visual example of the About page I constructed.

![gif](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Summary%20Gif%20FIles/About.gif)


Jump to: [Introduction](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#introduction), [About Page Styling](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#introduction), [Create and Edit Stories](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#rental-histories---create-and-edit-pages-and-functions), [Index page](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#rental-histories----index-page-view-sort-accordian-dropdown-edit-delete-and-detail-functions), [Other Details](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#other-relevant-project-details), [Page Top](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#aspnet-mvc-web-project)



## Rental Histories - Create and Edit pages and functions
Relevant files/folders: [Create.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Views/RentalHistories/Create.cshtml), [Edit.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Views/RentalHistories/Edit.cshtml), [Rent.css](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Areas/Rent.css), [JavaScript Query](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Scripts/Rent.js)

I was tasked here with creating and styling the Create and Index pages of the Rental Histories section. I created the database model and a scaffold of the model to create the CRUD (create, read, update, delete) pages needed to continue building. I then created a Jquery script for flipping title text on the create/edit pages notes/damage input when checkbox changed. Each line item also included an "on hover" drop-down menu function to edit, delete or view the specific index database id item.

Below is an animated visual example of the Create and Edit pages and functionality I constructed followed by the corresponding code snippets.

![CreateGif](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Summary%20Gif%20FIles/Create%20and%20Edit.gif)


Jump to: [Introduction](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#introduction), [About Page Styling](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#introduction), [Create and Edit Stories](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#rental-histories---create-and-edit-pages-and-functions), [Index page](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#rental-histories----index-page-view-sort-accordian-dropdown-edit-delete-and-detail-functions), [Other Details](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#other-relevant-project-details), [Page Top](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#aspnet-mvc-web-project)

Code Snippets:

Create.cshtml

        @model TheatreCMS3.Areas.Rent.Models.RentalHistory

    @{
        ViewBag.Title = "Create";
        Layout = "~/Views/Shared/_Layout.cshtml";
    }


    @using (Html.BeginForm())
    {
        @Html.AntiForgeryToken()

    <div class="rental_history-create--title">
        <h3>Create Rental History</h3>
    </div>

    <div class="container-fluid">
        <div class="rental_history-create--form-horizontal">
            <div class="rental_history-create--form">

                @Html.ValidationSummary(true, "", new { @class = "text-danger" })
                <div class="form-row">

                    <div class="col-md-8">
                        @Html.LabelFor(model => model.Rental, htmlAttributes: new { @class = "control-label rental_history-create--name " })

                        @Html.EditorFor(model => model.Rental, new { htmlAttributes = new { @class = "form-control" } })
                        @Html.ValidationMessageFor(model => model.Rental, "", new { @class = "text-danger" })

                    </div>
                    <div class="col-md-2">
                        @Html.LabelFor(model => model.RentalDamaged, "Damaged?", htmlAttributes: new { @class = "rental_history-create--damage rental_history-create--name" })
                        <div class="rental_history-create--checkbox">
                      
                            @Html.EditorFor(model => model.RentalDamaged)
                            @Html.ValidationMessageFor(model => model.RentalDamaged, "", new { @class = "text-danger" })

                        </div>
                    </div>
                </div>

                <div class="form-group">
                    @Html.LabelFor(model => model.DamagesIncurred, "Notes", htmlAttributes: new { @class = "control-label rental_history-create--damagesincurred col-md-16" })
                    <div class="col-md-16">
                        @Html.EditorFor(model => model.DamagesIncurred, new { htmlAttributes = new { @class = "form-control" } })
                        @Html.ValidationMessageFor(model => model.DamagesIncurred, "", new { @class = "text-danger" })
                    </div>
                </div>
                
                <div class="form-group">
                    <div class="col-md-offset-2 col-md-10">
                        <div class="rental_history-create--buttons">
                            <button type="button" class="btn btn-dark">@Html.ActionLink("Back to List", "Index", null, new { @class = "text-white" })</button>
                            <input type="submit" value="Create" class="btn btn-success" />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    }

    @section Scripts {
        @Scripts.Render("~/bundles/jqueryval")
    }


Edit.cshtml

    @model TheatreCMS3.Areas.Rent.Models.RentalHistory

    @{
        ViewBag.Title = "Edit";
        Layout = "~/Views/Shared/_Layout.cshtml";
    }



    @using (Html.BeginForm())
    {
        @Html.AntiForgeryToken()

    <div class="rental_history-create--title">
        <h3>Edit Rental History</h3>
    </div>

    <div class="container-fluid">
        <div class="rental_history-create--form-horizontal">
            <div class="rental_history-create--form">

                @Html.ValidationSummary(true, "", new { @class = "text-danger" })
                @Html.HiddenFor(model => model.RentalHistoryID)

                <div class="form-row">

                    <div class="col-md-8">
                        @Html.LabelFor(model => model.Rental, htmlAttributes: new { @class = "control-label rental_history-create--name" })
                        
                            @Html.EditorFor(model => model.Rental, new { htmlAttributes = new { @class = "form-control" } })
                            @Html.ValidationMessageFor(model => model.Rental, "", new { @class = "text-danger" })
                       
                    </div>
                    <div class="col-md-2">
                        @Html.LabelFor(model => model.RentalDamaged, "Damaged?", htmlAttributes: new { @class = "rental_history-create--damage rental_history-create--name" })

                        <div class="rental_history-create--checkbox">

                            @Html.EditorFor(model => model.RentalDamaged)
                            @Html.ValidationMessageFor(model => model.RentalDamaged, "", new { @class = "text-danger" })
                        </div>
                    </div>
                        
                </div>

                <div class="form-group">
                    @Html.LabelFor(model => model.DamagesIncurred, "Notes", htmlAttributes: new { @class = "control-label rental_history-create--damagesincurred col-md-16" })
                    <div class="col-md-16">
                        @Html.EditorFor(model => model.DamagesIncurred, new { htmlAttributes = new { @class = "form-control" } })
                        @Html.ValidationMessageFor(model => model.DamagesIncurred, "", new { @class = "text-danger" })
                    </div>
                </div>

              

                <div class="form-group">
                    <div class="col-md-offset-2 col-md-10">
                        <div class="rental_history-create--buttons">
                            <button type="button" class="btn btn-dark">@Html.ActionLink("Back to List", "Index", null, new { @class = "text-white" })</button>
                            <input type="submit" value="Save" class="btn btn-success" />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    }

    @section Scripts {
        @Scripts.Render("~/bundles/jqueryval")
    }
    
    
    
Rent.js - used Jquery for flipping text when checkbox changed
    
    $('#RentalDamaged').click(function () {

    if ($('#RentalDamaged').is(':checked')) {
        $('.rental_history-create--damagesincurred').html('Damages Incurred');
    } else {
        $('.rental_history-create--damagesincurred').html('Notes');
    }
        });



## Rental Histories -  Index page: *view, sort, accordian dropdown, edit, delete and detail functions*

Relevant files/folders: [Index.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Views/RentalHistories/Index.cshtml), [Rent.css](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Areas/Rent.css)

Relevant MVC files/folders: [Rent Folder](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/tree/main/Rent), [Controller - RentalHistories.cs](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Controllers/RentalHistoriesController.cs), [Model - RentalHistory.cs](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Models/RentalHistory.cs), [View - Index.cshtml](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Rent/Views/RentalHistories/Index.cshtml)


Here I created and styled the sorting functionality for the Index details page sort feature. I set the database to be able to be viewed as chosen by the user's sorting needs. Each viewable field included function to collapse and uncollapse the field to view the notes or damages incurred notes, as per item. 


Below is an animated visual example of the Index page sorting, edit, create and accordian detail collapse features I constructed followed by the corresponding code snippets.

![Index Sorting Gif](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/Summary%20Gif%20FIles/Index%20Sorting.gif)


Jump to: [Introduction](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#introduction), [About Page Styling](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#introduction), [Create and Edit Stories](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#rental-histories---create-and-edit-pages-and-functions), [Index page](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#rental-histories----index-page-view-sort-accordian-dropdown-edit-delete-and-detail-functions), [Other Details](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#other-relevant-project-details), [Page Top](https://github.com/Michael1388/ASP.NET-CMS-Web-Project/blob/main/README.md#aspnet-mvc-web-project)

Code Snippets:
Model for creating the database and scaffolding the CRUD pages

    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Web;

    namespace TheatreCMS3.Areas.Rent.Models
    {
        public class RentalHistory
        {
            public int RentalHistoryID { get; set; }
            public bool RentalDamaged { get; set; }
            public string DamagesIncurred { get; set; }
            public string Rental { get; set; }
        }
    }

Controller to create the sort finctionality view

     using System;
    using System.Collections.Generic;
    using System.Data;
    using System.Data.Entity;
    using System.Linq;
    using System.Net;
    using System.Web;
    using System.Web.Mvc;
    using TheatreCMS3.Areas.Rent.Models;
    using TheatreCMS3.Models;

    namespace TheatreCMS3.Areas.Rent.Controllers
    {
        public class RentalHistoriesController : Controller
        {
            private ApplicationDbContext db = new ApplicationDbContext();

          // GET: Rent/RentalHistories
          public ActionResult Index(string sortOrder)
          {
              ViewBag.NameSortParm = String.IsNullOrEmpty(sortOrder) ? "NoExtraSorting" : sortOrder;
              var rentals = from r in db.RentalHistories
                            select r;
              switch (sortOrder)
              {
                  case "NoExtraSorting":
                      rentals = rentals.OrderByDescending(r => r.RentalHistoryID);
                      break;
                  case "Damaged Rentals":
                      rentals = rentals.OrderByDescending(r => r.RentalDamaged == true).ThenByDescending(r => r.RentalHistoryID);
                      break;
                  case "Undamaged Rentals":
                      rentals = rentals.OrderByDescending(r => r.RentalDamaged == false).ThenByDescending(r => r.RentalHistoryID);
                      break;
                  case "RentalsAtoZ":
                      rentals = rentals.OrderBy(r => r.Rental);
                      break;
                  case "RentalsZtoA":
                      rentals = rentals.OrderByDescending(r => r.Rental);
                      break;
                  default:
                      rentals = rentals.OrderByDescending(r => r.RentalHistoryID);
                      break;
              }
              return View(rentals.ToList());
          }





## Other relevant project details

We utilized a specific naming convention ( [Model]-[Page]-[Element/Name] ) for newly created code modules for all css styling class and id's to keep sections organized for other team members. 

The project was accomplished using Microsoft's Visual Studio, pushing newly coded story modules to the master stored on Azure.

I gained more experience using Git and the Azure DevOps cloud services platform which was setup to coordinate the team's efforts. 

The project was managed using the Agile Scrum Framework having a Sprint Planning Session, Daily Stand-ups and Weekly Code Retrospectives. 

