facebot
=======

A facebook automated profile and reconnaissance system 

this simple python script allows for automated profile activities such as: sending friend requests,populating profile information from a configuration file,  populating content on the wall using the following content: youtube video links, news and quotes at random intervals . and crawling friends information on demand  by just providing a profile link  to the bot in addition it performs friend of friend crawling capabilities. below is the main tool menu: 
```
usage: facebotv2.py [-h] -c CONFIG [-b] [-B] [-t] [-cm] [-tm TARGET_MODE]

Welcome to facebot a facebook recon tool
                .
               _|_     LETS BE FRIENDS.... ?.
        /\/\  (. .)  /
        `||'   |#|
         ||__.-"-"-.___
         `---| . . |--.             | : : |  |_|
             `..-..' ( I )
              || ||   | |
              || ||   |_|
             |__|__|  (.)

optional arguments:
  -h, --help            show this help message and exit
  -c CONFIG, --config CONFIG
                        read config file
  -b, --build_profile   build "about me" section of the profile
  -B, --bot_mode        enables bot mode. this mode populates random content to the wall/ sends friend requests  in order to impersonate a real user
  -t, --test_mode       test mode
  -cm, --campaign_mode  enables  friend campaign mode. bot goes out and gathers friends of friends
  -tm TARGET_MODE, --target_mode TARGET_MODE
                        enables target mode. give it a friend profile id and the bot will crawl all infoz on his profile 


```

facebot is divided by two components. the masterbot.py script is the one that delivers instructions to the client bots. in this case the client would be facebotv2.py. 

## how to use this tool:

'Warning: before executing masterbot you need to create the DB in order to store all the loot. the database squema in pfd form is shown on the repo'.


1- execute masterbot. once masterbot has loaded it will listen on port 1337 and ready to dish out instructions 
```
python masterbot.py 
Masterbot listening on: 127.0.0.1:1337
```
2  execute facebot client by providing a config file and a mode to operate on . there is a sample config file available  for example purposes. in this case Bot mode was activated which populates content to the wall such as youtube videos, news and quotes. 
```
python facebotv2.py -c emma.cfg -B
```

#the Configuration file 
a sample config file has been shared  however the fields above need a bit more of explanation 
gender: 
          1 : female
          2 : male
relationship 
          1 : single
interested
          1 : women
          2 : men
current_city : "facebook id of the city as per facebook"
hometown : "facebook id of the city as per facebook"
