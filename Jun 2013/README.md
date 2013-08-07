#June 2013
===

Unsure of the exact date as I update this prior to creating this repository. 

  
### Tools
===
* [Live Reload](http://livereload.com/) - $9.99
* [Live Sync](https://github.com/sloped/live_sync) - Open Source/Self Authored/ Revision bec5b7731252
* [Sublime Text](http://www.sublimetext.com/) - $70 - Theme Flatland, Color Scheme Dark
* Rsync
* Chrome

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
  * The next step is to add the project file to Live Reload. Live Reload will watch a project directory for you and update any browser connected to it in real time. It can also execute a command when files change. I ask Live Reload to run `live_sync -r` after a file changes. This uploads all changes to the remote directory. 
  * In Chrome/Safari/Firefox I'll install and activate the Live Sync extention on any files I'm working on. This lets me edit CSS and see all my saved changes immediatly and also refreshes the browser whenever I save a static file that requires a reload such as .html or .js files. 
  ## Benefits
===
* Don't have to think about keeping the server in sync, done automatically
* Live Reload can be used with a js snippet to allow refreshing stylesheets immediatly in IE/Mobile Devices
* Local files mean fast searching through Sublime Text Projects
  
##Shortcomings
===

* Have to manually pull down all changes recieved when I update my server files through version control to bring back any changes made by others
* Live Reload senses file changes made by `live_sync -s` and reruns the `live_sync -r` command which can potentially cause a file to be overwritten before it's synced to the local directory
* Can't utilize any sort of dev tool editing
* live_sync is sort of fragile