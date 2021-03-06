OpenShift ElasticSearch Cartridge
=================================
Downloadable ElasticSearch cartridge for OpenShift with HTTP-Basic-Authentication.

To create your scalable ElasticSearch app, run:

    rhc app create <your app name> https://raw.githubusercontent.com/magdev/openshift-elasticsearch-cartridge/master/metadata/manifest.yml -s

**NOTE:** your app currently must be a scalable app or this cartridge will not run.


Adding additional cluster nodes
===============================
To add more nodes to the cluster, simply add more gears:

    rhc cartridge scale -a <your app name> elasticsearch <number of total gears you want>


Plugins
=======
To install ElasticSearch plugins -
* create new app in openshift
* edit the `plugins.txt` file 
* edit the `options.txt` file
* commit
* push your changes to openshift.

The above steps have been tested in OpenShift Online (v2). For Openshift Enterprise, in case it does not have internet access, you may need to copy the plugins and install them.


Options
=======
To set specific options, i.e. for plugins, use the options.txt file or set them as environment variable ES_JAVA_OPTS.


HTTP-Basic Authentication
=========================
[HTTP-Basic-Authentication](https://github.com/Asquera/elasticsearch-http-basic) is enabled by default. The Credentials are set in the options.txt file, default is user `testuser` and password `changeme`. 


License
=======
This project is licensed under the [Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).
