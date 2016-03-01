# Chat Roulette Node.js Server
This is a server side of [iOS Chat Roulette App]( https://github.com/Shahan/iOSChatRouletteClient ).
Actually, it's based on [OpenToK WebRTC Demo]( https://github.com/opentok/OpenTokRTC ) and almost work the same. 
Now this server also works as a website, but you can always remove this feature.

## Roulette Settings
As far as this server based on a room chat service, it works in the same architecture, but with some changes for Roulette features.
To find new partner, client just need to join roulette room. By default, it's name is `roulette`
You can always change it in config file `config.js`:
`config.web.roulettename = "any_name_that_you want";`

## File Overview
* `Procfile` is required to run the nodejs app on Heroku
* `package.json` contains all npm modules to run the app
* `app.js` contains all server side code  
* `config.js` contains configurations: TokBox credentials, p2p mesh support, Redis support, reserved rooms, etc.  
* `lib` folder contains all the code to handle configurations: p2p mesh support, Redis support, reserved rooms, etc.   
* `views` folder contains the html template for the app
* `public/css` folder contains all the css for the app.    
  Look for files with `.scss` extensions. `.css` files are generated from sass.
* `public/js` contains the front end code and interactions with OpenTok SDK. 

## How to run the app:
1. Clone this repo
2. Get my API Key and Secret from [TokBox]( http://TokBox.com )  
3. Replace `OTKEY` and `OTSECRET` with your corresponding API Key and Secret in `app.js`  
4. Run `npm install` to install the necessary packages  
5. Start the server with `node app.js`  

## Deploying this app to your own host (Heroku):
1. Clone [this repo]( https://github.com/opentok/OpenTokRTC )  
2. Go into the cloned repo: `cd OpenTokRTC`  
1. Create a heroku app: `heroku create appName`  
2. Add your TokBox apiKey and secret credentials in `config.js` or set [Heroku's environment variables](https://devcenter.heroku.com/articles/config-vars)   
2. Push to remote heroku repository: `git push heroku master`  
3. Visit your app  
