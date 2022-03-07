# Software Requirements

**What is the vision of this product?**
The ability to express creativity in a humorous way.

**What pain point does this project solve?**
Sometimes there just isn't a meme thagt accurately communicates how you feel at a given moment.

**Why should we care about your product?**
Because memes are the language of the Internet. The application will be light, free, easy to use, and encourages repeated use through user profile features.

## Scope (In/Out)
### IN - What will your product do

* Download a list of meme templates
* Edit/Update a given template with custom text
* Save the result into a user profile gallery
* Provide social media sharing links for each meme.

### OUT - What will your product not do.

* Will not allow custom image editing/uploading


**What will your MVP functionality be?**

* Able to take an image from API, overlay custom text and save the result to a new image.
* User's can log in to see their past memes.
* Able to update/delete past memes.
* Some kind of display or catalogue for memes.
* Links to share a meme on popular platforms.

**Stretch goals:**

* High level of integration with social media


**Functional Requirements**
List the functionality of your product. This will consist of tasks such as the following:

* User can create a profile, log in/log out.
* User can see a list of meme templates from which to choose and edit.
* User can edit a template with custom content.
* User can view their past creations on a profle page.
* User can update/delete their past creations.
* User can get a share link for their creations.

**Non-Functional Requirements**
* Security
  * Frontend and backend will be wrapped in Auth0 for security/authorization/authentication
  * Users will only have access to their own data for editing.
  * Meme templates will be cached locally to avoid excessive API calls
* Testing
  * Thunderclient to test API calls
  * Employ RESTful API practices
  * Ensure components are properly created to enable easy unit testing.
