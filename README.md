pushpin
=======

A Tasker program to record your gps position (with notes) and help you find your way back with google maps

Task
=====
"Pushpin" - to load saved data and launch the initial form
 1. Read File - File = "Saved Location Notes.txt", To Var = "%SaveLocNotes"
 2. Show Schene - Name = "Pushpin", Display As = "Activity, Full Window"

Scene
=====
Create a new scene with the following
 1. Button called "Set Location"
 2. Button called "Find Location"
 3. Button called "Clear"
 4. Text Area called "Notes"

Set Location
------------
Tap
 1. Write File - File = "Saved Location.txt", Text = "%LOC", Append = Off, Add Newline = On
 2. Popup - Title = "Location", Text = "Storing location: %LOC"


Find Location
-------------
Tap
 1. Read File - File = "Saved Location.txt", To Var = "%FindLoc"
 2. Open Map - Mode = "Navigate to", Lat,Long = "%FindLoc"
 

Clear
-----
Tap
 1. Delete File - File = "Saved Location Notes.txt'
 2. Element Text - Scene Name = "Pushpin", Element = "Notes", Position = "Replace Everything", Text = Enter a single space

Notes
------
Name = "Notes", Text = "%SaveLocNotes"
Text Changed
 1. Write File - File = "Saved Location Notes.txt", Text = "%new_val"
