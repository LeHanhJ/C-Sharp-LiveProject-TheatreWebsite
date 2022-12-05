# C-Sharp-LiveProject-TheatreWebsite
 
Thank you for checking this code summary out! It details the types of problems I encountered in the Live Project and how I managed to work past them.  This is the second and last live project that I've worked on while with The Tech Academy, and I can say that this project was one that I enjoyed most! Working with a team really helped myself understand that the entire process is a team effort, something that was lacking in the first project where we used the Django framework to create a web application of our own choosing. While making our own applications were fun, the problem solving in this second project made me enjoy the process even more.

Below you will find the story cards I was assigned to, and the code snippets I worked on during this two week live project! 


#### About the Project

To start, here is the overview we were given at the start of our project:

![Theatre CMS Overview](TheatreCMSOverview.png)

Our roles as developers were to collaborate on a website for a local theater/acting company, making it easy to use for users who don't have much experience with technology. As such, it is considered a content management service that is built using ASP.NET MVC and Entity Framework.

My role specifically was to work on the Cast Member list over the course of a few stories, which are detailed below.

### Story 1: Create Entity Model for CastMember

![Story 1: Create an Entity Framework model for CastMember, Part 1](../C-Sharp-LiveProject-TheatreWebsite/Photos/StoryCards/Card1CastMemberEM.jpg)

![Story 1: Create an Entity Framework model for CastMember, Part 2](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/StoryCards/Card1CastMemberEM2.jpg)

My first story came in three parts; the first part had me create an entity model for the CastMember class, and the second was to create an enum for the positions the Cast Member would hold. This was one of the most straightforward story in the live project. As you can see below, I created the entity model and created a database for it. I checked that the database was created correctly by using SQL Server Object Explorer.

![CastMember EF Model Snippet](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CastMemberModelSnippet.png)

The most difficult part for me in this particular story was that I had trouoble connecting with the ASPNET_THEATRECMS3 server that we were using on this project, but with a little research and questioning, I eventually connected to the server and synced up my database. 

After creating the model, I scaffolded the CRUD pages to create the views and controller based on the CastMember model. In our case, we had to make sure the controller, views, and models were in the correct area in the solution to easily mediate each programmer's specific task.

![Solution Explorer - Cast Member](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CRUDPart1Solution.png)

At this point, I checked to see if the Index, Create, Delete, Details, and Edit views were accessible, and they were! I also learned that some of the Views, like Edit and Details, would show a 400 error, but that was because there was no data in the database yet!

### Story 2: CRUD Pages, Stylizing the Create and Edit Pages

![Stylizing the Create and Edit Pages, Part 1](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/StoryCards/Card2CRUDPart1.jpg)

![Stylizing the Create and Edit Pages, Part 2](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/StoryCards/Card2CRUDPart1-2.jpg)


My second task was to stylize the Create and Edit pages that I had scaffolded in the previous story. This story seemed to be the most time consuming personally because of how I wanted the pages to look. Reflecting back on the live project, I could've spent less time on this aspect, but I wanted my pages to look as polished as I could make it. Here are some code snippet of the CSS file that we used for our section of the website. 

![CSS Code Snippet 1](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CSSCodeSnippet1.png)

![CSS Code Snippet 2](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CSSCodeSnippet2.png)

Looking back on the project, the css for the Cast Member Create and Edit pages could've been refactored and conglomerated to save room and increase readability. After all, if we were to look further in the code, it seems like the Edit and Create pages uses the same stylings! However, I suppose that one would like to have the Create and Edit stylings to be seperate from each other to ensure there is less confusion when editing one page from another!

You can see the finished version below:

![Create CastMember Page Final](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CreateCastMemberPageFinal.png)

I also worked on creating miscellaneous requests from the stories, such as changing the color of the Create and Back To List buttons on hover, and creating a dropshadow on whatever box has been selected by the user.

![Create Page Drop Shadow](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CreatePageDropShadowBox.png)

![Create Page Dropdown Selector](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CreateCastMemberDropdownMenu.png)

![Create Page Buttons, No Hover](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CreatePageNoHover.png)

![Create Page Buttons, Create Button Hover](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CreatePageCreateHover.png)

![Create Page Buttons, Back to List Hover](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CreatePageBackToListHover.png)

### Story 3: Photo Storage and Retrieval for CastMember

![Story 3: Photo Storage and Retrieval for CastMember](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/StoryCards/Card3PhotoStorage.png)

Starting from this story, all other stories that were assigned were optional. Regardless, this story was the one that gave me the most difficulty out of the previous ones assigned, but it was also the most satisfying to figure out! 

First off I had to create a method in the CastMember Controller to enable a file that was selected by a user and convert it into a byte array. It took me a while to fully undedrstand this task; I had to look into byte arrays, the HttpPostedFileBase class, the BinaryReader class, and how they all fit together.

Below, you can see that the Upload() method takes in an HttpPostedFileBase input parameter (what image the user will be choosing) and converting it into a byte[] (byte array). It uses the BinaryReader class to convert the uploaded file into binary code, then assigned that to the byte[] *bytes*. *bytes* is defined as the content length of the binary code that has been read using the BinaryReader and the InputStream pointer. At the end of the method, we return this byte[] *bytes*.

![Upload Method in CastMember Controller](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/UploadMethod.png)

Next, I have to modify both the Create() and Edit() methods to take in the photoUpload parameter that we had also put in the Upload() method. This is so we are able to define it in the method and use the parameter as well as the previously defined Upload() method to save the image to the database we had first created in the first story. 

![Controller Create Method Updates](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CreatePhotoUploadController.png)

As a side note, I had uncommented the Photo attribute in the CastMember model that I had made earlier, and was told to comment out. Since we are using the Photo attribute now to save images from users, it's time to uncomment it!

![CastMember Model Update](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CastMemberModelStory3Update.png)

The next task in this story was to make sure that users were able to upload the images that they wanted to use. First I had to specify that the FormMethod of the page was POST, and because of that, I had to encode the data that forms the body of the request. We are using `multipart/form-data` due to the input type of Photo is of type "file".

![Create View Photo](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CreateViewPhoto.png)

![Create View Beginning Using Statement](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/CreateViewEnctype.png)

Finally, all I had to do for this story was to present the file that was uploaded onto the Index page. I decided to return an image whose source stemmed from the Photo that was uploaded for that particular Cast Member. 

![Alt text](../../../../../../../C:/Users/dell/Desktop/LiveProjects/TheatreCMS3/C-Sharp-LiveProject-TheatreWebsite/Photos/IndexViewImage.png)


## Reflections on the LiveProject

This LiveProject was definitely my favorite project out of everything that I did in The Tech Academy as I felt like I learned the most from doing this singular project. I had to discover many things myself, and even though I needed a bit of help at some points, the entire project was very satisfying to see come to fruition. 

If I had more time, there were more optional stories that I could've done, but my biggest accomplishment was when I figured out the third story with the byte[]. I remember having a really hard time with that particular story, but with a little push, I was able to figure it out myself! 

## Final Thoughts

I hope that this code summary gives you a deeper look into what I am capable of, and I'm always hungry to learn more! Problem solving is the best part about this line of work for me, and I hope that I can have many more epiphanines in the future!