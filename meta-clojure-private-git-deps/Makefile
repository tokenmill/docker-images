docker-image-env-vars:
	docker build -f Dockerfile --build-arg ssh_prv_key="$SSH_PRIVATE_KEY" --build-arg ssh_pub_key="$SSH_PUBLIC_KEY" -t tokenmill/clojure-private-git-deps:test  .

docker-image-ssh-conf-files:
	docker build -f Dockerfile --build-arg ssh_prv_key="$$(cat ~/.ssh/id_rsa)" --build-arg ssh_pub_key="$$(cat ~/.ssh/id_rsa.pub)" -t tokenmill/clojure-private-git-deps:test  .
