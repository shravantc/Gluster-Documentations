Gluster 3.4.0-beta1 and OSX 10.8.3
----------------------------------

At the moment, CIFS (Samba) is not working well with Finder, and there's
no recent Gluster client for OSX. So we'll use NFS.

But mounting Gluster volume from OSX 10.8 Finder menu is not working
well during simple operations (like browsing or compress from/to the
volume) : It gives a "connection interupted" error dialog, even if the
volume is still mounted and working well using terminal.

A solution is to mount the Gluster volume by hand and tell it to use TCP
NFSv3 with nolock:

    $ sudo mount -t nfs -o intr,tcp,nolock,vers=3 XX.XX.XX.XX:/GlusterVolume /Your/MountPoint

Additionally, the "NFSManager" GUI for OSX (commercial) is helpful when
trying to mount NFS shares and choose options:

<http://www.bresink.com/osx/NFSManager.html>
