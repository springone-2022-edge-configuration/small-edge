# small-edge
This repository contains the yaml configuration of all the resources that need to be deployed in the SMALL-Edge locations.

[//]: # ( Create a bundle in a registry with configuration and image references)
imgpkg push -b index.docker.io/username/my-bundle:v1.0.0 -f config/

imgpkg pull -b localhost:5000/hello-app-bundle:v1.0.0 \
-o temp/hello-app-bundle

ytt -f temp/hello-app-bundle/config \
-f temp/hello-app-bundle/.imgpkg/images.yml \
--data-values-file values.yml \
| kbld -f- \
> temp/hello-friends.yml


[//]: # (TODO:)

[//]: # (- use gitregistry)

[//]: # (- push the imgpkg of the final yaml to the regitry)

[//]: # (- pass env var between jobs)

[//]: # (- cache carvel packages installation)

[//]: # (- not commit the final yaml to git)

[//]: # (- )
