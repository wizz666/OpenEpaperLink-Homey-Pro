# Display parsed version in Homey Pro
### The code is for Solum 2.9" BWR and BW displays but can be modifyed to fit other displays.<br>
This guide is for the OpenEPaperLink homey app.<br> [![Static Badge](https://img.shields.io/badge/Homey_Apps-blue)](https://homey.app/sv-se/app/nl.wiggert.OpenEPaperLink/OpenEPaperLink/)
<br>
Information regarding Json template <br> [![Static Badge](https://img.shields.io/badge/Json_template-grey)](https://github.com/jjwbruijn/OpenEPaperLink/wiki/Json-template)<br>
This is an good online editor <br> [![Static Badge](https://img.shields.io/badge/JSON_Beautifier-green)](https://jsonbeautifier.org/)<br>

In this section you change the text and insert the card from the Homey app that you want to be displayed.<br> 
Here you also change the positions for the text and for the card so that it fits on the display.<br>
It is important that the code below is between brackets [ ] otherwise it will not work, you can see how it looks in the code example above.<br>
```
     {"text": [10,20,"<b>Add your text here</b>","t0_14b_tf",1]},<br>
    {"text": [95,20,"<b>Here you add the card from homey</b>","t0_14b_tf",2]},<br>
```
If you want to add som text or sybols after the card you can do that.<br>
Just do it as in the picture below that shows the code.<br>
Here i added degrees (°) and also percent (%) and text for the the currency in my case SEK (Kr)<br>
Add whatever you want to customize it to your needs.<br>
Be careful not to get a lot of white space in between because it shifts the code.<br> 
This will only appear after you have uploaded the code to your AP and it has sent the code over to your display.<br>
Feel free to change and use the code as you like.<br> 

⭐ All credit for the code goes to Fredrik Tornell.<Br>
⭐ All credit for the pictures in this guide goes to Aaron Christophel @atc1441 [![Static Badge](https://img.shields.io/badge/Github_Page-blue)](https://github.com/atc1441)<br>

<img width="500"  alt="display" src="Images/IMG_1333.png"><img width="300"  alt="display" src="Images/homey.png"><br>

# AP installation
If you bought an AP from me, it comes fully flashed and ready for installation.<br>
What you need to do is connect power to your AP with at least 1A After that you can go to the ip that the AP has pre-installed (192.168.4.1).<br>
when you go to that address you will get the interface for the AP and now you should enter your own network and log in with your user credentials for your network and then your AP is up and running in your network.<br>
<img width="400"  alt="AP" src="https://media.hardwear.io/wp-content/uploads/2023/12/image2.png">

# Start upp the display from deep sleep
Now we will start up the display which is in deep sleep and to wake up the display you need to remove the batteries.<br>
Take it easy as the cover that covers the batteries is very tight and can be difficult to remove.<br>
When the cover is gone, remove the batteries and take a battery and carefully insert the battery in the wrong direction for about 10 seconds, then you short-circuit the battery leads (See the picture which tins should be cross-circuited)<br>
Then you insert the batteries in the correct position and close the door.<br>
It will take a little while before the screen reboots but when it does it will find your AP and the display will then appear in your AP.<br>
When it has been found by your AP, you can choose to run one of the pre-installed scripts from your AP (See the pictures below) or make an integration via the Homey app or Home assistant and more.<br>
<img width="400"  alt="Display" src="https://media.hardwear.io/wp-content/uploads/2023/12/image3-1080x573.webp"><br>
<img width="400"  alt="Display" src="https://media.hardwear.io/wp-content/uploads/2023/12/image6.png"><br>
<img width="400"  alt="Display" src="https://media.hardwear.io/wp-content/uploads/2023/12/image7.png"><br>
<img width="400"  alt="Display" src="https://media.hardwear.io/wp-content/uploads/2023/12/image8.png"><br>

# 3D files
In the folder above (Case for AP) you will find 3D files for the S3_C6_NanoAP v.1 and also for S3_C6_NanoAP v.2<br>
You will also find 3D files for wall mounts and table stands for the 2.9" BWR displays in this folder.<br>

# Ready to go :)
### Now you are ready to start using your AP and display and only your imagination sets the limits.<br>
⭐ The OpenEPaperLink startup guide video by Aaron Christophel @atc1441 [![YouTube](https://custom-icon-badges.demolab.com/badge/youtube-red.svg?logo=youtube&logoSource=feather)](https://youtu.be/Etonkolz9Bs "Watch the OpenEPaperLink startup guide video")

# Support the work
<a href="https://ko-fi.com/wizz666">☕ Buy me a coffee</a>
