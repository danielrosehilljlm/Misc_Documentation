## An unintelligent solution for finding the optimum level of blue light filtering for your viewing comfort.

Firstly get the daemon going:

    redshift &

If you don't like what you see reset the adjustment:

    redshift -x

To set a color temperature use the -O variable.

Pick a credible value.

Redshift recommends that low temperatures, for nighttime computing, be in the 3000-4000K range and that daytime tempreatures be in the 5500K-6500K range.

For instance, at nighttime, try:

    redshift -O 4500

If it's still a little bit bright for you then reduce the value in small increments but you need to refresh the filtering first.

So try:

    redshift -x redshift -O 4200

If you've gone too far with the blue light filtering then go the other way:

    redshift -x redshift -O 4300

After much experimentation you will hopefully find something to your pleasing.

At which point you can update the configuration file in /~/.config/redshift.conf

Input the values that you were comfortable with along with the other changes.

Enjoy reduced eyestrain and more pleasant computing.
