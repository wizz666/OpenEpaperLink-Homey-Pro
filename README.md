# Display parsed version in Homey Pro
This is an example on the code to use and edit for the OpenEPaperLink homey app.<br> https://homey.app/sv-se/app/nl.wiggert.OpenEPaperLink/OpenEPaperLink/
<br>The code is for Solum 2.9" display but can be modifyed to fit other displays.<br>
Information regarding Json template - https://github.com/jjwbruijn/OpenEPaperLink/wiki/Json-template<br>
This is an good online editor - https://jsonbeautifier.org/<br>

Here you change the text for each part that you want to display in each section.<br>
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

All credit for the code goes to Fredrik Tornell.<Br>
<img width="500"  alt="display" src="Images/IMG_1333.png"><img width="300"  alt="display" src="Images/homey.png"><br>

# AP installation
If you bought an AP from me, it comes fully flashed and ready for installation.<br>
What you need to do is connect power to your AP with at least 1A After that you can go to the ip that the AP has pre-installed (192.168.4.1).<br>
when you go to that address you will get the interface for Apn and now you should enter your own network and log in with your user credentials for your network and then your Ap is up and running in your network.<br>
<img width="400"  alt="AP" src="https://media.hardwear.io/wp-content/uploads/2023/12/image2.png">

# Start upp the display from deep sleep
Now we will start up the display which is in deep sleep and to wake up the display you need to remove the batteries.<br>
Take it easy as the cover that covers the batteries is very tight and can be difficult to remove.<br>
When the cover is gone, remove the batteries and take a battery and carefully insert the battery in the wrong direction for about 10 seconds, then you short-circuit the battery leads (See the picture which tins should be cross-circuited)<br>
Then you insert the batteries in the correct position and close the door.<br>
It will take a little while before the screen reboots but when it does it will find your AP and will then appear in your AP.<br>
When it has been found by your AP, you can choose to run one of the pre-installed scripts from your AP (See the pictures below) or make an integration via the Homey app or Home assistant and more.<br>
<img width="400"  alt="Display" src="https://media.hardwear.io/wp-content/uploads/2023/12/image3-1080x573.webp"><br>
<img width="400"  alt="Display" src="https://media.hardwear.io/wp-content/uploads/2023/12/image6.png"><br>
<img width="400"  alt="Display" src="https://media.hardwear.io/wp-content/uploads/2023/12/image7.png"><br>
<img width="400"  alt="Display" src="https://media.hardwear.io/wp-content/uploads/2023/12/image8.png"><br>

# Ready to go :)
Now you are ready to start using your AP and display and only your imagination sets the limits.<br>
All credits for the pictures in this guide goes to Aaron Christophel @atc1441<br>

# The OpenEPaperLink startup guide video
### by Aaron Christophel @atc1441<br>
- https://youtu.be/Etonkolz9Bs
