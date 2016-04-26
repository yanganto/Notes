# Nothing but Inspiration
* Cindy Chi
* 2015 Visual Design Conference Summery
* Orgin form CSS founder, JS master
* B307
---
# How to design a innovation product
## must of speaker point out the performance issue in font end
* shirnk the number of requests, ** should less than 15 in each page**
* upgrad the loading speed
* each page size < **400k** (a example case of Pizza is 600K)
* loading page in **2 ~ 3** seconds
* each 100ms, 1% customer loose
* 1s quick, 2% _cummertion rate_ enchance
---
# a good design should balance user needs and Development convience
- performance budget
  - CSS
  - **images**
  - JS
  - font
- [webpagetest](http://www.webpagetest.org)
- **get ur design in to __Code__ earlier**
---
# How to do it.
* lazy loading
* Magazine style (**Content First**)
  * layout should serve content, _not in small div_
    * in New css(3), Support text warpper
    * css: **shape-outside**
    * css form editor
    * [can I use](http://caniuse.com/)
  * rotate a picture
    * css: transform : rotate
  * multi-column
    * css: multi-column
  * view port unit
    * wh, wv, vmin, vmax
    * on resize automatically
---
# multi-screen  
## must of user access the website via different kind browser (40%?)
  * do **NOT** save data in local, but in the **Cloud**.
  * _think the smart phone as a magin can_ [iPhone 5S Ads]()
---
# Context
## How to defines context
  **time**, **location**, distance, direction, and more ...
  - click -> press, tap
  - event driven web disign, EX: upcomming event has different view
  - using context Map, to analysis each page in different stage
  - social service may use the distance
  - sort by different view point, and should show the **Sorting Info** in the header
  - the bottum in _easy/ok to touch area_, in small phone 60% user use **single** hand
  - Phablets, 74% user use **both** hands
  - floating bottom
  - hover event _not in phone_, avoid it
  - make sure the bottun larger than 0.7cm, 44px (web), 44point (iOS), 48dp (Android)
  - do NOT show too much things in a single page
  - slow down user, if somethin is really important, ex: delete github repo
---
