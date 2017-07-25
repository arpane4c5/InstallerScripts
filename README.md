# InstallerScripts : Scripts to setup hadoop tools (tested on Ubuntu 14.04)

The scripts were prepared by me while setting up a 5 node hadoop cluster in my lab. They should not be used 'as-is', since the settings might differ for your systems. I had installed Ubuntu 14.04 on all the nodes, with 'hadoop' as the username for all (The passwords may differ). It is recommended that you go through the scripts and make the necessary changes (usernames or file/folder paths) and then execute the scripts, starting from 'step1_...'. It is mentioned in each script, which has to be executed as root and which is not i.e., for execution as root `sudo ./stepX_...`. Use `chmod +x stepX...` to make the file executable.

## Prerequisites and some instructions

* Install Ubuntu 14.04 on the nodes, (I have made the usernames of all the nodes as 'hadoop' but they may differ).

* Create a folder named 'Backup' on the Desktop and store the following softwares (as per your requirements) into the folder: jdk-8u60-linux-x64.tar.gz, scala, eclipse(if needed), apache-ant, apache-maven, gradle, spark, hadoop-2.7.1, opencv-3.X, cuda_8.X_linux.run, Anaconda2-2.4.0-Linux-x86_64 etc.

* `sudo apt-get update`

* Make sure that openjdk is NOT installed (Hadoop works with Oracle JDK). If it is installed, then remove it using `sudo apt-get purge openjdk-*`

* The commands in the scripts are written such that they are valid if executed as a part of the script (i.e., using ./stepX_...). If you wish to copy and paste the commands one by one, then make sure that you modify the commands as per the correct syntax, e.g., wherever when writing a path to `.bashrc` the `\$` will be replace by `$` in the line `export HADOOP_HDFS_HOME=\$HADOOP_HOME`.

* The files core.txt, mapred.txt, yarn.txt and hdfs.txt are helper files containing lines which need to be copied to the corresponding config files of hadoop. The script step2_installHadoop has commands that copies the lines from these files and puts them in the correct places in the config files. 

* For setting up a multinode cluster, after installing step2_installHadoop, refer the file multinode/step2_configHadoopMultinode.

* step4_installHIPI is used for installing [Hadoop Image Processing Interface](http://hipi.cs.virginia.edu/). If you are working on this platform then only you need to install it.

* For installing OpenCV, I have used one configuration. One may refer the [official site](http://docs.opencv.org/trunk/d7/d9f/tutorial_linux_install.html) for the details of how to install with some other configuration of modules.

* spark_env.sh is a sample file with changed configurations. slaves file is also a sample file.

Note: The scripts from step1_... to step11_... were prepared around July 2015. Therefore, the versions of the tools that have been used are from around that time. You may make necessary changes for recent version.
