[![](https://img.shields.io/badge/Lifecycle-Incubating-blue)](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md#incubating-)
# Camunda Cloud Self Managed Docker Compose
docker-compose file to stand up a complete Camunda Cloud Self Managed (Zeebe, Elasticsearch, Operate, Tasklist, Identity, and Optimize) environment for development purposes. Note, it has been tested with Zeebe, Identity, Operate, and Tasklist v8.0.0 and Optimize v3.8.0.

Clone this repo and update your hosts files to include:

```
127.0.0.1	keycloak
```

Issue the following command to start up your environment:

```
docker-compose -f ccsm-all.yml up -d
```

Wait a few minutes for the environment to start up and settle down. Monitor the logs, especially the Keycloak container log, to ensure the components have started.

Now you can navigate to: <br><h3>Operate http://localhost:8081
<br>Tasklist (http://localhost:8082)
<br>Optimize (http://localhost:8090)</h3>
You'll notice you're using Identity/Keycloak to log into each application.

Zeebe, Operate, Tasklist, along with Optimize require a separate network from Identity as you'll see in the docker-compose file. You'll also notice in the zeebe-application.yml file there are two exporters defined, one for Operate and Tasklist and one for Optimize. Feedback and updates are welcome!

Identity