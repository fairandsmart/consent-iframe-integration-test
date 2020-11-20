# fair[&]smart - consent iframe integration test

Some code to demonstrate and check the lifecycle of a concent form created using Fair and Smart Right Consent platform.

## in a nutshell
* put your own values (organization ID, model ID etc ...) in config.ini ;
* build the image : `docker build --tag consent-iframe-integration-test .`
* run the container : `docker run consent-iframe-integration-test`

## configuration
Configuration can either be done in config.ini or using environment variables (especially useful when running using
docker).

| parameter  | environment variable name  | config file key  | 
|---|---|---|
| authorized emails | AUTHORIZED_EMAILS | authorized_emails |
| auth server url | AUTH_URL | auth_url |
| auth server realm | AUTH_REALM | auth_realm |
| auth server clientid | AUTH_CLIENT_ID | auth_client_id |
| auth server username | AUTH_USERNAME | auth_username |
| auth server password | AUTH_PASSWORD | auth_password |
| api server url | API_URL | api_url |
| organisation id | ORGANISATION_ID | organisation_id |
| model id or alias | MODEL_ID_OR_ALIAS | model_id_or_alias |

Configuration file is loaded from CONFIG_FILE_PATH (default : "config.ini"). 
 
## run example
Under docker, using a specific config file "my-config.ini" :

`docker run --mount type=bind,source=$PWD/my-config.ini,target=/var/www/html/my-config.ini -e CONFIG_FILE_PATH="my-config.ini" consent-iframe-integration-test`
