# GraalVM Clojure Docker

Docker image with GraalVM and Clojure `tools.deps`.

## How to use the image

The image is intended for use in the FROM field of a downstream Dockerfile. For example, specify:
```docker
FROM tokenmill/clojure:graalvm-ce-19.2.0-tools-deps-1.10.1.469
```

## Building the Docker image yourself

Execute the following build command:

```
docker build -t tokenmill/clojure:graalvm-ce-19.2.0-tools-deps-1.10.1.469 .
docker build -t tokenmill/clojure:latest .
```

## Publishing images

Login to the Docker registry:

```
$ cat ~/my_password.txt | docker login --username foo --password-stdin
```

Push the images:
```
docker push tokenmill/clojure:graalvm-ce-19.2.0-tools-deps-1.10.1.469
docker push tokenmill/clojure:latest
```
