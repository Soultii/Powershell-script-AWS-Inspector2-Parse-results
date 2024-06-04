# AWS Inspector Parsing PowerShell Script

## Prerequisites

### PowerShell AWS Module

``` PowerShell
Install-Module -Name AWS.Tools.Installer
Install-AWSToolsModule AWS.Tools.Common, AWS.Tools.Inspector2, AWS.Tools.S3, AWS.Tools.SecurityToken, AWS.Tools.SSO, AWS.Tools.SSOOIDC -MinimumVersion 4.1.0.0 -MaximumVersion 4.2.0.0
```
|Minimum PowerShell|
|---------------|
|version 5.1|

Tested with:
| Module | Version |
| ----------- | ----------- |
| AWS.Tools.Installer | 1.0.2.5 |
| AWS.Tools.Common | 4.1.592 |
| AWS.Tools.Inspector2 | 4.1.592 |
| AWS.Tools.S3 | 4.1.592 |
| AWS.Tools.SecurityToken | 4.1.592 |
| AWS.Tools.SSO | 4.1.592 |
| AWS.Tools.SSOOIDC | 4.1.592 |

Connect to your AWS Account via SSO:

``` PowerShell
Initialize-AWSSSOConfiguration
```
.aws/config example
``` Sh
[profile my-sso-profile]
sso_account_id=111122223333
sso_role_name=SamplePermissionSet
sso_session=my-sso-session

[sso-session my-sso-session]
sso_region=us-west-2
sso_registration_scopes=sso:account:access
sso_start_url=https://provided-domain.awsapps.com/start/
```

``` PowerShell
Invoke-AWSSSOLogin -ProfileName my-sso-profile
```
