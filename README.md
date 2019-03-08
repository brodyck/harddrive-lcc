# harddrive-lcc
Script that stops any hard drive head from parking (idle) for a specified amount of time.

**Problem:** Green and consumer drives that aren't high-end have a head-park time of between 8 and 13 seconds.

**Idea:** Asking for S.M.A.R.T. data puts any drive into active mode and unparks the head.

**Solution:** Ask for S.M.A.R.T. data before the head parks, continuously. Works for any drive that has S.M.A.R.T. stuff built in. Actual amount of seconds kept alive vary from drive to drive. 

And why not put it on a timer to set high-usage days?

---

It's a mess to read, but:

In the script, in an array, you can:  
- Specify days of the week (0 to 6)  
- Specify hours of the day (0 to 23)  

And it will keep the drive on between the hours of the day on the days specified after first access, then only for the amount of seconds specified during the times that aren't specified.

---

Throw this in a boot script to use it:

    nohup $(bash /path/to/harddrive-spindown $1 $2) &> /dev/null &
    
**$1** is seconds to keep idle

**$2** is the disk to keep idle

---

It's a pretty lazy script, but my LCCs haven't been climbing as drastically since and it seems to have the access speeds I'd expect at the times I'd expect.

Interesting to note: I removed all 'if' statements, opting for '&&', because with the nature of Bash, continually running scripts and the amount of 'if's I used, my CPU usage would skyrocket. 
