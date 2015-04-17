HowTo
=====

### From GlusterDocumentation

This page contains guides for doing stuff with GlusterFS.

#### Finished Articles

-   [GlusterFS On ZFS](GlusterOnZFS "wikilink")
-   [CTDB HOWTO](CTDB "wikilink")
-   [HA and Load Balancing with NFS and SMB](http://download.gluster.org/pub/gluster/glusterfs/doc/HA%20and%20Load%20Balancing%20for%20NFS%20and%20SMB.html)
-   [Creating Gluster RPMS](CompilingRPMS "wikilink") - How to compile GlusterFS RPMs from git source, for RHEL/CentOS 6.4 and Fedora 16-18
-   [GlusterFS Keystone Quickstart](GlusterFS_Keystone_Quickstart "wikilink")
-   [GlusterFS Cinder](GlusterFS_Cinder "wikilink") - Setup instructions for using GlusterFS with OpenStack Grizzly's block service (Cinder)
-   [GlusterFS iSCSI](GlusterFS_iSCSI "wikilink") - Setup instructions for using GlusterFS as a block storage system with an iSCSI interface
-   [Adding space in EC2 with EBS](Adding_space_in_EC2_with_EBS "wikilink") - A simple procedure to expand the size of your EBS-backed GlusterFS volume.

##### Tips and Tricks

-   [Network Configuration Techniques](Network_Bonding "wikilink")
-   [Brick naming conventions](HowTos:Brick_naming_conventions "wikilink")
-   [Using Gluster with OSX](Using_Gluster_with_OSX "wikilink") - Tips for connecting to GlusterFS volumes with OSX
-   [Linux Kernel Tuning](Linux_Kernel_Tuning "wikilink") - Need to get in the nitty gritty for kernel tuning parameters? This is the article for you
-   [Glusterfs-filter](Glusterfs-filter "wikilink") - Modyfing .vol files directly with a filter.
-   [Using the Gluster Test Framework](Using_the_Gluster_Test_Framework "wikilink") - How to get started with the GlusterFS Test Framework
-   [Building QEMU with gfapi for Debian based systems](Building_QEMU_with_gfapi_for_Debian_based_systems "wikilink")
-   [Performance Testing](Performance_Testing "wikilink") - DRAFT - how to test Gluster performance with typical multi-client, multi-stream workloads.

##### Troubleshooting

-   [Disk already used in a volume](http://joejulian.name/blog/glusterfs-path-or-a-prefix-of-it-is-already-part-of-a-volume/)
-   [Resolve GFID to filename](https://gist.github.com/4392640)
-   [Resolving Peer Rejected](Resolving_Peer_Rejected "wikilink")
-   [Gluster 3.4: Brick Restoration - Replace Crashed Server](Gluster_3.4:_Brick_Restoration_-_Replace_Crashed_Server "wikilink")

#### Articles that need to be written

##### Troubleshooting

-   UUID's and cloning Gluster instances
-   Verifying cluster integrity

##### Configuration

remaining topics:

-   using cgroups to manage Gluster behaviour under different workloads
-   CTDB configuration for failover of non-native protocols (SMB/NFS)
-   [Patching Debian/Ubuntu Packages](http://www.gluster.org/community/documentation/index.php?title=DebianPackagePatching&action=edit&redlink=1)

##### Tips and Tricks

-   Running commands on multiple servers
-   Which filesystem should I format the Gluster bricks with? - XFS or Ext4. There was at one time an [interaction issue](https://lwn.net/Articles/544298/) between the kernel ext4 implementation and older versions of Gluster but that has been [fixed](http://review.gluster.org/#/c/4711/) in recent versions of Gluster and backported to earlier branches ([3.3](http://review.gluster.org/4822) and [3.4](http://review.gluster.org/4799)).

##### Analytics

-   [Running GlusterFS on top of Hadoop](Hadoop "wikilink")
