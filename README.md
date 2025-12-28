**Student Name: Adam McCarthy**
**Student Number:** ********* (Redacted for GitHub)

# Weather Weather Web App

**Assignment 2 - Web Development 1
SETU HDip in Computer Science (Semester 1 - Autumn 2025)**

Whether Weather is a desktop and mobile responsive, data-driven weather web application built with Eleventy, Nunjucks, and the Bulma Framework.

The site displays a dashboard, multiple global city pages generate through pagination, and reusable templates which generate content from YAML data files.

The site is hosted on Netlify [here](https://assignment2-whether-weather.netlify.app/)

## App Images

### Desktop Screenshots
  #### Dashboard
  ![Dashboard Desktop Screenshot](readme-images/app-dashboard.jpg)
  #### City Page
  ![City Page Desktop Screenshot](/readme-images/app-city-page.jpg)
  #### Settings Page
  ![Settings Page Desktop Screenshot](/readme-images/app-settings-page.jpg)
### Mobile Screenshots
  #### City Page
  ![City Page Desktop Screenshot](/readme-images/mobile-city-page.png)

---

## Product Specification

Weather weather is developed using static-site development with Eleventy. City pages are generated dynamically through pagination using data sourced from YAML files.

The site contains:
- A *Dashboard* with clickable weather cards for six cities which link to individual pages.
- Six *City* pages generated through Eleventy pagination and a data source which could in the future be linked with an API
- A settings page for the user to select options for customising their experience.

---
## Site features
 - City pages paginated from structured data which is easily updatable
 - Reusable Nunjucks templates and partials
 - Navigation which updates as the site does implemented by Eleventy Navigation Plugin
 - Site cards generated through Nunjucks loops and data sources
 - Responsive layout implemented with Bulma
 - Netlify ready json build file

---

## Getting Started

### Install Eleventy

```bash
npm install @11ty/eleventy js-yaml
```

### Run Eleventy

```bash
eleventy --serve
```

Now navigate to [http://localhost:8080](http://localhost:8080) to see your site.

Hot reloading is enabled, so any changes you make to your files will be reflected in the browser.

## Technologies
* [Eleventy](https://www.11ty.dev/)
* [Bulma](https://bulma.io/)
* [Nunjucks](https://mozilla.github.io/nunjucks/)
* [Netlify](https://www.netlify.com/)
### Plugins
* [Eleventy Navigation Plugin](https://www.11ty.dev/docs/plugins/navigation/)
* [js-yaml](https://www.npmjs.com/package/js-yaml)

## Project Structure
Generated using the "tree" command in terminal
 "tree -L -I "node_modules|.git|_site"

 ```
├── _data
├── _includes
├── assets
├── index.njk
├── package-lock.json
├── package.json
├── pages
├── readme-images
└── README.md
 ```

 ## Implementation Hightlights
 - Eleventy pagination generates one city page per data entry in cityData.yaml
 - eleventyComputed populates the Cities dropdown automatically
 - Nunjucks loops used
  - Dashboard
  - Partials:
   - left-panel-forecast-cards.njk
   - nav.njk
   - right-panel-seven-day-cards.njk
- Nunjucks variables linked to _data YAML files used throughout site rather than hardcoded for a single source of data for the  website
- Git tags used to capture the following stages of development which shows how the project was refactored to remove hardcoding of values and unnecessary repeated code:
  ```
  proof-of-concept-1
  proof-of-concept-2
  proof-of-concept-3
  release-1
  release-2 
  ```
- package.json build scripts included for Netlify Deployment

## Author
**Adam McCarthy** [GitHub](https://github.com/AdamMcCarthyCS)
**Date: Dec 2025**
**Email:** adammccarthycs@gmail.com
**Course:** [SETU Certificate in Computer Science](https://tutors.dev/course/setu-cert-comp-sci-2025)
**Module:** [Web Development 1](https://tutors.dev/course/setu-cert-comp-sci-2025-web-dev-1)

## Attributions

#### Proof of concept 1 
- The weather icon was obtained [here](https://iconscout.com/free-icon/free-weather-icon_1100758) and edited using microsoft powerpoint by me to include text
- Keep elements from stacking when narrowed using the is-mobile class found [here](https://bulma.io/documentation/columns/responsiveness/#mobile-columns)

- The clipart sun-image.png Designed By Nicole Jiang was taken from [here](https://pngtree.com/freepng/sun-clipart-golden-yellow-gradient-sun-vector-material_5564308.html?sol=downref&id=bef)
#### Proof of concept 2 
- The sun and clouds weather icon was found [here](https://freesvg.org/vector-image-of-color-weather-forecast-icon-for-sunny-intervals) and is public domain
- The font was too big for mobile viewers on the todays weather section. I found that you can set widths for mobiles and desktops seperately [here](https://bulma.io/documentation/helpers/typography-helpers/#:~:text=Responsive%20size-,%23,-You%20can%20choose) which is kinda cool for how easy it is to apply
- I had this really annoying issue that I couldn't get the header and footer text to center when viewing on a mobile. I tried is-centered and that didnt work for mobile. So I saw in the dev-tools that the card-header & card-footer are both flex containers. Hence i was able to use is-justify-content-center to the the text centered on both mobile. For some reason if I removed the is-centered on the header then in desktop mode the title became left aligned. I had to settle for the workaround of using both is-justify-content on the card-header and is-centered on the card-header-item. The card-footer appears to center with just is-justify-content-center
  - I concluded that all card headers and footers in Bulma are flexbox containers by looking at the source repo for Bulma [here](https://github.com/jgthms/bulma/blob/main/sass/components/card.scss)
- Change all weather icons in the project to use Weather icons pack by MerlinTheRed for consistency across site. Used under CC BY-SA 3.0 which i found [here](https://www.deviantart.com/merlinthered/art/plain-weather-icons-157162192)
- For the icons in the weather info section I downloaded a pack of icons from [here](https://erikflowers.github.io/weather-icons/)
#### Proof of concept 3 
- I took the weather for Rio from [here](https://www.accuweather.com/en/br/rio-de-janeiro/45449/weather-forecast/45449)
- I used the same image set from the "Today's Forecast" section of Proof of Concept 1, which I downloaded from [here](https://pngtree.com/freepng/sun-clipart-golden-yellow-gradient-sun-vector-material_5564308.html?sol=downref&id=bef) and were designed by Nicole Jiang
#### Dev Release 1
- I used the same image set from the "Today's Forecast" section of Proof of Concept 1, which I downloaded from [here](https://pngtree.com/freepng/sun-clipart-golden-yellow-gradient-sun-vector-material_5564308.html?sol=downref&id=bef) and were designed by Nicole Jiang
- I took the weather data from [here](https://www.accuweather.com/en/world-weather)
#### Dev Release 2
- At this point I had to make a decision to either implement the rest of the pages using page generation through loops and pagaination or to copy paste the code and fill in the details then later convert everything to pagination. I decided to implement pagination now. No risk no reward, and the time i save on copy pasting i will use to learn pagination.
- Added a navbar dropdown for the cities by following the example on the [Bulma Documentation](https://bulma.io/documentation/components/navbar/#dropdown-menu)
#### Nunjucks refactor
- I replaced the values which will change in each city page with nunjucks variables following [this documentation](https://mozilla.github.io/nunjucks/templating.html#variables)
- I have previously worked with YAML before on [this course which I completed](https://www.udemy.com/course/python-3-deep-dive-part-3/?couponCode=CM251225G1) (see certificate [here](https://github.com/AdamMcCarthyCS/adammccarthycs/blob/main/certificates/Python%20Deep%20Dive%20Part%203.pdf)) in the section Serialization and Deserialization > PyYaml
- As you can write YAML out as key-value pairs,  it allows a neat layout of the variables rather than a dump of them with no organisation. Docs on key, value YAML pairs are [here](https://yaml.org/spec/1.2.2/#mapping). Basically in a nutshell you can write Yaml like:
  collection:
    \- item
  - This then allows you to call it in nunjucks as a variable using collection.item 
#### Eleventy refactor City page
- Here I discovered that when eleventy builds the pages it finds the variables in the partials and fills them in as part of building the current page.
- I refactored the todays forecast cards into a single loop by following [this template](https://mozilla.github.io/nunjucks/templating.html#for)
#### Dev pagination sandbox
- This was the most part of the project and took significant effort. What I learned here:
  - Eleventy doesnt support YAML natively in _data folder [see here](https://www.11ty.dev/docs/data-custom/?utm_source=chatgpt.com)
  - It will recognise JSON no problem **see the testJSON file in the dev-pagination-sandbox branch**
  - You can use yaml but you need to install a plugin using: npm install js-yaml --save (the --save adds it as a dependency to the package.json file)

  - You can generate multiple pages using the citypagetemplate.njk as in the front matter:
    - pagination tells eleventy to loop over data/test
    - size: 1 means each item generates one page (item marked out with "-" )
    - alias is just a shorthand for the current page like a loop variable reprsenting a page as in {{page.someField}} is an attribute of that item like the name or greeting
    - permalink generates a url for that page

    - You can store the items to be filled in on each page in the [_data folder](https://www.11ty.dev/docs/data-global/) (which only supports JSON and JS files):
      - the test.yaml file is a list
      - each item in the file is an object
      - the slugs are iterated over and their variables are accessed using slug.variable 
      - this populates all the different pages by filling in their respective attribute values
    - Using the data required the installation of the [js-yaml](https://www.npmjs.com/package/js-yaml) plugin
#### Dev pagination
- I followed the same logic as in sandbox above and reproduced the six pages using a for loop
- For the dashboard, I have implemented the page as three columns. Nunjucks loops can be nested to do three columns of two cards by putting the different cities in sets of two in a column nunjucks list and within this list doing an inner loop to produce the two cards. This is essentially a nested list. Lists are marked out in yaml by using "-"
- The whole reason I did the loop on the dashboard page was so I could use the slug in each dashboardCards "card" to create a link which I could include in the anchor tag at pages/cityPages/{{ card.slug }}. This way I can use the cards as links to paginated pages and also have just a single piece of card html. I made the decision to not adjust cityData.yaml as it took a significant amount of time previously to implement, so I ended up repeating the same data again in the file dashboardCards.yaml, with some small changes. Not very DRY, but I saved a lot of html by using loops so I think its a decent tradeoff.
#### Dev settings
- Added buttons on the settings panel by following [this](https://bulma.io/documentation/elements/button/#button-group-with-addons) example on the bulma documentation 
- I could have refactored the buttons using a Nunjucks loop and a YAML file, but I chose not to as each button would have its own logic associated with it.
#### Misc Fixes
- The page titles displayed beside the header are generated through pagination for the cities only. I used the Nunjucks "or" keyword and the front matter of the Dashboard and Settings pages to ensure that those pages also had a matching page title. I learned about the or keyword [here](https://mozilla.github.io/nunjucks/templating.html#logic)
- This works the same as a short circuit expression in Python where it will use the first value it encounters which is 'truthy'. Hence when it finds the Settings or Template page it will have nothing from city.pageTitle (which is falsy) so will move onto pageTitle and will find the variable in the front matter and fill it in.
#### Eleventy Navigation Plugin
- I can use the eleventy navigation plugin by nesting the dropdown template for pages inside the main template for pages which I found [here](https://www.11ty.dev/docs/plugins/navigation/#humans-md)
  - This way I can use a nested loop to create the pages inside the dropdown in nav.njk
- I used [this example](https://www.11ty.dev/docs/data-computed/?utm_source=chatgpt.com#real-world-example) from the eleventy docs to generate the pages within the Cities dropdown
- In order for all pages to appear in dropdown i need to include addAllPagesToCollection: true, this is from [here](https://www.11ty.dev/docs/pagination/#add-all-pagination-pages-to-collections)
#### Deployment to Netlify
- Added build key to package.json following [this](https://11ty.rocks/posts/create-your-first-basic-11ty-website/?utm_source=chatgpt.com#:~:text=Begin%20the%20Project-,%23,-Open%20a%20new) webpage's instructions for deployment
  - following [these](https://11ty.rocks/posts/create-your-first-basic-11ty-website/?utm_source=chatgpt.com#connect-to-netlify-and-deploy) steps

## Github repository

The github repository for this project can be found [here](https://github.com/AdamMcCarthyCS/web-dev-1-assignment-2)

Feel free to look through the repository's branches to see the evolution of the project:

In chronological order:
```
main
dev
dev-poc1-card
dev-proof-of-concept-1
dev-proof-of-concept-2
dev-proof-of-concept-3
dev-release-1
dev-release-2
dev-nunjucks-refactor
dev-eleventy-refactor-cities
dev-pagination-sandbox
dev-pagination
dev-cities-pagination
dev-settings
```