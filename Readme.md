
pkAppMan

What is it?
An application written in gambas basic for linux systems that use the new
policy-kit for running gui applications as root from a non terminal environment
Ie. from a menu or a desktop launcher
If you have used GKSU in the past before it disappeared 
and pkexec became the alternative but don't know how to
configure pkexec then you will want this app.

with GKSU you could just set a launchers command to 
gksu /path/appname
and the app would launch fine as root after asking you for your password
pkexec on the other hand is a bit more complicated as you have to set up
a policy file for pkexec and add allowed apps to it before it will work.

That's where this app comes in.
Features.
-- Creates a new pkexec policy file if one does not exist or will
load your existing one if you have one.

-- after first launch (must be run from terminal as root)
it adds the gambas runtime to the pkexec list of apps and
after that if not run as root (ie just double click app) it will 
relaunch itself with the pkexec prefix to ask for password.
Also with the gambas runtime added any gambas app that wants
root access can use pkexec prefix.

-- pass a file as an argument, if launched with a file name as 
it's argument Ie. 'pkAppMan.gambas "/usr/bin/gedit"' then it will
auto add the app to the list. the means you can right click any app
on your computer and Select "Open with pkAppMan" to load pkAppMan 
with said file auto added.

-- Edit description and message.
The description is just so you know what it is in the list
the Message is what is displayed when asked for password.


Requirements:
gambas3-runtime
'sudo apt-get install gambas3-runtime'

Important: on 1st ever running of the application you must run via sudo from a terminal.
ie.
sudo /path/pkAppMan.gambas
Or
sudo gbr3 /path/pkAppMan.gambas

On the first launch it will add gbr3 the gambas runtime exe
to the list of pkexec allowed commands and after that you can just 
double click the pkAppMan.gambas file and it will be able to
elevate your privilages.

Instructions..

Simply launch the app and add a rule, then set the full path to the executable file you wish to run
Give a short desription (just so you know what it is) and set a message.
The 'Message' is what is displayed when the gui you want to run asks for password

Then Save.

Now you can make a launcher or menu item using pkexec.
Eg. to make a launcher for pluma text editor as root
add a rule and set it to '/usr/bin/pluma' (it should be there)
Then set the launchers command to 'pkexec pluma'
Or 'pkexec pluma "<path to file>"' to open a file

Downloading...
Download pkAppMan.gambas for the standalone application file.
Download pkAppMan.zip for the programs Gambas source code directory.


Written by Bruce Steers
