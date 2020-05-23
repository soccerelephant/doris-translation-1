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


