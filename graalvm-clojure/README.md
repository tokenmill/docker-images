# GraalVM Clojure Docker

Docker image with GraalVM and Clojure `tools.deps`.

## How to use the image

The image is intended for use in the FROM field of a downstream Dockerfile. For example, specify:
```docker
FROM tokenmill/clojure:graalvm-ce-19.0.0-tools-deps-1.10.0.442
```

# Building the Docker image yourself

Execute the following build command:

```
docker build -t tokenmill/clojure:graalvm-ce-19.0.0-tools-deps-1.10.0.442 .
```
