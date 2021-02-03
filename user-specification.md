#DevsHelpDevs User Specification V0.5

This document describes the planed platform from a users point of view.


### Definitions 
* Applicant - Developer applying on the platform for Help
* Donor - People using the platform to help applicants
* Staff - People from the community that administer the platform and review applications
* Application - The Data that describes the need of an applicant

### Platform description

The platform has to provide services for all three user types Applicants, Donors and Staff

From my current perspective I would implement the interface for the Donors as Web app, for applicants a mobile app is probably better because it makes uploading images much easier if you only have a phone and we can implement push notifications and be able to track some more information to prevent scams. It will depend on what the staff will use best. I currently lean towards an app but we have to discuss which functionality is needed. In the following the functionality is described without any specific technology in mind.

## Functionality for Donors

### Main page

This is the homepage of the platform. If contains:

### logo + title
 to be discussed

### Grid with 6 application cards. 
This cards will be selected randomly from the registered applicants.

Each application card contains:

* Picture of the applicant
* name
* Twitter Handle
* country
* type of need (spare parts, repair, used laptop, collection for new laptop)
* teaser text of his story

When you click on one of the cards you will get to the application page

### Simple Filter Buttons

Filter Buttons for

* Country of Applicants (to be discussed but I think many donors may have a special tie to a certain country)
* Price ranges of needed help
* Type of needed help

Buttons should be toggle buttons + one clear filter Button. 

If any filter is changed the 6 cards get updated.

### Show all Button

If this Button is clicked all applications that match the filter  will be shown in a multi-column list.

### Login/Account Button
Will popup a Login dialog with the ability to register

In general donors don't have to register to browse applications and they also can directly contact applicants if they have provided a Twitter handle. To make a Donation you have to register so that we can track actions.

Our Backend supports

* Email / Password
* Github
* Google
* Facebook

So we will offer all these.

When the user is logged in the button changes to an account button to display a list of applicants a donor is helping.

### Other links/buttons
* About: lead to an about page that explains who we are and what our Mission is

* How does it work: Description of the process to apply and how to donate

* IS IT SAFE: Leads to a page describing what measures this platform takes to prevent scams and fraud

* Partners: Page listing our partners like: Technology partners, local stores we cooperate with, payment providers me may recommend.

* FAQ: a page where we collect frequent questions and their answers

* Contact: Page with contact information. Possibly with a global chat window that can be monitored by all staff members. 


## Application Page of the applicant

### Images

Display:

* Applicants picture
* additional pictures to describe the situation (current old/broken Laptop, Screenshots of current system information)
* If a donor has registered show a picture of his ID (this has to be discussed. IMHO it would increase the trust for donors, but I'm not sure how much harm this could bring to applicants)

### Story
The story that the applicant has given when applying

### Request Details

* Type of wished support
* amount of money needed in US$

### Chat Window / messaging system

If a Donor is logged in a chat window will be displayed to communicate with the applicant.
This is currently merely an idea to solve this. we should discuss what's the best approach.

IMHO it's important that donors don't have to hand out any personal information if they don't want to to prevent people spamming them after an initial contact.

Staff will be able to view the communication in case a problem was reported from either side.

To be discussed if the chat of one application is visible to all registered donors. This would make sense that you can see if someone already is helping the person. It also helps the overall transparency. 

### Donate Button
When a donor wants to donate, he clicks on that button and will receive an email with all needed information how to help (shipping instructions if he wants to donate a laptop / payment information if he wants to donate money).

This will mark this application as 'solved' and it won't be displayed on the front page anymore.

### Report Problem Button
In case a donor has the impression this Application is a fraudulent one this will notify the staff about it.

### Share buttons
Buttons to share this Application on social media

## Account Page 

Displays the Applications a donor is already donating.

Has a close account button if a Donor wants to leave the platform.

## Applicant App
This is the app through that Applicants can apply for a donation

### First Start

* On first start the applicant has to register with one of the supported service providers.
* They have to add a picture of themselves as well as one of their official travel documents.
* They have to enter their full name, Address, mobile phone and email.
* The Email has to be verified with a link

* After Verification they are asked to enter all data that is necessary for a full Application (see Application page above)

### Home

(To be discussed if an Applicant can make more than one application at the same time).
Displays a list of the Applications the User has already open on hour platform.

* Central piece could be a chat screen to communicate with Donors. 
* A menu or Navbar to edit an Application
* Menus or Navbar to access statistics about their application (number of views)
* Share function for social media
* Button to report a problem with a donor,
* Button to confirm that a Donation was received

## Staff App/Website

* This app has to be able to display all new application that are no yet validated
* It also should be able to display all applications with status filter/search capabilities
* If a Application is reported as suspicious it also get reported here, possibly with a Push notification
* Staff group chat to discuss if there are problems (this could also be solved by a Signal group, but if we use some chat service anyway this would be a nice to have)
* Ability to invite new users/delete users / change users role

### Staff Application View
* Ability to block/unblock an application in case there is a problem
* Ability to ban users
* Ability to get into touch with a donor that is already in interaction with that Application
* If the Application is new the a function to validate the Application. Only after validation an Application will be listed on the main app.


## User Roles
From the above requirements its obvious that we need user roles to regulate access rights. 
Luckily the backend from nhost.io already supports this, so it should be easy to implement.