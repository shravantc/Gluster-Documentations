This procedure is for replacing a failed server, IF your newly installed
server has the same hostname as the failed one:

(If your new server will have a different hostname, see [this
article](http://community.gluster.org/q/a-replica-node-has-failed-completely-and-must-be-replaced-with-new-empty-hardware-how-do-i-add-the-new-hardware-and-bricks-back-into-the-replica-pair-and-begin-the-healing-process/)
instead.)

For purposes of this example, the server that crashed will be *server3*
and the other servers will be *server1* and *server2*

-   On both server1 and server2, make sure hostname server3 resolves to
    the correct IP address of the new replacement server.
-   On either server1 or server2, do
        grep server3 /var/lib/glusterd/peers/*

    This will return a uuid followed by ":hostname1=server3"

-   On server3, make sure glusterd is stopped, then do
        echo UUID={uuid from previous step}>/var/lib/glusterd/glusterd.info

-   On server3:
    -   make sure that all brick directories are created/mounted
    -   start glusterd
    -   peer probe one of the existing servers
    -   restart glusterd, check that full peer list has been populated
        using
            gluster peer status

    -   (if peers are missing, probe them explicitly, then restart
        glusterd again)
    -   check that full volume configuration has been populated using
            gluster volume info

    -   if volume configuration is missing, do\
            gluster volume sync server1 all
-   add the volume id(s) to the new brick(s) (do this for each
    volume/brick on this server)
        vol=myvol
        brick=/mnt/myvol/brick1
        setfattr -n trusted.glusterfs.volume-id \
          -v 0x$(grep volume-id /var/lib/glusterd/vols/$vol/info \
          | cut -d= -f2 | sed 's/-//g') $brick

-   now restart gluster:        

        restart glusterd

This will restore the configuration for this server.

If this is a replica brick, restore the data with

        gluster volume heal $vol full