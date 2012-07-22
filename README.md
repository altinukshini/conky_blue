#About Conky#

Conky is free software and runs in X on Linux and BSD. Originally a fork of Torsmo, Conky's torsmo-based code is BSD licensed. New code in Conky has been licensed under the GPL 3.0.

Since its inception, Conky has changed significantly from its predecessor, while maintaining simplicity and configurability. Conky can display just about anything, either on your root desktop or in its own window. Not only does Conky have many built-in objects, it can also display just about any piece of information by using scripts and other external programs.

For more visit: http://conky.sourceforge.net/

##Configuration Files##
<img src="https://github.com/altinukshini/conky_blue/raw/master/screenshot.png" align="left" style="paddig-left: 10px;" alt="Screeshot" />
clock_rings.lua & conkyrc

Clock Rings by Linux Mint (2012) reEdited by Altin.

This script draws percentage meters as rings, and also draws clock hands if you want! It is fully customisable; all options are described in the script.
This script is based off a combination of my clock.lua script and my rings.lua script.

**IMPORTANT**: (about conky_rings.lua) If you are using the 'cpu' function, it will cause a segmentation fault if it tries to draw a ring straight away. 
                    The if statement on line 324 uses a delay to make sure that this doesn't happen. 
                    It calculates the length of the delay by the number of updates since Conky started. 
                    Generally, a value of 5s is long enough, so if you update Conky every 1s, 
                    use update_num>5 in that if statement (the default). 
                    If you only update Conky every 2s, you should change it to update_num>3; 
                    conversely if you update Conky every 0.5s, you should use update_num>10. 
                    ALSO, if you change your Conky, is it best to use "killall conky; conky" to update it, 
                    otherwise the update_num will not be reset and you will get an error.

To call this script in Conky, use the following in your conkyrc:

	lua_load ~/.fluxbox/conky/conky_blue/clock_rings.lua
	lua_draw_hook_pre clock_rings

###Changelog:###
* v1.0 -->  Original release (30.09.2009)
* v1.1p -->   Jpope edit londonali1010 (05.10.2009)
* vX 2011mint --> reEdit despot77 (18.02.2011)
* vX 2012 --> Altin reEdit (22.07.2012)
 	* Added weather function (Accu Weather)
 	* Added battery monitoring
 	* Syslog monitoring
 	* Running processes monitoring
 	* Rearanged rings
 	* Exctra network functions/monitoring
 	* Changed Fonts

##SETUP##

Because I have used this conky configuration with fluxbox I have put it under .fluxbox folder on my home directory.

1) Create a directory named **conky** under **~/.fluxbox**

2) Paste the **conky_blue** folder under **~/.fluxbox/conky**

3) Copy and paste all fonts from **conky_blue/fonts** directory to your fonts directory **~/.fonts**

4) Change weather location by editing **conky_blue/accu_weather/rss/acc_rss**

Replace your accuweather rss address in line 94

	address="http://rss.accuweather.com/rss/liveweather_rss.asp?metric=1&locCode=EUR|XK|298740|PRISTINA"

5) Install conky: 

	$ sudo apt-get install conky

6) Start conky with this configuration:

	$ conky -c ~/.fluxbox/conky/conky_blue/conkyrc
