# ci-me-dice-on-demand
[![Build Status](https://app.travis-ci.com/camilotorres97/ci-me-dice-on-demand.svg?branch=main)](https://app.travis-ci.com/camilotorres97/ci-me-dice-on-demand)

Sample Python app for learning CI. You will get a flexible dice on demand! 

This application is written in Python and uses Flask as the web framework. It serves a single HTML page.  
Gunicorn is used for the production server.  
Continous Integration is managed using Travis-CI  
Continous Deployment is managed using Heroku  

# :page_with_curl: Instructions
1. Clone this repo
2. Navigate to the directory
3. Execute this:
```
# This will create and activate a virtualenv. Using a virtual environment allows you to manage your project’s dependencies without messing with system-level files shared by all applications.
python3 -m venv venv
source venv/bin/activate
# Install dependencies
pip install -r requirements.txt
# or if you're still using python 2
pip3 install -r requirements.txt
```

Now that all dependencies are installed, we can run the program!

4. To test the app:
```
python3 -m pytest -v tests/test_dice.py
```
5. To run the app:
```
# You can define FLASK_ENV environment variable to automatically reload your app when changes are detected so you don't need to restart it
FLASK_ENV=development flask run
```

6. Go to the URL provided by the app (i.e. `http://localhost:5000`)

# Usage

1. First off, enter the number of sides of your dice. (Some games might require you to use 20-sided dice)
2. Now, click on the `roll` button!
3. You should see a message on the screen - "You Rolled a ..."
4. That's it!

# :mortar_board: Your task
- Clone this repo
- Create a simple CI pipeline for this application on [Travis CI](https://docs.travis-ci.com/) with (at least) the following steps:
    - Checkout
    - Test
    - Slack notification on success or failure
    - Deploy this app to [Heroku](https://www.heroku.com/) on success (yay! Continuous Deployment!)
- Bonus points:
    - Add the [Travis status image](https://docs.travis-ci.com/user/status-images/) to your Readme
    - Add Pull Requests flows to your CI
    - Build a container for your app in your CI flow
    - Deploy the container to Heroku

## Deliverable
Send us:
- Your repo URL
- Your Travis URL
- Your deployed app URL

# :shipit: Suggestions
- Read (at least) the [Travis CI Core concepts for Beginners](https://docs.travis-ci.com/user/for-beginners/) and the [Travis CI tutorial](https://docs.travis-ci.com/user/tutorial/). 
    - Ask yourself, if we didn't provide these links, would you have looked for them?
    - How should you approach a completely new tool?
    - Look for the Slack and Heroku integrations in the Travis docs, they are very simple to navigate and easy to follow
- Google *everything* you don't know (Gradle, Travis, and Heroku are probably new tools for you, do you understand their purpose?)
- Remember, you cannot automate something you haven't done it manually first (I mean, you could, but you would struggle more than is necessary)
- Send too many Slack notifications and people will start ignoring them (nobody wants to see your 20-something attempts at setting up Slack notifications, use a test channel or your private conversation)

# :safety_vest: Hint
You need to connect your GitHub (or any VCS) account with [Travis CI](https://app.travis-ci.com/), investigate about stages, phases and jobs (at least) in Travis-CI and how to write a build pipeline that deploys to Heroku (CD), send build notifications on success/error using Slack. Also, using environment variables in Travis-CI will be needed. Good luck!

PS. The **Procfile** is empty but you will need it also :) Investigate why.
