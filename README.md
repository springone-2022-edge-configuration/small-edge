# small-edge
This repository contains the yaml configuration of all the resources that need to be deployed in the SMALL-Edge locations.

imgpkg pull -b localhost:5000/hello-app-bundle:v1.0.0 \
-o temp/hello-app-bundle

ytt -f temp/hello-app-bundle/config \
-f temp/hello-app-bundle/.imgpkg/images.yml \
--data-values-file values.yml \
| kbld -f- \
> temp/hello-friends.yml

TODO:
- cache carvel packages installation
- pass env var between jobs
- not commit the final yaml to git
- push the imgpkg of teh final yaml to the regitry
- 