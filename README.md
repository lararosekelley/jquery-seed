#jQuery Seed

###*Testable plugins in the blink of an eye*

**by Ty-Lucas Kelley**

---

This project is a skeleton for an organized and testable jQuery plugin (or a full web app with not too much extra work). 
It can be used to quickly bootstrap a plugin and development environment.

The project contains everything you need to instantly get started with your jQuery plugin, get it tested, and make a demo.

The sample app provided demonstrates a trivial plugin, which changes text to "Hello, World!" when called.

###The Setup

Just clone this repository and install the dependencies:

**What you'll need**

1. [git](http://git-scm.com/)
2. [node.js](http://nodejs.org/)
3. [npm](https://www.npmjs.org/)

**Clone jquery-seed**

Use git for this part:

    git clone http://github.com/tylucaskelley/jquery-seed
    cd jquery-seed

**Node modules**

The included `package.json` file takes care of all the annoying stuff for you! All you need is:

    npm install
    
(Beatles fans may argue that you need love as well)

After that, assuming there were no problems, you'll have a new directory that looks like this:

    node_modules/
        bootstrap/
        chai/
        chai-webdriver/
        chromedriver/
        http-server/
        jquery/
        jshint/
        mocha/
        node-http-server/
        normalize.css/
        selenium-webdriver/
        
Not all of these modules are necessary, so if you don't need or want one, just run:

    npm uninstall <module> --save-dev

to remove it and update your `package.json` accordingly.

###Running the App

Everything is preconfigured for you (with a very simple development server), so just start things up with this:

    npm start
    
and go to http://localhost:8080 to see the sample project in action.

###Project Structure

    app/                    --> All of the app source files
        css/                    --> CSS stylesheets
            main.css                --> Sample CSS
        img/                    --> Images
            js.jpg                  --> Sample image
        index.html              --> Sample index page
        js/                     --> JavaScript source
            hello.js                --> Sample jQuery plugin
        package.json            --> NPM stuff: go here for jshint, dependencies, and app info
        README.md               --> Sample README
        test/                   --> All test source
            mocha.opts              --> Mocha config file
            spec/                   --> Test files
                tests.js                --> Sample e2e tests
                
###Testing

Testing your plugin is made easy thanks to JSHint, Chai, Mocha and Selenium-Webdriver. To run your tests in chrome, simply type:

    npm test
    
which will first run JSHint, based on the configuration set in `package.json`:

    "jshintConfig": {
        "node": true,
        "unused": true,
        "undef": true,
        "globals": {
            "$": false,
            "jQuery": false
        }
    }

and then the end to end tests (written using the `selenium-webdriver/testing` module + `chai` and `chai-webdriver` for assertions). 
You don't need to have a server running, as the included tests will take care of this.

You can configure Mocha to use different reporters, globals, and default timeouts by editing the `mocha.opts` file in `test/`, which looks like this by default:

    --reporter nyan
    --timeout 0

The tests run in Chrome by default, but Firefox or another browser can be used, with some small additional setup:

1. Download the selenium standalone server from [here](http://selenium-release.storage.googleapis.com/index.html) and run it using:

        java -jar /path/to/selenium-server-standalone-X.xx.x.jar
        
2. Change your test code to use Firefox instead of Chrome:

        var driver = new webdriver.Builder().
            withCapabilities(webdriver.Capabilities.firefox()).
            build();
            
3. Run your tests the same way: `npm test`.

###Changing things

The nice part about this seed app is that everything is modular, thanks to npm:

* Don't like Chai? Use Assert instead.
* Don't like http-server? Write up your own.
* No need for Bootstrap? `npm uninstall bootstrap`.
* Want to plug in AngularJS and Protractor to make a full blown application instead of a plugin? Easy as 1, 2, `npm intsall`.