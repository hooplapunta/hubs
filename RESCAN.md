# Notes for REscan
Please only refer to the `hubs-cloud` branch for our code and mods.

The prototyping environment for the tools developed is Mozilla Hubs, which allows for multiplayer VR interactions and observation. Hubs comes with a environment and scene editor tool called Spoke, a REscan exported environment can be imported here for the purposes of testing.

https://hubs.mozilla.com/docs/welcome.html

Hubs allows for images, videos, PDFs, 3D models and other media to be displayed. However, for other complex interactions like the panel and spawning items requires additional code to be added to Mozilla Hubs.

A modding guide that shows how to inject additional javascript into the web application was followed in order to build out our prototype:
- http://www.aelatgt.org/Custom-Hubs-Components/docs/HijackingHubs.html
- https://github.com/colinfizgig/Custom-Hubs-Components

As such, the source hub.js file is modified to facilitate the injection code. Such an injection will only work on a custom Mozilla Hubs server. Our team utilized the AWS solutions provided by Mozilla Hubs. The custom client must then be built and deployed to the srever.
- https://hubs.mozilla.com/docs/hubs-cloud-custom-clients.html

Please find the files relevant to our prototype mod in the /mods folder. This folder (or rather the whole repository) is hosted with GitHub pages so that it may be retrieved by the the custom client. Within, the slideshow components (slideconfig.js, slideshow-template.js and hubs-slide-show.js) make up the new component that can be summoned via the `mod_addSlides();` command in the browser console, or if someone types `addSlides` into the Hubs chat feature. Please see the modding guide for full details about the functions of this slideshow component.

For now, the following features were used to simulate and test the designs in the prototype:
- a floating panel is shown that stays put when released instead of dropping from gravity
- invisible buttons to the left and right to progress forward or back in the slideshow.

Future improvements should be made if continuing to use this mod approach:
- a whole component may be written instead of using injection
- actual UI may be drawn instead of using static images
- back/forward buttons may be resized and repositioned based on the current slide
- spawning can be re-included