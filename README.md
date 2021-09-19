# Getting MEAN Book Project

This is my repository for the project described in the book Getting MEAN by Simon Holmes. This readme contains notes, screenshots, and readme chapter question responses for each chapter.

# <a name="ch10"></a>Chapter 10

[Heroku App](https://cryptic-dawn-68037.herokuapp.com/)

**Notes**
* On P. 315 there is a typo in Listing 10.9, at the top where it says `locationProvider` it should be `$locationProvider`.
* On P. 317 there is a typo under *Creating The New Common Template* it is missing a `<` after `vm.main.content`.
* For a while it would not let me post reviews stating `All fields required, please try again`, I fixed this by fixing the spacing in `reviewModal.view.html`.

**Chapter 10 Screenshot**

![ch10](/readme_images/Chapter10SS.png)

# <a name="ch9"></a>Chapter 9

[Heroku App](https://cryptic-dawn-68037.herokuapp.com/)

**Notes**
* I got stuck for a while at the end of 9.3.4 because I had forgotten a comma.
* This chapter was a slightly different version of chapter 8.

**Chapter 9 Screenshot**

![ch9](/readme_images/Chapter9SS.png)

# <a name="ch8"></a>Chapter 8

[Heroku App](https://cryptic-dawn-68037.herokuapp.com/)

**Notes**
* The filter functionality seems to be very sensitive. In order to find `Diversions Cafe` I need to type at least `Di` where as when I try to find `Jewel Box Cafe` I only need to type `J`.
* At first I forgot to change the way distances are calculated in `../public/angular/loc8rApp.js` and the distances were calculated in the thousands.
* I used `function loc8rData($http) {...}` & `function geolocation() {...}` rather than `var loc8rData = function($http) {...}` & `var geolocation = function() {...}` as shown in the book.

**Chapter 8 README Questions**
1. With AngularJS being a front-end framework, it means that the machine the code us executed on, is that of the user rather than the server.
2. If you put a `console.log()` command in your AngularJS controller, you would see the output in the browsers developer console.

**Chapter 8 Screenshot**

![ch8](/readme_images/Chapter8SS.png)

# <a name="ch7"></a>Chapter 7

[Heroku App](https://cryptic-dawn-68037.herokuapp.com/)

**Notes**
* I needed to add my google API key in order for the application to correctly display the cafe locations.
* When attempting to post a review with all of the fields filled out, it brings me to the error page displaying `error 400`. In terminal it states `[MongoError: Unknown modifier: $pushAll]`.
* I had an error that would not allow me to post reviews. I fixed this by adding `{usePushEach: true}` to the end of the `var locationSchema` in `../app_api/models/locations.js` and using `form.form-horizontal(action="", method="post", role="form")` rather than `form#addReview.form-horizontal(action="", method="post", role="form")` which is listed in the notes, in `..app_server/views/location-review-form.jade`.

**Chapter 7 README Questions**
1. **Consuming a REST API** is a *fancy* term for **using an API as part of your application**. We are "consuming" the API set up in chapter 6 because we are using it in chapter 7.
2. Deleting either `lng : -122.481541` or `lat : 47.262259` in the **homelist module** in `../app_server/controllers/locations.js` would cause the "API Lookup Error" message.
3. The bug on P. 215 is that if someone entered a `0` for `lng` or `lat` due to being on the equator or Prime Meridian, it would return an API error. This is because JavaScript actively looks for values it considers false, like an `empty string`, `null`, or `0`. The fix for this is to change the condition in the `locationsListByDistance` controller from: `if (!lng || !lat)` to `if ((!lng && lng!==0) || !lat && lat!==0)`.

**Chapter 7 Screenshot**

![ch7](/readme_images/Chapter7SS.png)

# <a name="ch6"></a>Chapter 6

[Heroku App](https://cryptic-dawn-68037.herokuapp.com/)

**Notes**
* Variables `routesAPI` and `routes` are called `index` and `indexApi` in my code.
* I had a bit of trouble reading the very specific instructions to make a bunch of different `module.exports` for the controllers.
* I had a problem on page 177 getting my databases to load. The solution to this was to switch the Node version from `4.1.0` to `4.2.1`.
* I had a problem after implementing locationsCreate with it returning `TypeError: Cannot read property 'split' of undefined` when attempting to post. This was solved by manually entering the information into Postman.

**Chapter 6 README Questions**
1. According to my API routing, the name of the function that will be called when the server receives a request at the `/api/locations` url is `locationsCreate`.
2. The format of the data that the server returns when you make a request to the api URLs is `JSON`.
3. Postman is used for **API Development** and it is useful because it allows the user to **easily test, develop, and document APIs by putting together both simple and complex HTTP requests**. Its functionality is similar to a web browser like chrome because it **allows you to use a URL to gather and send information requests** but is different because it **connects to the back end of the server rather than the front end**.

**Chapter 6 Screenshots**

![ch6_1](/readme_images/Chapter6SS_1.png)

![ch6_2](/readme_images/Chapter6SS_2.png)

# <a name="ch5"></a>Chapter 5

[Heroku App](https://cryptic-dawn-68037.herokuapp.com/)

**Notes**
* It is a lot easier to add data to the database using [Robomongo](https://robomongo.org/) than it is using terminal.
* I now have two [mLab](http://docs.mlab.com/) accounts due to the book having two separate sets of instructions.
* When my program runs in terminal, it does not return `Express server listening on port 3000`.
* When my program runs in production mode, it does not return `Express server listening on port 3000` nor `Mongoose connected to momgodb://heroku_app..`.

**Chapter 5 README Questions**
1. Individual database entries in MongoDB are called **Documents**.
2. The difference between the command line commands `mongo` and `mongod` is: `mongo` is the interactive command-line shell that connects to a specific instance of `mongod`, and `mongod` is the host process for the database, the core database process running in the background.
3. `mLab` provides a fully managed cloud database service. This allows us the ability to not only store our database, but to back it up, recover, monitor, and manage it.

**Chapter 5 Screenshot**

![ch5](/readme_images/Chapter5SS.png)

# <a name="ch4"></a>Chapter 4

[Heroku App](https://cryptic-dawn-68037.herokuapp.com/)

**Notes**
* Google did not require me to enter an API key to imbed Google Maps.
* The misprint in the book is located on page 99. The book tells you the code is in the file `app_server/views/location-info.js` when the actual file is `app_server/views/location-info.jade`.
* This version includes the wrap up process described in Appendix C.
* I used *Diversions Cafe* as the replacement to *Starcups*.

**Chapter 4 README Questions**
1. The Jade/Pug templates used in Chapter 4 help to avoid unnecessary repetition of code by allowing us to define something once in a layout file, such as `sharedHTMLfunctions.jade`, and use it as many times as we want by calling one line. In this case, that line is `+outputRating(location.rating)`.
2. When the `/location` url request is received, the route in `../routes/index.js` calls the `locationsInfo` function inside of  `../controllers/locations.js` which loads the `../views/location-info.jade` template.
3. In the MEAN acronym, the letter that is most closely associated with the part of the stack that provides our routing functionality is **E: Express**. Express is a back-end web framework that allows users to easily create routes, handle cookies, etc.

**Chapter 4 Screenshot**

![ch4](/readme_images/Chapter4SS.png)

# <a name="ch3"></a>Chapter 3

[Heroku App](https://cryptic-dawn-68037.herokuapp.com/)

**Notes**
* Created a web application using directions from the book *Getting MEAN with Mongo, Express Angular, and Node*.

**Chapter 3 README Questions**
1. The process of mapping URL requests to the functionality we want to associate with the URL is called **routing**.
2. The Node command to bring an external module into your code (for the chapter 3 code) is
```javascript
var index = require('./app_server/routes/index');
var users = require('./app_server/routes/users');
```
3. If you put `console.log('This is a console log message')` into the `apps.js` file, you see the message in the console after the application has been launched.

```
17:18:37 web.1   |  > book-project@0.0.0 start /Users/benscarbrough/Atom/CSCI 240/Book_Project
17:18:37 web.1   |  > node ./bin/www
17:18:37 web.1   |  This is a console log message
```

**Chapter 3 Screenshot**

![ch3](/readme_images/Chapter3SS.png)
