# mongoperf

[![Git](https://app.soluble.cloud/api/v1/public/badges/7a94694f-18aa-4f72-8999-30d2f41afae6.svg?orgId=679096383598)](https://app.soluble.cloud/repos/details/github.com/desteves/mongoperf?orgId=679096383598)  
Added the option to use existing mongoperf__testfile__tmp file from a previous run.

Forked from original:
https://github.com/mongodb/mongo/blob/master/src/mongo/client/examples/mongoperf.cpp

# How To
In your mongoperf input, add "create:<bool>". By default this value true.
Example, 
{nThreads:16,fileSizeMB:1000000,mmf:true,r:true,w:true,recSizeKB:4,create:false}

To gracefully end your test, create a file named "mongoperf__end" in the running directory. 
Example, 
touch mongoperf__end

It will take up to 60 seconds for the test to see the mongoperf__end file. It will then tell the threads to enter a noop loop and end.

# Why
Because SSDs.
