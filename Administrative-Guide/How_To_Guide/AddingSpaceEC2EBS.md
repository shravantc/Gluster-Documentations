### Expanding EBS volumes

Before starting, you may want to tail the logs on important clients/applications using the volume to make sure they remain up & running throughout the procedure. If done correctly this entire process can be done without interrupting clients. One thing to note is the self-heal process may add significant load to your servers, which may degrade client performance.

1.  Kill brick export daemons (glusterfsd processes) on one glusterfs server for the bricks to expand first
2.  Unmount the bricks you're going to expand. (Unmount before snapshotting so when we restore the filesystem is clean.)
3.  Call EC2 API CreateImage (without reboot) of the server
4.  Force detach the EBS vols you're going to expand. (Make sure you have unmounted the brick before you force detach, or else you wont be able to remount later and will have to reboot.)
5.  Locate the AMI created by CreateImage and get the list of attached snapshots. Create new EBS vols from snapshots to larger size & attach at the same points. (It's important to keep track of which snapshot goes to which volume, and where each is mounted)
6.  Mount new EBS vols & grow XFS
7.  Verify you mounted new bricks in the right order. See details below.
8.  Restart glusterd or force volume start to respawn brick export daemons
9.  Ensure clients reconnect
10. Check heal status with 'gluster volume heal \$vol info'
11. Once heal is finished then repeat for other server

### Verifying bricks are mounted in the right order

1.  Open a terminal on two replica servers
2.  Choose a directory in the volume that has several files
3.  In your bricks directory do ls -la volbrick\*/path/to/files in both terminals
4.  Verify that the output is identical
5.  Each brick should have the same files on both servers. If you see brick contents are not equal then go back & fix your brick mounts.