[![wercker status](https://app.wercker.com/status/66210606b8d3610fd34e8ea8e82d2bf4/m/ "wercker status")](https://app.wercker.com/project/byKey/66210606b8d3610fd34e8ea8e82d2bf4)

# Overview

The [wercker getting started with Java sample](https://github.com/wercker/getting-started-java) has been updated in this forked copy to [use the OWSAP dependency-check tool](https://www.owasp.org/index.php/OWASP_Dependency_Check) as a step in the `security-scan` pipeline.

There is also an option to use the OWASP supplied gradle plugin based on the updates made to the orginal `build.gradle` file in the `build` pipeline.

The wercker application for this fork has a wercker workflow that triggers the `security-scan` pipeline after the `build` pipeline completes. In addition, the GitHub status is updated by wercker such that each commit will indicate the result of the pipelines.

## HTTPS Proxy for dependency-check with wercker CLI

When building locally with the wercker CLI, a proxy server and proxy port can be specified in the environment file:

```
X_HTTPS_PROXY_SERVER="proxy.company.com"
X_HTTPS_PROXY_PORT="80"
```

Then when running the wercker CLI specify:

```
wercker --environment /home/crperez/proxy_env.txt build --pipeline security-scan
```

## HTTPS Proxy for gradle with wercker CLI

To run the gradle build with a proxy server, update the properties file in your local ~/.gradle folder or create a gradle.properties file in the root of the gradle project:

```
systemProp.http.proxyHost=proxy.company.com
systemProp.http.proxyPort=80
systemProp.http.nonProxyHosts=*.company.com|localhost|127.0.0.1
systemProp.https.proxyHost=proxy.company.com
systemProp.https.proxyPort=80
systemProp.https.nonProxyHosts=*.company.com|localhost|127.0.0.1
```

# OWASP dependency-check

See [https://www.owasp.org/index.php/OWASP_Dependency_Check](https://www.owasp.org/index.php/OWASP_Dependency_Check) or the [documentation on GitHub](https://jeremylong.github.io/DependencyCheck/)

# TODO

- Abstract out the version of the OWASP dependency-check tool used when the Step executes
- Add additional Step parameters that map to the OWASP dependency-check CLI parameters

# getting-started-java

A sample application in Java for wercker.

This application uses the `openjdk` container obtained from the [Docker Hub](https://registry.hub.docker.com/_/openjdk/)

## Setup & Build
Clone this repo and cd into the directory:

```
git clone https://github.com/wercker/getting-started-java.git
cd getting-started-java
```

then build using:

```
wercker build
```

## Run
To run the application, simply execute:

```
wercker dev --expose-ports
```

Now point your browser at `http://localhost:8080` to see:
```
Hello World!
```

---
Sign up for wercker: http://www.wercker.com
Learn more at: http://devcenter.wercker.com
