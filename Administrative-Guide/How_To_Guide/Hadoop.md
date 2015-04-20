Hadoop - GlusterFS Resource Page
--------------------------------

For the tl;dr folks, there is a great (albeit somewhat out of date)
video on the basics of glusterfs and hadoop interop by Venky Shankar,
available here <https://www.youtube.com/watch?v=uwROr9zvjjM> .

For the rest of us:

[Hadoop](http://hadoop.apache.org/) (or the "Apache Hadoop software
library" as it's officially called) is a framework that allows for the
distributed processing of large data sets across clusters of computers
using a simple programming model. It is designed to scale up from single
servers to thousands of machines, each offering local computation and
storage. Rather than rely on hardware to deliver high-avaiability, the
library itself is designed to detect and handle failures at the
application layer, so delivering a highly-availabile service on top of a
cluster of computers, each of which may be prone to failures.

Although the lines between HDFS and gluster continue to blur with new
features being added to both, the fundamental differences remain which
make the plugin an exciting addition to the hadoop ecosystem of tools
which will allow people to run MapReduce in place against data already
in a gluster environment.

With the GlusterFS connector a highly available file system can be
accessed inside of a hadoop cluster without needing to run an ETL of
copying data into and out of HDFS. Also, the FUSE mountable, POSIX
compliant nature of glusterfs integrate the workflow for ingestion and
analytics access patterns.

The Gluster Connector for Hadoop will be available in [GlusterFS 3.3
beta](3.3beta "wikilink").

### Resources

-   [Apache Hadoop](http://hadoop.apache.org/) project home
-   [Community Q&A for GlusterFS
    Betas](http://community.gluster.org/t/3-3-beta/) and Hadoop
-   [Download GlusterFS 3.3](http://www.gluster.org/download/) with the
    Hadoop connector
-   [GlusterFS 3.3 Beta Resource Page](3.3beta "wikilink")
-   Download GlusterFileSystem (the hadoop plugin) :
    <http://ec2-54-243-59-213.compute-1.amazonaws.com/archiva/browse/org.apache.hadoop.fs.glusterfs/glusterfs-hadoop>