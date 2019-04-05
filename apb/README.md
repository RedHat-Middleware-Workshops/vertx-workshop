# Setting up a the Vert.x 

If running via your own machine you can run the following command

  ```
  oc new-project labs-infra

  oc run apb --restart=Never --image="quay.io/openshiftlabs/vertx-workshop-apb" \
             --image-pull-policy="Always" \
             -- provision -vvv \
             -e namespace="$(oc project -q)"  \
             -e openshift_token=$(oc whoami -t) \
             -e infrasvcs_gogs_user_count=1 \
             -e che_generate_user_count=1 \
             -e openshift_master_url=$(oc whoami --show-server)/console
  ```

to follow the logs
  ```
  oc logs apb -f
  ```
