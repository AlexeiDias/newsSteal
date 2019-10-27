# News Steal
##### This webapp kepps track of On and off duty employees. It also creates new employees and adds them the employees list.

## Technologies usen on the project
* Github
###### Github is a remote repository where we can store versions of our code.
* Gitlab
###### GitLab is a web-based DevOps lifecycle tool that provides a Git-repository manager providing wiki, issue-tracking and CI/CD pipeline features, using an open-source license, developed by GitLab Inc.
* HTML 5
###### HTML is a markup language tool where we write the text of our webpages. It Uses tags to organize the page in a  semantic meaning. Making easer to read and understand de structure of the page.
* JavaScript
###### JavaScript, often abbreviated as JS, is a high-level, interpreted scripting language that conforms to the ECMAScript specification. JavaScript has curly-bracket syntax, dynamic typing, prototype-based object-orientation, and first-class functions.

* Heroku
##### Heroku is a cloud platform as a service supporting several programming languages. It supports Java, Node, Scala, Clojure, Python, PHP, and Go.

* Mongodb
##### MongoDB is a cross-platform document-oriented database program. Classified as a NoSQL database program, MongoDB uses JSON-like documents with schema.
---
* gif demo
![how it looks](public/assets/images/screenshot.png)
---
## The following piece of code uses handlebars variables that represent the values that going to be render to the page.
```javascript
 axios.get('https://www.democracynow.org/')
  .then(response => {
      let $ = cheerio.load(response.data)
      var sources = [];
      var list = $('a', ".news_item").attr('data-ga-action', 'home: story headline')
      list.append($('picture', ".modern").attr('src',))
      for (let i = 0; i < list.length - 1; i++) {
          console.log("\nNew Item")
          if (list[i].children[0].type == 'text' && list[i].attribs.href != '') {
              console.log($(list[i]).text())
              console.log("Source:", `https://www.democracynow.org${list[i].attribs.href}`)
              // Add the text and href of every link, and save them as properties of the result object
              $("div h3").each(function(i, element) { 
      // Save an empty result object
      var result = {};
      console.log("result bellow here")
      console.log(list)
      console.log("result above here")
      // Add the text and href of every link, and save them as properties of the result object
      result.title = $(this)
        .children("a")
        .text();
        console.log("title bellow here")
        console.log(result)
        console.log(result.title)
        console.log("title above here")
      result.link = $(this)
        .children("a")
        .attr("href");
        console.log("link bellow here")
        console.log(result.link)
        console.log("link above here")
      result.igm = $(this)
        .children("picture")
        .attr("img");
        console.log("foto bellow here")
        console.log(result.img)
        console.log("foto above here")
      // Create a new Article using the `result` object built from scraping
      db.Article.create(result)
        .then(function(dbArticle) {
          // View the added result in the console
          console.log("article bellow here")
          console.log(dbArticle);
          console.log("article above here")
       })
        .catch(function(err) {
          // If an error occurred, log it
          console.log(err);
        });
      });
    }
  }
})
```
---
> Author
 Alexei Dias
 Linkedin 
 https://www.linkedin.com/in/alexei-dias-b4054a164/