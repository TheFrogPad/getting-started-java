[![wercker status](https://app.wercker.com/status/66210606b8d3610fd34e8ea8e82d2bf4/m/ "wercker status")](https://app.wercker.com/project/byKey/66210606b8d3610fd34e8ea8e82d2bf4)

# NOTE

The original wercker sample has been update in this fork to use the OWSAP dependency-check tool as a step in the `build` pipeline.

## HTTPS Proxy for wercker CLI

When building locally with the wercker CLI, a proxy server and proxy port can be specified in the environment file:

```
X_HTTPS_PROXY_SERVER="proxy.company.com"
X_HTTPS_PROXY_PORT="80"
```

Then when running the wercker CLI specify:

```
wercker --environment /path/to/environment.txt build
```

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
