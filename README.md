Quick instructions :-) 

Install the operators for OpenShift Serverless and Red Hat Integration - Camel-K

Create a namespace
Add the broker (oc create -f broker.yaml)
Install the cloud emitter (new node.js S2I using https://github.com/utherp0/cloudeventemitter)
Change the CEBROKERURI env in the deployment for the cloudeventemitter to have the right broker URI (fix the {} value)

Add an integration-platform to the namespace (go to installed operators, choose Camel-K, create an integration-platform using the default values)
Run the camel-k integration (cd camelk; kamel run EventReader.java)

cd quarkusfunction
Change the target image (currently quay.io/ilawson/something) to one you can write to
Build the function (kn func deploy)

Pre-reqs - latest 'kn' CLI and latest 'kamel' CLI
