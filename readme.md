# Seattle CoderDojo App Inventor Orientation Sensor Workshop

Today we're going to experiment with moving things on the screen, not by touching the screen, but by moving it.

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

From the orientation sensor's menu, take the "When OrientationSensor1.orientationChanged" block. In it, let's put blocks for the "pitchValue" and "rollValue" and set them to display the pitch and roll values.

There's an azimuth value as well, but we'll ignore it for now. 

![simplePitchandRoll](/images/simplePitchandRoll.jpg)

Let's open the app in our companion and try it out.

Hold up your device so the screen is facing you, and it's turned so it's wider than it is tall, with the "top" side of the device on the left.

 ![pixabay_android](/images/pixabay_android.jpg)

The pitch value will be near 0 and the roll value will be near 90. 

Now tilt the top away from you and the roll value will go down. Tilt it back toward you and it will come back to 90, then start going down as it tilts from straight up and down to tilting toward you.

Now tilt the right side up and the pitch value will go up. Tilt the left side up and it will go down, even below zero. 

The values range between -90 and 90 and they're both approximately zero when you lay the device flat on a table.

The azimuth value, which we didn't include, would change if you laid that phone flat on the table and spun it. We're not using it today. On the other hand, if you wanted to make a game where you set your device on a table and had to spin it fast enough to make a character get dizzy and barf, you'd totally use the azimuth.

## Let's make something move

Start a new project. We can call this one "OriBall" (for Orientation Ball).

Add a canvas from "Drawing and Animation." Then drag a ball from "Drawing and Animation" onto it. Then grab an orientation sensor from the "Sensors" menu.

**Canvas1**

* Set the height and width to "fill parent"

**Ball1**

* Set the radius to 10, X to 0, and Y to 0

It should look like this.

![screen2](/images/screen2.jpg)

Let's add some code blocks.

![globalx](/images/globalx.jpg)

The first thing we do is set a global variable called "xVal" because we're going to need to do a little extra math with it.

![massageX](/images/massageX.jpg)

Then we'll pull in a to-do procedure block and name it "massageX."

Next, pull in an "if-then" from the control menu, and use the mutator (the little gear in the top left) to add an "else if." 

The "get global xVal" and "set global xVal" blocks come from the "Variables" menu, and the rest come from the math menu. If we didn't do this, you'd have to rotate the phone so the screen was facing away from you to get the ball to go up. Instead, we set it so that if the phone is tilted past 45 degrees, the value starts becoming negative (which makes the ball go up). We have the "else if" to handle when the numbers are negative, like if you flipped the phone around so the top was on the right instead of the left.

![rollit](/images/rollit.jpg)

Then, from the Orientation Sensor's menu, we pull in the "when Orientation changed" block we used in the last project.

It may seem odd, but because the app sets up and down as the top and bottom of the device, we'll use the Y value to set the side-to-side motion of the ball. Every time this runs, we'll set the ball's Y position to its current position, minus the pitch divided by 3.

Now, if you wanted the ball to move at a constant speed, you might do a "massageY" function that simply set the value to a constant positive or negative value. But by setting how much it moves to a fraction of the pitch, the more you tilt the device, the faster the ball will move.

Next, we set the global "xVal" variable to the sensor's roll value, run "massageX" on the variable, and set the ball's X position like we set the Y position, but to a third of the massaged roll value instead of a third of the one directly from the sensor. 

It should all look like this.

![rollblocks](/images/rollblocks.jpg)

Try it out. See how it works. You can even adjust some of the numbers to see how that affects the way the ball moves.

## And now... HOMEWORK!

This is the 9th workshop of the two sessions we've done with App Inventor. Now it's time for you to start pulling together everything you learned to make something of your own.

If you don't have a project you want to work on specifically, add to this one. Use things you learned from MoleMash and Flick Golf to make a game that lets you move your screen to move the ball into a goal or through a maze.

Or maybe make something else entirely.

When you're done. Publish your game to the gallery. 

* From the "Projects" menu, select "My projects."
* Check the box next to the project with your game.
* Click the "Publish to Gallery" button.

This way we can all load it and check it out next week.

If you want to change the name of your game so it stands out in our gallery search, go to the "Projects" menu and select "Save project as" to save it with a different name. Then you can publish that one.

Next week, we can play some of each other's games, and if you want, you can talk about how you made yours.

Have fun!

© 2019 - Copyright 2019 by Greg Bulmash - this content is licensed [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/)