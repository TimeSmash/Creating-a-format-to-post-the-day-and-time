# Creating-a-format-to-post-the-day-and-time
This is an exercise provided by w3resource.com. I tried to use only the knowledge I had available, so I'm sure this code could be a lot shorter. It was a nice introduction to Date and some of its methods!

What the project does/Proposed problem: Posts the day and time in a specificied format

Proposed problem: "The day is: DAY.  
Current time is: XX AM/PM : XX : XX"

Why the project is useful: Helpful exercise, with what I hope is a thorough explanation

It doesn't have much use outside of showing a possible solution to the proposed problem, but I'm proud of it!

P.S. I currently have no knowledge of how one would keep refreshing the date real-time, so this applies to only a specific instance in time.

Solution explained:

Create dayAndTime

There’s a lot going on here. So we’re going to break it down nice and easy. Note that the following focuses more on the `rightNow` variable rather than the `noonNow` variable (which is a user-defined Date, versus one created at the moment in time like rightNow), but most of the same logic can be used.

The variable `rightNow` is defined as a new <b>Date()</b> constructor, which prints the current date and time upon its creation. If we called `rightNow`, we would get the time I made this example, which was Mon Jan 28 2019 17:05:59 GMT-0600 (Central Standard Time). Note that this is <u><strong>not</strong></u> a string. So, we make a var `timeString` to convert it into a string, which returns "16:30:39 GMT-0600 (Central Standard Time)", which <u><strong>is</strong></u> a string. From there, we make var `minSec` by concatenating a bunch of space strings with uses of <b>string.slice()</b> to cut out colons and numbers from the `timeString`, since we want spaces between colons and numbers returned. We get var `hour` by using <b>.substring()</b> to make a small string made up of the first two characters from `timeString`. Finally, we make var `day` by taking the original `rightNow` variable (remember, not a string), and subject it to the <b>Date.getDay()</b> method, which will return a 1, since Monday = 1 via <b>.getDay()</b>’s rules. 

Since we don’t want military time, if `hour` is >12, we subtract 12 from it and then add “ PM”. If `hour` is <em>exactly</em> 12, we just add “ PM” to it. If it’s <12, we add “ AM” to it. 

After this, we make use of a <b>switch statement<b>, whose cases depending on what `day` is going to equal. Since `day` = 1, we make `day` become “Monday”.

Finally, we return a template literal that utilizes the value of `day`, `hour`, and `minSec`.
