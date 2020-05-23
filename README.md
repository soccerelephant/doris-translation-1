# doris-translation-1
doris compilation translation

Compilation
This documentationis to mainly explain how to use source code to compile Doris

Use mirror Docker for compilation using  (recommended)
Use existing off-the-shelf image mirrors

1. Download Docker Image Mirror
  $ docker pull apachedoris/doris-dev:build-env
  Check image mirror download completed:
  
  $ docker images
  REPOSITORY              TAG                 IMAGE ID            CREATED             SIZE
  apachedoris/doris-dev   build-env           f8bc5d4024e0        21 hours ago        3.28GB
  
  Note: For different versions of Oris, you must download the corresponding mirror version.
  
  image version	                            commit id	                      release version
  apachedoris/doris-dev:build-env	          before ff0dd0d	                0.8.x, 0.9.x
  apachedoris/doris-dev:build-env-1.1	      ff0dd0d or later	              0.10.x or later
  
  
2. Running Image Mirror
   $ docker run -it apachedoris/doris-dev:build-env
   
   If you want to compile Doris source codelocally, you can specify the path:
   $ docker run -it -v /your/local/incubator-doris-DORIS-x.x.x-release/:/root/incubator-doris-DORIS-x.x.x-release/ apachedoris/doris- dev:build-env
   
   
3. Download source code
   After starting the image mirror, you should be inside the container. The Doris source code can be downloaded from the following  command (local  source directory specified is not required):
   $ wget https://dist.apache.org/repos/dist/dev/incubator/doris/xxx.tar.gz
   or
   $ git clone https://github.com/apache/incubator-doris.git
   
4. Compile Doris
  $ sh build.sh
  The output file is in the output/ directory after compilation.
  
  
  
Self-compiling Development Environment Mirror
You can also create a Doris development environment mirror yourself, particularly referring to the `docker/README.md'file.

Direct Compilation (CentOS/Ubuntu)

You can compile Doris directly in your own Linux environment.

System Dependences:

GCC 5.3.1+, Oracle JDK 1.8+, Python 2.7+, Apache Maven 3.5+, CMake 3.11+

If you are using Ubuntu 16.04 or newer, you can use the following command to install the dependencies

   sudo apt-get install build-essential openjdk-8-jdk maven cmake byacc flex automake libtool-bin bison binutils-dev libiberty-dev

After installation, set environment variables PATH, JAVA_HOME, etc.

Compile Doris

$ sh build.sh
The output file is in the output/ directory after compilation.
   
   



