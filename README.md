### Assignment 2 - Web Development 1 - SETU HDip in Computer Science: Semester 1

  # Whether Weather

A web application to display the weather for different cities globally.

### Getting Started

#### Install Eleventy

```bash
npm install -g @11ty/eleventy
```

#### Run Eleventy

```bash
eleventy --serve
```

Now navigate to [http://localhost:8080](http://localhost:8080) to see your site.

Hot reloading is enabled, so any changes you make to your files will be reflected in the browser.

### Technologies

* [Eleventy](https://www.11ty.dev/)
* [Bulma](https://bulma.io/)

---

#### Proof of concept 1 - Attributions
- The weather icon was obtained [here](https://iconscout.com/free-icon/free-weather-icon_1100758) and edited using microsoft powerpoint by me to include text
- Keep elements from stacking when narrowed using the is-mobile class found [here](https://bulma.io/documentation/columns/responsiveness/#mobile-columns)

- The clipart sun-image.png Designed By Nicole Jiang was taken from [here](https://pngtree.com/freepng/sun-clipart-golden-yellow-gradient-sun-vector-material_5564308.html?sol=downref&id=bef)
#### Proof of concept 2 - Attributions
- The sun and clouds weather icon was found [here](https://freesvg.org/vector-image-of-color-weather-forecast-icon-for-sunny-intervals) and is public domain
- The font was too big for mobile viewers on the todays weather section. I found that you can set widths for mobiles and desktops seperately [here](https://bulma.io/documentation/helpers/typography-helpers/#:~:text=Responsive%20size-,%23,-You%20can%20choose) which is kinda cool for how easy it is to apply
- I had this really annoying issue that I couldn't get the header and footer text to center when viewing on a mobile. I tried is-centered and that didnt work for mobile. So I saw in the dev-tools that the card-header & card-footer are both flex containers. Hence i was able to use is-justify-content-center to the the text centered on both mobile. For some reason if I removed the is-centered on the header then in desktop mode the title became left aligned. I had to settle for the workaround of using both is-justify-content on the card-header and is-centered on the card-header-item. Mysteriously the card-footer was fine with just is-justify-content-center???
  - I concluded that all card headers and footers in Bulma are flexbox containers by looking at the source repo for Bulma [here](https://github.com/jgthms/bulma/blob/main/sass/components/card.scss)
- Change all weather icons in the project to use Weather icons pack by MerlinTheRed for consistency across site. Used under CC BY-SA 3.0 which i found [here](https://www.deviantart.com/merlinthered/art/plain-weather-icons-157162192)
- For the icons in the weather info section I downloaded a pack of icons from [here](https://erikflowers.github.io/weather-icons/)
#### Proof of concept 3 - Attributions
- I took the weather for Rio from [here](https://www.accuweather.com/en/br/rio-de-janeiro/45449/weather-forecast/45449)
- I used the same image set from the "Today's Forecast" section of Proof of Concept 1, which I downloaded from [here](https://pngtree.com/freepng/sun-clipart-golden-yellow-gradient-sun-vector-material_5564308.html?sol=downref&id=bef) and were designed by Nicole Jiang
#### Dev Release 1
- I used the same image set from the "Today's Forecast" section of Proof of Concept 1, which I downloaded from [here](https://pngtree.com/freepng/sun-clipart-golden-yellow-gradient-sun-vector-material_5564308.html?sol=downref&id=bef) and were designed by Nicole Jiang
- I took the weather data from [here](https://www.accuweather.com/en/world-weather)
#### Dev Release 2
- At this point I had to make a decision to either implement the rest of the pages using page generation through loops and pagaination or to copy paste the code and fill in the details then later convert everything to pagination. I have decided to try to implement pagination now. No risk no reward, and the time i save on copy pasting i will use to learn pagination.
- Added a navbar dropdown for the cities by following the example on the [Bulma Documentation](https://bulma.io/documentation/components/navbar/#dropdown-menu)
#### Nunjucks refactor
- I replaced the values which will change in each city page with nunjucks variables following [this documentation](https://mozilla.github.io/nunjucks/templating.html#variables)
- I have previously worked with YAML before on [this course which I completed](https://www.udemy.com/course/python-3-deep-dive-part-3/?couponCode=CM251225G1) (see certificate [here](https://github.com/AdamMcCarthyCS/adammccarthycs/blob/main/certificates/Python%20Deep%20Dive%20Part%203.pdf)) in the section Serialization and Deserialization > PyYaml
- As you can write YAML out as key-value pairs,  it allows a neat layout of the variables rather than a dump of them with no organisation. Docs on key, value YAML pairs are [here](https://yaml.org/spec/1.2.2/#mapping). Basically in a nutshell you can write Yaml like:
  collection:
    \- item
  - This then allows you to call it in nunjucks as a variable using collection.item 
#### Eleventy refactor Cities (READ ME)
- Here I stumbled completely by mistake onto what I think is Eleventy's coolest feature. I realized after I had made all the variables into key, value pairs in YAML that some of the variables would exist on other Nunjucks template pages. I thought I was screwed and would have to abandon the idea of pagination because the variables exist on all separate pages. But when eleventy builds the pages it finds the variables in the other templates and fills them in as part of building the current page...CLASS...Genuinely, I was only moderately convinced by Eleventy until this moment, but now I think its great!!!