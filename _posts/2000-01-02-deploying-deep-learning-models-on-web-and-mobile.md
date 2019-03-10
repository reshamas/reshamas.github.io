
<p>
<img src="../assets/images/app_food_web.png" width="85%" height="85%" style="padding:1px;border:thin solid black;" align="center"> 
</p>


This article was co-authored by [Nidhin Pattaniyil](https://www.linkedin.com/in/nidhinpattaniyil/) and [Reshama Shaikh](https://reshamas.github.io).


## Jump to:
1. [Training the Classifier](#training-the-classifier)
    1. [Sample Heading](#sample-heading)
    
2. [Deploying the **WEB** App](#deploying-the-web-app)


3. [Deploying the **MOBILE** App](#deploying-the-mobile-app)
- repo: [mobile-deep-learning-classifier](https://github.com/npatta01/mobile-deep-learning-classifier)

 
## Training the Classifier
### Sample Heading

- repo: npatta01/[web-deep-learning-classifier](https://github.com/npatta01/web-deep-learning-classifier) 

xxx


---

## Deploying the Web App
- We are using this repository as a template: [web-deep-learning-classifier](https://github.com/npatta01/web-deep-learning-classifier) 
- Our web app can be found here:  [food-img-classifier](https://food-img-classifier.herokuapp.com)

[Heroku](https://www.heroku.com/) was utilized to deploy the web app.

### Input to Heroku App

This output file, **`model.pth`** is the input to the Heroku app.  


### File Changes
:point_right: To run your own mobile app, you need only make the following adjustments:

1.  In this file [src/config.yaml](https://github.com/npatta01/web-deep-learning-classifier/blob/2a30245d467b51705e51aa7a71658dd407dc49cf/src/config.yaml), updates these fields:
- `title`
- `description`
- `about`
- `code`
- `sampleImages`

2.  In this file [docs/2_heroku_app.md](https://github.com/npatta01/web-deep-learning-classifier/blob/e9a41bc0a09fe98d44a168b1d64323dad2d074e0/docs/2_heroku_app.md), the following changes need to be made:  
- Replace our app name with your app name:  `APP_NAME="food-img-classifier"`
- Example:  if you classified birds, your app name could be `APP_NAME="bird-img-classifier"`

### Heroku Setup

If you don't have a Heroku account, create one here: [www.heroku.com](https://www.heroku.com/).  Each line can be copied and submitted.  

**Reminder:** in your code, you will have updated your `APP_NAME` 

```
wget -qO- https://cli-assets.heroku.com/install-ubuntu.sh | sh
heroku login
heroku container:login

APP_NAME="food-img-classifier"
heroku create $APP_NAME

heroku container:push web --app ${APP_NAME}

heroku container:release web --app ${APP_NAME}
heroku open --app $APP_NAME
heroku logs --tail --app ${APP_NAME}
```

Note:  After 15 minutes of inactivity, Heroku will suspend the app.  The next time the web app is called, Heroku will restart the app.  There could be a slight delay in starting the app.
 
### Our Flask Web Application
- Our Flask web app is available here on Heroku:  
[**food-img-classifier**](https://food-img-classifier.herokuapp.com)
- Give it a try!  Upload an image or add a URL.


---

## Deploying the Mobile App
<p>
<img src="../assets/images/demo.gif" align="center"> 
</p>
