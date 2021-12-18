# tekton-chains-demo

All the files are about a simple example to test tekton.

- `sa.yaml`: the service account file to store the sa info which is associated with secrets, such as github/gitlab credentials, dockerhub credentials;
-  `secret-credentials.yaml`: to store the detail credentials info about github/gitlab/dockerhub login;
-  `pipelineresource.yaml`: specify the input and output for the CI/CD Pipeline, namely the input source and output image info;
-  `task.yaml`: detail info about tekton task;
-  `taskrun.yaml`: detail info about taskrun;

Then using `kubectl apply` command to create all the resouces, the demo will be OK.

Checking the taskrun resource

```
$ tkn -n tekton-demo tr list
NAME                     STARTED      DURATION   STATUS
build-docker-image-run   6 days ago   1 minute   Succeeded
```

Checking the task resource

```
$ tkn -n tekton-demo task list
NAME                 DESCRIPTION   AGE
build-docker-image                 6 days ago
```

The below info shows the tekton demo(build docker image and push image to the registry success).
