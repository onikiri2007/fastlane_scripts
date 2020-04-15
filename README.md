# Initial setup

1. Clone repo
2. Go to certificates folder.
3. open certificates/.fastlane/Appfile and add your apple id
4. run the commands below

# Available Actions

### certificate_cli

#### download and install apple certificates and provisional profiles when run in CI.

#### eg. You can setup CI to trigger when the certificate repo is updated and run this scripts to install

```
fastlane certificate_cli keychain_name:"login" keychain_password:xxxx
```

| Parameters        |                     Description                      | default |
| ----------------- | :--------------------------------------------------: | ------: |
| keychain_name     | name of the keychain you want to store cerificate to |         |
| keychain_password |                password of keychanin                 |         |

### certificates

#### download and install apple certificates and provisional profiles for all teams that running user has access to.

```
fastlane certificates readonly:true recreate:false team_id:xxxx keychain_name:xxxx keychain_password:xxx env:"development"
```

| Parameters        |                                                               Description                                                                |                                                           default |
| ----------------- | :--------------------------------------------------------------------------------------------------------------------------------------: | ----------------------------------------------------------------: |
| readonly          | when false it will download and create new provisional profile if doesn't eixsts and install certificate on keychain as well as git repo |                                                              true |
| recreate          |                                flush the certificate lists from the cert store and recreate in cert repo                                 |                                                             false |
| team_id           |                                                              id of the team                                                              |                                                                   |
| keychain_name     |                                           name of the keychain you want to store cerificate to                                           |                                                                   |
| keychain_password |                                                          password of keychanin                                                           |                                                                   |
| env               |                                               environment of the certificate to be created                                               | development (development), staging (adhoc), production (appstore) |

### certificate

#### create and download and install apple certificate for a single bundle identifier for a team.

```
fastlane certificate readonly:true recreate:false keychain_name:xxxx keychain_password:xxxx env:development name: insighttimer
```

| Parameters        |                                                               Description                                                                |                                                           default |
| ----------------- | :--------------------------------------------------------------------------------------------------------------------------------------: | ----------------------------------------------------------------: |
| readonly          | when false it will download and create new provisional profile if doesn't eixsts and install certificate on keychain as well as git repo |                                                              true |
| recreate          |                                flush the certificate lists from the cert store and recreate in cert repo                                 |                                                             false |
| team_id           |                                                              id of the team                                                              |                                                          optional |
| keychain_name     |                                           name of the keychain you want to store cerificate to                                           |                                                                   |
| keychain_password |                                                          password of keychanin                                                           |                                                                   |
| env               |                                               environment of the certificate to be created                                               | development (development), staging (adhoc), production (appstore) |
| app_identifier    |                                      full bundle identifier. required either name or app_identifier                                      |                                                                   |

### push_notification_certificates

#### download and install push notification certificates all teams.

```
fastlane push_notification_certificates keychain_password:xxxx
```

| Parameters        |      Description      | default |
| ----------------- | :-------------------: | ------: |
| keychain_password | password of keychanin |         |

### setup_app

#### create an app identifier in developer portal for given identifier.

```
fastlane setup_app app_identifier:com.ghoerg.xxx app_name:dghoerg
```

| Parameters        |                                                                Description                                                                 |                                                           default |
| ----------------- | :----------------------------------------------------------------------------------------------------------------------------------------: | ----------------------------------------------------------------: |
| enable_services   | list of services enabled in cert eg nfc see fastlane produce for parameters push_notification and associated_domain are enabled by default |                                                                   |
| keychain_name     |                                            name of the keychain you want to store cerificate to                                            |                                                                   |
| keychain_password |                                                           password of keychanin                                                            |                                                                   |
| env               |                                                environment of the certificate to be created                                                | development (development), staging (adhoc), production (appstore) |
| app_identifier    |                                                   full bundle identifier. app_identifier                                                   |                                                          required |
| app_name          |                                                              name of the app                                                               |                                                          required |

### create_push_notification_certificate

#### create push notification for given identifier.

```
fastlane create_push_notification_certificate
```

| Parameters        |                          Description                           |                                                           default |
| ----------------- | :------------------------------------------------------------: | ----------------------------------------------------------------: |
| keychain_name     |      name of the keychain you want to store cerificate to      |                                                                   |
| keychain_password |                     password of keychanin                      |                                                                   |
| env               |          environment of the certificate to be created          | development (development), staging (adhoc), production (appstore) |
| app_identifier    | full bundle identifier. required either name or app_identifier |                                                                   |

### renew

#### be very careful executing this command. it will nuke all the certificates for particular type

```
fastlane renew
```

| Parameters |       Description        |                               default |
| ---------- | :----------------------: | ------------------------------------: |
| type       | type of the cert to nuke | development, distribution, enterprise |

### list_teams

```
fastlane list_teams
```

---

This README.md is auto-generated and will be re-generated every time [fastlane](https://fastlane.tools) is run.
More information about fastlane can be found on [fastlane.tools](https://fastlane.tools).
The documentation of fastlane can be found on [docs.fastlane.tools](https://docs.fastlane.tools).
