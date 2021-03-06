# System Requirements

In this section, we discuss the hardware, software, and network requirements for SnappyData.

## Hardware  Requirements

SnappyData turns Apache Spark into a mission-critical, elastic scalable in-memory data store. This allows users to run Spark workloads and classic database workloads on SnappyData.

**Memory**: SnappyData works well with anywhere from 8GB of memory to hundreds of GB of memory. While exact memory requirements depend on the end user application, we recommend allocating no more than 75% of the memory to SnappyData. We recommend using a machine with at least 8GB of RAM when working with SnappyData.
**CPU Cores**: SnappyData is a highly multi-threaded system and can take advantage of CPU cores to deliver higher throughput. It has been tested with multi-core multi-CPU machines. We recommend using machines with at least 16 cores when working with SnappyData. The degree of parallelism you can achieve with SnappyData directly depends on the number of cores, as higher core machines perform better than lower core machines.

**Network**: SnappyData is a clustered scale-out in-memory data store and both jobs and queries use the network extensively to complete their job. Since data is mostly available in-memory, queries and jobs typically get CPU and/or network bound. We recommend running SnappyData on at least a 1GB network for testing and use a 10GB network for production scenarios.

**Disk**: SnappyData overflows data to local disk files and tables can be configured for persistence. We recommend using flash storage for optimal performance for SnappyData shared nothing persistence. Data can be saved out to stores like HDFS and S3 using SnappyData DataFrame APIs.


## Operating Systems Supported

| Operating System| Version |
|--------|--------|
|Red Hat Enterprise Linux|RHEL 6.0 and 7.0|
|Ubuntu|Ubuntu Server 14.04 and later|
|CentOS|CentOS 6, 7|


## Host Machine Requirements
Requirements for each host:

* A supported [Java SE installation](http://www.oracle.com/technetwork/java/javase/downloads). SnappyData does not support Java SE 9.

* A file system that supports long file names.

* TCP/IP.

* System clock set to the correct time.

* For each Linux host, the hostname and host files must be properly configured. See the system manual pages for hostname and host settings.

* For each Linux host, configure the swap to be in the range of 32-64GB to allow for swapping out of unused pages.

* Time synchronization service such as Network Time Protocol (NTP).

!!! Note: 
	* For troubleshooting, you must run a time synchronization service on all hosts. Synchronized time stamps allow you to merge log messages from different hosts, for an accurate chronological history of a distributed run.

	* If you deploy SnappyData on a virtualized host, consult the documentation provided with the platform, for system requirements and recommended best practices, for running Java and latency-sensitive workloads.

## Filesystem Type for Linux Platforms

For optimum disk-store performance, we recommend the use of local filesystem for disk data storage and not over NFS.


