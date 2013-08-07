#August 7th 2013
=======
Date: 2013-08-07


### Tools
===
* [Live Style](http://livestyle.emmet.io/) - Currently Free, but will be paid at some point - Beta
* [Live Sync](https://github.com/sloped/live_sync) - Open Source/Self Authored/ Revision 0237b5616
* [Sublime Text](http://www.sublimetext.com/) - $70 - Theme Flatland, Color Scheme Dark
* Rsync
* Chrome
* [Watchman](https://github.com/facebook/watchman) - Open Source/No Binaries so has to be built

### Process
====

Each project has it's own top level folder. Inside of that folder I will have the following directories, if necessary:

* A copy of the project directory checked out of version control. All of our project documentation is included in this folder. (Only on Work Projects)
* A **design** folder that contains PSD Comps, assets, ect. 
* A **remote** folder. This folder contains individual folders for each remote source I may work on. 

All work is done within individual folder inside of Remote. I prefer to keep a local copy of the files from the server. I do all version control operations directly on the server. 

To manage keeping my local and the server files in sync I use a combination of tools. 

 * Live Sync -  This program was written to handle the task of actually performing the syncing of files and folder to and from the server. 
  * Within each directory within **remote** I can run the following command. 
  `setup_live_sync server:/remote/file/path/`
  * Then, inside of that directory I can run `live_sync -s` to pull down all the files form the remote directory. 
  * I will then open the directory in Sublime Text, modify the project file as necessary, Save the project folder I keep version controlled but seperate from actual working files
  * When I wish to start syncing files I run `live_sync -w` This creates a watchman trigger which runs `live_sync -r` as files change. 
  * When I start working on a site, I open Chrome Dev Tools, click on Live Styles, and activate Live Styles and associate css files on the server with css files in my editor. This allows me to immediately see changes in my browser and make changes in dev tools that will be instantly reflected in my editor. 
  
## Benefits
===
* Don't have to think about keeping the server in sync, done automatically
* Live Sync is smart enough to disable the watchman trigger and enable it only after the rsync process is completed
* Dev Tool Editing is great for perfecting layouts
* Instant Feedback to edits make in the edior. 
* Local files mean fast searching through Sublime Text Projects
  
##Shortcomings
===

* Have to manually pull down all changes recieved when I update my server files through version control to bring back any changes made by others
* Requieres building binaries of watchman 
* live_sync is sort of fragile
* Instant Feedback of styles not possible in IE or Mobile at this time. 

