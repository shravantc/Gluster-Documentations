#Managing Geo-replication

Geo-replication provides a continuous, asynchronous, and incremental
replication service from one site to another over Local Area Networks
(LANs), Wide Area Network (WANs), and across the Internet.

Geo-replication uses a master–slave model, whereby replication and
mirroring occurs between the following partners:

-   **Master** – a GlusterFS volume

-   **Slave** – a slave which can be of the following types:

    -   A local directory which can be represented as file URL like
        `file:///path/to/dir`. 
        
        You can use shortened form, for example,
        
        ` /path/to/dir`.

    -   A GlusterFS Volume - Slave volume can be either a local volume
        like `gluster://localhost:volname` (shortened form - `:volname`)
        or a volume served by different host like
        `gluster://host:volname` (shortened form - `host:volname`).

    > **Note**
    >
    > Both of the above types can be accessed remotely using SSH tunnel.
    > To use SSH, add an SSH prefix to either a file URL or gluster type
    > URL. For example, ` ssh://root@remote-host:/path/to/dir`
    > (shortened form - `root@remote-host:/path/to/dir`) or
    > `ssh://root@remote-host:gluster://localhost:volname` (shortened
    > from - `root@remote-host::volname`).

This section introduces Geo-replication, illustrates the various
deployment scenarios, and explains how to configure the system to
provide replication and mirroring in your environment.
