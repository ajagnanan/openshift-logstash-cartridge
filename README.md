## OpenShift Logstash Cartridge

This cartridge is best used as a addon to an application in openshift. The configuration is mainly driven through environment variables,
due to certain configurations require confidential information.

## Environment Variables

These environment variables are available when configuring Logstash:

 * **`OPENSHIFT_LOGSTASH_CONF_FILE`**: Configuration file name located in the /conf folder. Required.

 * **`OPENSHIFT_LOGSTASH_ES_HOST`**: URL of the Elasticsearch cluster to log to. Required.
 * **`OPENSHIFT_LOGSTASH_ES_USERNAME`**: Username to connect as. Optional.
 * **`OPENSHIFT_LOGSTASH_ES_PASSWORD`**: Password to connect with. Optional.

 * **`AWS_ACCESS_KEY_ID`**: AWS access key
 * **`AWS_SECRET_ACCESS_KEY`**: AWS secret key
 * **`AWS_SQS_QUEUE_NAME`**: AWS queue name

 * **`OPENSHIFT_LOG_LOCATION`**: Log location when using the file input

## Installation Steps

    1. Create your application
    2. Add the environment variables
    3. Add this cartridge to your application

## Environment Variable Configuration

    # Configure application environment variables
    $ rhc set-env --app my-app --env "OPENSHIFT_LOGSTASH_ES_HOST=abc123-us-east-1.foundcluster.com"

    # Add this cartridge
    $ rhc cartridge add -a your-app-name https://cartreflect-claytondev.rhcloud.com/github/ajagnanan/openshift-logstash-cartridge