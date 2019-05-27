# Clojure dependencies in private Git repositories

## How to use

Create a Docker image:
```bash
docker build -f Dockerfile --build-arg ssh_prv_key="$(cat ~/.ssh/id_rsa)" --build-arg ssh_pub_key="$(cat ~/.ssh/id_rsa.pub)" -t tokenmill/clojure-private-git-deps:test  .
```

Run the docker container with an interactive bash shell:
```bash
docker run -it tokenmill/clojure-private-git-deps:test bash
```

Start a Clojure REPL with your private Clojure module: 
```bash
clojure -Sdeps '{:deps {me/module {:git/url "git@gitlab.com:me/module.git" :sha "2aa1c686760cff280b7b65b825a4321bdb8de53e"}}}'
```

Voila!

As of now by default: GitHub, GitLab, and BitBucket are supported as sources of private Git repositories.

To add another source of Git repositories add to Dockerfile:
```dockerfile
RUN ssh-keyscan your.git >> /root/.ssh/known_hosts
```

## Thanks!

The solution based on infinite amount of Googling and these online resources:
- https://codehopper.nl/2018/09/27/clojure-gitlab-deps/
- https://stackoverflow.com/questions/18136389/using-ssh-keys-inside-docker-container/42125241
- https://clojure.atlassian.net/projects/TDEPS/issues/TDEPS-91?filter=allopenissues
