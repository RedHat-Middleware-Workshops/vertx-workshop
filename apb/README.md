If running via your own machine you can run the following command

  ```
  oc new-project labs-infra

  oc run apb --restart=Never --image="quay.io/openshiftlabs/vertx-workshop-apb" \
-- provision -vvv -e namespace="labs-infra" -e openshift_token=$(oc whoami -t) -e infrasvcs_gogs_user_count=50
  ```

to follow the logs
  ```
  oc logs apb -f
  ```