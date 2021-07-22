# One Time Secret Docker Image
This repository is a fork of this fork https://github.com/siw36/onetimesecret of this awesome project Onetimesecret (https://onetimesecret.com/).   

### Differences from the original
- Containerized (Docker image)
- Deployable on Kubernetes and OpenShift
- No accounts and paid features, just secret sharing
- Customized for Pareto

### Image details
- Base image: `ruby:2.5.9` (official image from Docker Hub) <img src="https://www.ruby-lang.org/favicon.ico" alt="Ruby Icon" height="20"/>
- This image is designed to run on Kubernetes/OpenShift __together with a REDIS container in a pod (see examples)__.  
- The container can and should be run unprivileged (leveraging the OCP arbitrary user ID feature).  

### Variables
| Name | Description | Default value |
|---|---|---|
| OTS_DOMAIN | The domain name, which points to this instance | <none - required to be set> |
| OTS_MASTER_KEY | Global secret (gets combined with the users key to encrypt the secret) | <none - required to be set> |
| OTS_REDIS_PW | Password for REDIS access | <none - required to be set> |
| OTS_REDIS_HOST | The hostname or IP address of the REDIS instance | <none - required to be set> |
| OTS_REDIS_PORT | The port of the REDIS instance | <none - required to be set> |
| OTS_SSL | Use SSL or not | true |
| OTS_CREATE_SECRET |  | 250 |
| OTS_CREATE_ACCOUNT |  | 10 |
| OTS_UPDATE_ACCOUNT |  | 10 |
| OTS_EMAIL_RECIPIENT |  | 50 |
| OTS_SEND_FEEDBACK |  | 10 |
| OTS_AUTHENTICATE_SESSION |  | 5 |
| OTS_HOMEPAGE |  | 500 |
| OTS_DASHBOARD |  | 1000 |
| OTS_FAILED_PASSPHRASE |  | 5 |
| OTS_SHOW_METADATA |  | 1000 |
| OTS_SHOW_SECRET |  | 1000 |
| OTS_BURN_SECRET |  | 1000 |
| OTS_IMAGE_FAV_ICON | link to the custom icon (png) | <none - defaults to the original icon> |
| OTS_IMAGE_LOGO | link to the custom logo (png) | <none - defaults to the original logo> |
| OTS_COLOR | CSS color code (#XXXXXX) | #dd4a22 |


### OpenShift deployment config
You can find an example template for OTS on OCP in the examples folder.
