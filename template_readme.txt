So you want to make your own calendar skin! That's neat, but be aware that calendar skins are very much in the stone age, and the whole calendar system is in need of an overhaul. I'm unsure if the calendar system ever will be overhauled, so calendar skins are just sort of a little misc thing that doesn't typically see much use.

But if you would still like to make one, press onwards! It's actually not too hard, so long as you don't mind fiddling with the spacing until you have it how you want.

Before we begin, a quick note: please make sure you add a craftman and replace the name/directory of the calendar skin in the descript.txt and install.txt files!

Also, as far as I can tell, calendar skins will not pop up a readme file when the user installs them. So, I've omitted readme.txt, and just included this template readme for you instead. You can delete this file once you're done making your calendar skin. They also do not have the ability to network update, so there's no need to provide a homeurl as they can't use it. But if you want to add one anyways just in case the functionality is added in the future, I suppose you could.

There is, at the time of writing, no Ukadoc page for calendar skins! So, this template is just thrown together from what little I have seen of other existing calendar skins. I hope one day that will change, but who knows.

And that's the main reason this file exists! This file will describe the things you'll find in the other files, so that you know what they do, without having to clutter that file up.


————— Things to keep in mind —————
Calendar skins are a bit weird, so here are some things to remember while working with them!

• No self alpha. You will have to have a "transparency color" behind your images. It can be any color, ideally one that doesn't appear elsewhere in the image. The top left pixel of each image will be used as the color to be made transparent. In my case, I've exported my markers on top of the background color of the calendar background. But this may not work for you, and you may want to put them on some odd color that doesn't appear in your design. My "current" marker is an example of this, being on a tan background.
• No readme, as mentioned.
• No ability to network update, so no homeurl, as mentioned.
• You can reload the calendar skin simply by closing and reopening it! If you have a ghost in focus, you can press Ctrl D to quickly open/close it.


————— How to make a calendar skin —————

Most of what's described here is for descript.txt, so that's where we'll start. First of all, please change the name of the skin, and make sure you add your name (craftman) and a link to credit you by (craftmanurl).


Next in the file is the table. This is one of the most important things in a calendar skin, and setting up a good table is key. SSP will automatically generate the grid of days in the month based on the area of the table you set up. You'll want to draw your background image, and then set up your table so you can make sure it will be aligned how you want on your image. It's probably a good idea to make a mockup image while you're working on getting everything aligned, before you draw the final design, in case you need to make any adjustments.

You'll see there are 4 settings for the table; left, top, right, and bottom. Specify coordinates here to mark out the area where the table can be generated, so that SSP can automatically fill the table with cells of the appropriate size. You may want to do a little math to figure out how big each cell will be so that you can plan for your other markers, or you can just play with it until it seems right. If you're planning to give your calendar a visible grid in the background, it's really important to get this aligned properly. (This also goes for if you want to add labels for the days of the week!)

Note that all of the day numbers and markers that get attached to the days use coordinates relative to the top left corner of their cell in the table.


After the table comes the numbers. You need images for numbers 0-9, and SSP will use these to automatically generate all the numbers it needs.

Note that there are 3 types of day numbers! Saturday numbers are for Saturday, holiday numbers are for Sunday, and the other numbers are for everything else. This means you can have Saturdays and Sundays be highlighted different colors, if you'd like. But if you don't want that, you can just make them all use the same files. We'll look at how to do that later.

The day.pos.x and day.pos.y can be used to position the day numbers within their cells in the table. You can put them wherever you'd like in the cells.

You can also use the day.spacing, saturday.spacing, and holiday.spacing to adjust the space between digits in numbers that have multiple digits, if you need to. You can use negative numbers here to push them closer together, if desired!

The year numbers are similar, but the X and Y options position the year number relative to the background image. Place the year number wherever you like, and SSP will figure out the rest.


After this are the day markers. The today marker is used to mark the current day, and the current marker is used to mark which day the user currently has selected. Position them as needed relative to the cell of the table they're in.


Then come the event markers. Event markers actually have their own special file, because you can specify as many event markers as there are event types! If you look in icon.txt, you'll see where it specifies the event types, and which icon each should get. Note that the markers here are listed by their file name, without the extension. If you wanted, you could put the markers into a subfolder to keep things tidy.

By default there are two different markers. I'm not really sure what's special about some of the events that they get a different marker, but I've maintained the setup that the default SSP calendar has. You can make all the markers be the same, or you can make several markers, whatever you'd like! I would recommend keeping them all the same size though.

Once you've got your markers, you'll need to use the icon.left, icon.top, icon.right, and icon.bottom options to mark out a rectangle in which the markers can appear.

You'll also want to specify the size of your marker images with the width and height options, and you can add a little buffer space between them there if desired. I think it defaults to the size of the image, but I'm not positive there.

As the user adds events to a day, SSP will automatically add markers into the box you've specified, until it runs out of room. Try to size your box to fit a decent amount of them! It might be a good idea to add several events to a day so you can see how they'll fit.


Next are the month names! This is pretty simple, just use the month.pos.x and month.pos.y to position where the month name images will appear. I would recommend making sure all the month names have images of the same height, otherwise they'll shift around weirdly.

Note that you can get a little creative with this. For example, I made a galaxy calendar that looks like a wall calendar, and the image on the top half is actually controlled by the month name so that it has a different picture for each month. I would *not* recommend trying to add anything fancy around the table, because that area will probably have conflicts with other icons and such. But if you're careful, you can have a bit of fun with it!


And finally, the next and previous buttons! These are used to go back and forward by one month on the calendar. In this template, they're left and right buttons. But, you can also make them up and down buttons, or whatever you want.

Draw your arrows/whatever markers onto your background image, and then use coordinates in the left, top, right, and bottom options to mark out the clickable areas.


And that's about it! You *can* adjust the filenames at the very bottom if you want to, but most likely you won't need to, unless you want to do something like make the year number use a different font, or make all the days use the same numbers instead of Saturday and Sunday being highlighted.

If you want to do that, it's pretty simple. You can see that these options specify a filename with no extension (like was mentioned before with the markers in icon.txt), and for the months and numbers, they specify it without the number on the end. So for the day numbers, if you put "day.filename,number", it will search for files called "number0.png", "number1.png", etc. It automatically appends the numbers as needed.

I have sorted the files into subfolders to make things a bit tidier, but you can put them all in the main folder if you want to. Just make sure you adjust the filenames appropriately.


Once you're done with all that, do a final check of your info at the top of descript.txt, check your install.txt, delete this file, and then you can drag and drop your calendar skin's folder onto any running ghost and ask them to make a .nar file! (If you don't get the option to do so, you probably need to turn developer mode on.) Note that a lot of ghosts, especially older ones, don't have dialogue for when they're done installing a calendar skin. Just open your calendar, right click it, and check under the "Skin" menu to see if it's there!


Simplicity Calendar v1.0.1
Made by Zichqec https://ukagaka.zichqec.com/
You are free to use this to create any calendar skins you like, no need to credit me! But if you'd like to find more by me, including more templates like this, find me at the link above.