[()]
>Insert logo here

# Peanuts

**Disclaimer: currently proof of concept**

Peanuts is a cloud-enabled, mobile-ready, offline-storage, azure web server powered grocery management app and IoT kitchen camera that provides a seamless end-to-end grocery experience.

  1. Tracks stock and quality of kitchen groceries
  2. Employs data-analytics magic to optimise your food consumption and grocery purchasing patterns

## Proof of concept demo

[![Link to proof of concept](https://appservice.azureedge.net/images/linux-landing-page/v3/python.svg)](https://flask-iot-kitchen.azurewebsites.net/)

## Video demo

> (Insert video here)

Markdown is a lightweight markup language based on the formatting conventions that people naturally use in email.  As [John Gruber] writes on the [Markdown site][df1]

> The overriding design goal for Markdown's
> formatting syntax is to make it as readable
> as possible. The idea is that a
> Markdown-formatted document should be
> publishable as-is, as plain text, without
> looking like it's been marked up with tags
> or formatting instructions.

This text you see here is *actually* written in Markdown! To get a feel for Markdown's syntax, type some text into the left window and watch the results in the right.

### Tech

Peanuts uses a number of open source projects to work properly:

##### Software
* [Flutter](https://flutter.dev/) - HTML enhanced for web, mobile and desktop apps!(to create the mobile user interface )
* [Flask](https://flask.palletsprojects.com/en/1.1.x/) - python web app framework
* [Azure web server] - platform to host web server
* [MongoDB](https://www.mongodb.com/) - Popular NoSQL document database
* Data analytics (not in proof of concept) for tracking and recommending consumption pattern

##### Hardware
* [Nvidia Jetson Nano](https://developer.nvidia.com/embedded/jetson-nano-developer-kit) - small, powerful computer that can run multiple neural networks in parallel for applications like image classification, object detection, segmentation, and speech processing

    *Software*: [YOLO](https://pjreddie.com/darknet/yolo/), [OpenCv](https://opencv.org/)
#### UI/UX
* [Figma](https://www.figma.com) - Design, prototype, and gather feedback all in one place

## How tech work
- Household's inventory is stored in MongoDB cloud and on household members' mobile devices for offline use (syncing with database)
- Items are added to the database via scanning of a QR code containing a temporary link to a receipt of groceries from local supermakret
- This temp link is created from the supermarket's server, and essentially outputs the receipt in JSON format to the mobile app. The mobile app would post this to our flask server hosted by Azure and in turn post this to MongoDB
- Cameras are connected to a Jetson Nano houses an object identification model that identifies the food that a member of the household is going to comsume. It would post an update to MongoDB of the items that are just consumed Front end slider mechanisms can also be used
- Inventory data from supermarkets helps to recommend when and where is best to purchase

## How it flows
[![Presentation slides](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAMQAAAEBCAMAAAAQKvrqAAAAe1BMVEX/wQf/////7LP/oAD/vgD/9dv/8tH/6LX/7MH/vwD/5Kv/7cT/wwf/2Xn/mgD/7dH/zHj/663/qwP/+OX/+OT/xy3/5Kj//PX/89X/02f/xSL/3pD/+ev/2X//6rr/1nP/24f/0F3/35n/4qH/zE3/77r/yWv/lgD/pAAJVuUDAAAEe0lEQVR4nO3ciXLaMBAGYIkqUNEkbYLBIeHI1eP9n7A2GLDwqbUd7e/Z/wF29M3KgrElKX2VOHqafn0W18PwinIAs/WzNSGy7qTIIRZ7Y6xVIWLvJlEviFcTBnBE/H7ooDghoqUJRjggJh0UGWIasA0ZooNCZYaQhAwxeaA+3QdEFNiQIci9OCCWQefSBUFVpIiX0I04I4iKBLEJbrggaIoEsQ09mfII0tOtdBzekEdQeqH0LvxschCEXii9Z9YJQi9U+PW1gPDuhYpDA9JcIXwVisECW0R4KlTwvxxpCgg/hbrhifBSsEX4KPgiPBSMEe0VnBGtFawRbRW8ES0VzBHtFNwRrRTsEW0U/BEtFACIZgUColEBgWhSYCAaFCCIegUKolYBg6hT4CBqFECIagUSolIBhahSYCEqFGCIcgUaolQBhyhT4CFKFICIogIRUVBAIiYPmxEgrnoBinAVqAhnRsEi8r3AReR6AYy49AIZce4FNOKkwEZkCnDEUYGOOCjgEamCCeLzFz1/NjwQSj3ek/P3JxfE7eM3au7ZIDooGCHoCk4IsoIVgqrghSAqmCFoCm4IkoIdgqLghyAoGCL8FRwR3gqWCF8FT4SnginCT8EV4aVgi/BR8EV4KBgj2is4I1orWCPaKngjWiqYI9opuCNaKdgj2ij4I1ooABDNCgREowIC0aTAQDQoQBD1ChRErQIGUafAQdQogBDVCiREpQIKUaXAQlQowBDlCjREqQIOUabAQ5QoABFFBSKioIBEXCswEVcKUISrQEU4ClhEXoGLyCmAERcFMuKs6ISwvV7yS7huN1N0QBj79j773ltm72/WeyRHBRlh1TwunNnrmHiufLtxUFARZtu34Jit72BSBRFh5sMYtJ4TFDTEcAaSgrRD2d4NZ9D6zvu5+EfqxJAGrb2HY278EeZjWMSH94AICLtpHkiXbHznEwFhP4c1aP3pqaAgXoZGvHwBYjU0YjU8wsyGRsx8RyQIQQhCEIIQhCAEgYFY9PXaaREQserr/d8qIML73URV0bkgBCEIp6ggBCEIt6ggBCEIt6ggBCEIt6ggBCEIt6ggBCEIt6ggBCEIt6ggBCEIt6ggBCEIt6ggBCEIt6ggBCEIt6ggZKuQ1tGunz1buyggYpAIQhCCEIQgBCEIQYwHMYpjm+M4QDuGo8yjOFQ+juP9o7hogduVF8RODPlT4fsjQUYMqCAYqAg+F/J0QSh7O8TVSLf+F1V1QajskqofPYV2SVVnBIPrwvpAcIkguEQQXCIILhEElwiCSwTBJYLgEkFwiSC4RBBcIgguSRARPiJSG3zERsWhx9A9sdJL8vtDHrFLrfQeHbFPEDvwh8LsEkSM3ok4QegttMJudYrAXmTN5oDQL8AKk241OXxZx11lk/X1hMD962GiM0JPQRVmqi+IRAE4o2xmOCF0tIRrhlmeDixctsy8YjXDmtfz0HP7fhb7Ll+TvzLpF/R97rJfZ/NSPFs/9/qFfZjY5/XM2ZRR2IEVR09T1nmKCrtK/gOKTqnKagFJiAAAAABJRU5ErkJggg==)](https://docs.google.com/presentation/d/1SoCnFtdbRhlorfWPjvCNIBzC6zK7TQDaetXBJoY2R90/edit#slide=id.g893141ec5d_8_10)
[![Mock up]]()
### Installation

## Credits
- [Chia Yong Kang](https://github.com/ExtremelySunnyYK)
- [Tan Jia Yue]
- [Hoe Jun Leong]
- [Joseph Low]
- [Dhanush Kumar]
### Todos

 - Write MORE Tests
 - Add Night Mode



[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)


   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>
