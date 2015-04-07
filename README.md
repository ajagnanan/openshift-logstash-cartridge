OpenShift Logstash Cartridge
=================================
This cartridge provides a Logstash installation for Openshift. It is a cartridge, so it'll need an existing Openshift gear to be installed on. It is mainly user configuration driven because the configuration files can be uploaded as part of the gear's repository. If using my [openshift-elasticsearch](https://github.com/ajagnanan/openshift-elasticsearch) cartridge, it'll auto configure the `access.log` to be inputted into Elasticsearch. It'll use the user credentials that `Kibana` uses if `shield` is installed.

To add this cartride, run:

    rhc cartridge add https://cartreflect-claytondev.rhcloud.com/github/ajagnanan/openshift-logstash-cartridge -a <app>

### Configuration

Configuration files can be added in your repository's `logstash` folder. Follow the samples provided in the `template/logstash` directory. Multiple configuration files can be used and a guide of that is found [here](http://lookonmyworks.co.uk/2014/04/17/multiple-configuration-files-for-logstash/). 

### Updates

This cartridge is upgradeable. The setup looks at an environment variable to handle the upgrade.

The steps are as follows:

  - rhc set-env LOGSTASH_VERSION=1.4.2 -a [app] --namespace [domain]
  - trigger a `deploy` by pushing a change with git

### License
This cartridge is [MIT](http://opensource.org/licenses/MIT) licensed.
