# Seattle CoderDojo App Inventor Orientation Workshop

Today we're going to experiment with moving things on the screen by moving the screen.

## Understanding Pitch and Roll

For our first experiment, we're going to create a simple display that shows us the numbers that are generated when we tilt our devices.

We'll start a new project, called "Orientation 1."

In it, we'll put 2 horizontal arrangements from the "Layout" menu, and in each horizontal arrangement we'll put two labels from the "User Interface" menu.

**Horizontal Arrangement 1**

Set width to "fill parent"

* 1st label rename to "pitchLabel," change the font size to 18, and the text to "Pitch: "
* 2nd label rename to "pitchValue," change the font size to 18, and the text to nothing.

**Horizontal Arrangement 2**

Set width to "fill parent"

- 1st label rename to "rollLabel," change the font size to 18, and the text to "Pitch: "
- 2nd label rename to "rollValue," change the font size to 18, and the text to nothing.

From the "Sensors" menu, pull an Orientation Sensor onto the screen. Your screen should look like this.

![screen1](/images/screen1.jpg)

Let's add some blocks to make it functional.

From the orientation sensor's menu, take the "When OrientationSensor1.orientationChanged" block. In it, let's put blocks for the "pitchValue" and "rollValue" and set them to the pitch and roll values.

There's an azimuth value as well, but it's unlikely to be used for our games. 

![simplePitchandRoll](/images/simplePitchandRoll.jpg)

Let's open the app in our companion and try it out.

If you hold up your device so the screen is facing you, and its turned so it's wider than it is tall, with the "top" side of the device on the left.

 ![pixabay_android](/images/pixabay_android.jpg)

The pitch value will be near 0 and the roll value will be near 90. 

Now tilt the top away from you and the roll value will go down. Tilt it back toward you and it will come back to 90, then start going down as it tilts from straight up and down to tilting toward you.

Now tilt the right side up and the pitch value will go up. Tilt the left side up and it will go down, even below zero. 

The values range between -90 and 90 and they're both approximately zero when you lay the device flat on a table.

The azimuth value, which we didn't include, would change if you laid that phone flat on the table and spun it. But for our game purposes, it doesn't help us in this case, so we're not using it. On the other hand, if you wanted to make a game where you set your device on a table and had to spin it fast enough to make a character get dizzy and barf, you'd totally use the azimuth.

## Let's make something move

Start a new project. We can call this one "OriBall" (for Orientation Ball).

Add a canvas from "Drawing and Animation." Then drag a ball from "Drawing and Animation" onto it. Then grab an orientation sensor from the "Sensors" menu.

**Canvas1**

* Set the height and width to "fill parent"

**Ball1**

* Set the radius to 10, X to 0, and Y to 0

It should look like this.

![screen2](/images/screen2.jpg)