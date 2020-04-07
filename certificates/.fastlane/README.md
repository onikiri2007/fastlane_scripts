fastlane documentation
================
# Installation

Make sure you have the latest version of the Xcode command line tools installed:

```
xcode-select --install
```

Install _fastlane_ using
```
[sudo] gem install fastlane -NV
```
or alternatively using `brew cask install fastlane`

1. open Matchfile
2, change the git_url to your repository where you store certificates

# Available Actions
### certificate_cli
```
fastlane certificate_cli keychain_name:"login" keychain_password:xxxx
```
| Parameters   |      Description      |  default |
|----------|:-------------:|------:|
| keychain_name |  name of the keychain you want to store cerificate to |  |
| keychain_password |    password of keychanin   |   |


### certificates
```
fastlane certificates readonly:true recreate:false team_id:xxxx keychain_name:xxxx keychain_password:xxx env:"development"
```
| Parameters   |      Description      |  default |
|----------|:-------------:|------:|
| readonly | when false it will download and install certificate on keychain as well as git repo  | true |
| recreate | flush the certificate lists from the cert store and recreate in cert repo |   false |
| team_id |   id of the team  |    |
| keychain_name |  name of the keychain you want to store cerificate to |  |
| keychain_password |    password of keychanin   |   |
| env |  environment of the certificate to be created  | development, staging, production  |


### certificate
```
fastlane certificate readonly:true recreate:false keychain_name:xxxx keychain_password:xxxx env:development name: insighttimer
```
| Parameters   |      Description      |  default |
|----------|:-------------:|------:|
| readonly | when false it will download and install certificate on keychain as well as git repo  | true |
| recreate | flush the certificate lists from the cert store and recreate in cert repo |   false |
| team_id |   id of the team  |  optional  |
| keychain_name |  name of the keychain you want to store cerificate to |  |
| keychain_password |    password of keychanin   |   |
| env |  environment of the certificate to be created  | development, staging, production  |
| name |  name of the app without bundle id | |


### push_notification_certificates
```
fastlane push_notification_certificates keychain_password:xxxx
```
| Parameters   |      Description      |  default |
|----------|:-------------:|------:|
| keychain_password |    password of keychanin   |   |


### setup_app
```
fastlane setup_app name:xxxx 
```
| Parameters   |      Description      |  default |
|----------|:-------------:|------:|
| enable_services | list of services enabled in cert  eg nfc see fastlane produce for parameters push_notification and associated_domain are enabled by default |  |
| keychain_name |  name of the keychain you want to store cerificate to |  |
| keychain_password |    password of keychanin   |   |
| env |  environment of the certificate to be created  | development, staging, production  |
| name |  name of the app without bundle id | |


### create_push_notification_certificate
```
fastlane create_push_notification_certificate
```

| Parameters   |      Description      |  default |
|----------|:-------------:|------:|
| keychain_name |  name of the keychain you want to store cerificate to |  |
| keychain_password |    password of keychanin   |   |
| env |  environment of the certificate to be created  | development, staging, production  |
| name |  name of the app without bundle id | |


### renew
#### be very careful executing this command

```
fastlane renew
```
| Parameters   |      Description      |  default |
|----------|:-------------:|------:|
| type |  type of the cert to nuke | development, distribution, enterprise |


### list_teams
```
fastlane list_teams
```


----

This README.md is auto-generated and will be re-generated every time [fastlane](https://fastlane.tools) is run.
More information about fastlane can be found on [fastlane.tools](https://fastlane.tools).
The documentation of fastlane can be found on [docs.fastlane.tools](https://docs.fastlane.tools).
