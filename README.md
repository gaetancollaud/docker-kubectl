# docker-kubectl

A simple docker image with kubectl installed. Can be used for deployment scripts.

No entrypoint defined ! You have to use the command `kubectl`. This is on purpose.

```shell
docker run --rm gaetancollaud/kubectl kubectl version
```


# Gitlab CI example

```yaml
deploy:
  stage: deploy
  image: gaetancollaud/kubectl
  script:
    - cat "$KUBE_CONFIG_CONTENT" > ~/.kube/config
    - kubectl version
  only:
    - master
```
