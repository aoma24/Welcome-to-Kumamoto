# Development Documentation
__by Ayari Omachi__

In this readme file, I will be providing a guideline for implementing the project, highlighting the design patterns,  principles, iterations and improvements in my implementation. Particularly, I would want to focus on reflecting the process of improving my website from the mockup because there were many difficulties I faced during the process and countless decision-makings.

## Website Specifics
### Colors
```CSS
.palettes {
/*   mainly background color */
  color: #FFFDF5;
/*   mainly font/background color */
  color: #536250;
/*   mainly titles and borders */
  color: #AD9579;
/*   mainly small texts */
  color: #21231D;
}
```
#### Accessiblity
![contrast checker](readme_files/accessibility.png)
Using __Contrast Checker__ from __WebAIM__ to check that the website is accessible to anyone([Here is a link to WebAIM](https://webaim.org/resources/contrastchecker/))
There are two major combinations of colors that are used in the website are the above. According to the Contrast Checker, these color are considered accessible to all users in terms of the colors.


### Fonts
* Bungee & Bungee Shades: the titles of the nav, footer
* Advert Pro: section-title/sub-title
* Nunito: all others(descriptions)

## Design Patterns and Principles
### Contrast
This is relevant to creating an accessible design, but I kept in mind that some elements are different from the others and stand out because users may find it difficult to read if the design lacks in contrast.
![examples of contrast in website](readme_files/contrast.png)
### Balance
Because a design comprises many different elements such as colors, images, and typography, some draws more attention than others. Thus, I made sure that the pages have a feeling of balance with these elements laid out. I specifically used a symmetrical balance method, instead of an asymmetrical balance method, because I thought it is more easier to handle.
![examples of balance in website](readme_files/balance.png)
### Repetition
Throughout the prototype design process, I always came back to my mockup to double-check what my concept and purposes were and what I planned to do. This really helped the website with its consistency because it is easy to lose track of what you are doing when it comes to design. Since repetition is crucial to have a sense of unity in the website, I used fixed colors, navigation bar, footer, etc. for every page. 
## From Mockup to Prototype
### <ins>Footer</ins>
![Mockup and Prototype for footer](readme_files/footer.png)
Footer is one of the parts that had changed a lot from the mockup. As you may seen in the image, the mockup had hyperlinks or something similar to a sitemap where users can jump between pages, and I added this feature to the mockup because I thought it is a typical thing to do in websites. However, I realized when I was building this website that there would be  exact same page-links from footer and nav as my plan was to have the navigation bar fixed at the top when users scroll down the pages. I was not able to anticipate this ealier because I did not include a mockup design with the fixed navigation bar. At the end, I removed the whole div element with hyperlinks and kept the name of the website and its contact informtion.

In addition, I added a embedded map of the place inbetween the top div and the bottom div for several reasons. First is that it is simply an information that users are looking for, and by embedding the map here, users do not need to open a new tab and look for the location of Kumamoto. Second is due to the aesthetic reason. I was using a simple line to divide between 'website info section' and 'socials section', which did not look appealing. Finally, this can be said to any elements of footer/navbar, but the information in these sections are accessible by users on any pages, and thus, all of them must be useful for users.

### <ins>Food</ins>
![Mockup and Prototype for food section](readme_files/food.png)
When creating a exact same design prototype from the mockup, I realized that this page has many random spaces and lack in unity because there was no dark green background, unlike other pages. I thought that it would affect much when designing a mockup, but it felt very empty when I actually saw it on the web page. 
![An example of background](readme_files/food_bg.png)
I wanted to avoid just simply adding a green background because it would look very identical to the 'places section from Todo page'. Therefore, I first added a background as you may see in the image above, but it did not go well with my concept of keeping everything simple. After all, I decided to make a change by adding a dotted border to each section, so that the food divisions are more clear and each would stand out. I also removed a border from food images so that they would fit better.


###
<ins>Others</ins>
* __Homepage top__: In mockup, I included images slider at the top of home page so that users gets more attracted to Kumamoto with the beautiful photography. However, I realized that there is already a 'gallery section' at the bottom of homepage, and hence, a auto-play video is added to have some variety in content.

## Code Comments
### HTML
#### <ins>reset.css</ins>
reset.css is used to reset the styling of all HTML elements to a consistent baseline.
```HTML
  <link href="reset.css" rel="stylesheet" type="text/css" />
```
#### <ins>Embedding</ins>
As I wanted to have a google map on the website, I embedded the link from the google map website. This is part of the footer section.
```HTML
<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d214588.35994143016!2d130.56015059364606!3d32.820271937044026!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3540f414acf11b4f%3A0x1a51ced19bcf5c31!2sKumamoto%2C%20Japan!5e0!3m2!1sen!2sau!4v1668921553129!5m2!1sen!2sau" width="100%" height="auto" style="border-top: 0.5vh solid #536250; border-bottom: 0.5vh solid #536250;" allowfullscreen="true" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
```

### CSS
#### <ins>Responsive Design</ins>
Here is an example of how I created a micro destination site that is responsive to mobile. In this example, I changed the number of column of the gallery section. As the width of the device gets smaller, the number of column so that the size of the images gets bigger and users can see it better.
```CSS
@media screen and (max-width: 1200px) {
  #images {
    column-count: 3;
  }
}
@media screen and (max-width: 1000px) {
  #images {
    column-count: 2;
  }
}
@media screen and (max-width: 800px) {
  #images {
    column-count: 1;
  }
```
#### <ins>Container Class</ins>
This class was utilized in almost all pages of the website to have some common styles for dividing sections. When necessary, I adjusted specific styles for the container on each page, like the example below.
```CSS
.container {
  background: #FFFDF5;
  margin: 10%;
  position: relative;
  display: flex;
  padding: 3%;
  width: 80%;
  justify-content: space-between;
}
.food .container {
  border: 5px dotted #AD9579;
  border-radius: 30px;
}
```
#### <ins>Hovering</ins>
Hovering effect is very important for enhancing user experience, and thus, I tried applying it to different parts of the website.(but not too much) These include: changing color of buttons, menu dropdown, removing filter from images.  
```CSS
button[type=submit]:hover {
  background-color: #FFFDF5;
  color: #21231D;
  border: 1px solid #21231D;
}
.dropdown:hover .dropdown-content {
  display: block;
}
#images img:hover {
  border: 1px solid #FFFDF5;
  filter: none;
  cursor: zoom-in;
}
```
## Reference List (APA 7th)
Calendar, J. T. F. (2022, September 23). Hinokuni Matsuri. Ohmatsuri.com. https://ohmatsuri.com/en/articles/kumamoto-hinokuni-matsuri

JavaScript - How to Create a Responsive Hamburger Menu with HTML, CSS, & JavaScript. (n.d.). Www.youtube.com. Retrieved November 21, 2022, from https://youtu.be/flItyHiDm7E

KUMAMOTO FIRED UP! (n.d.). KUMAMOTO FIRED UP! https://firedup-kumamoto.com/column02/

nekosenbei. (n.d.). O-DAN - Cross-searching for high-quality free stock photo site. O-Dan.net. https://o-dan.net/en/

omni-links-europe. (2019). Kumamoto prefecture: rich in beauty and history PeakExperienceJapan. Peak-Experience-Japan.com. https://www.peak-experience-japan.com/blog/508

Unsplash. (2022). Beautiful Free Images & Pictures. Unsplash.com; Unsplash. https://unsplash.com/

Wells, T. (2022, January 3). Create a simple responsive image gallery with HTML and CSS. Medium. https://timnwells.medium.com/create-a-simple-responsive-image-gallery-with-html-and-css-fcb973f595ea

‌
‌