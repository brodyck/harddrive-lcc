# harddrive-lcc
Script that stops any hard drive head from parking (idle) for a specified amount of time.

It's a pretty lazy script and may or may not work the exact way I intended, but my LCCs haven't been climbing as drastically since and it seems to have the access speeds I'd expect at the times I'd expect.

Interesting to note: I removed all 'if' statements, opting for '&&', because with the nature of Bash, continually running scripts and the amount of 'if's I used, my CPU usage would skyrocket. 

Throw this in a boot script to use it:

    nohup $(bash /path/to/harddrive-spindown 1200 /dev/sde) &> /dev/null &
    
$1 is seconds to keep idle
$2 is the disk to keep idle
