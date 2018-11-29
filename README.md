# harddrive-lcc
script that stops any hard drive head from parking (idle) for a specified amount of time.

It's a pretty lazy script and it may or may not work the exact way I intended, but my LCCs haven't been climbing as drastically anymore.

Throw this in a boot script to use it:

    nohup $(bash /path/to/harddrive-spindown 1200 /dev/sde) &> /dev/null &
    
    $1 is seconds to keep idle
    $2 is the disk to keep idle
