# Aws-vault





{% embed url="https://github.com/99designs/aws-vault" %}

aws-vault reference:

[Aws-vault - Secure Access To Multiple AWS Accounts 2023](https://hands-on.cloud/how-to-securly-manage-connections-to-multiple-aws-accounts/)

[https://faun.pub/step-by-step-aws-iam-assumerole-with-aws-vault-configuration-9d5986373c33](https://faun.pub/step-by-step-aws-iam-assumerole-with-aws-vault-configuration-9d5986373c33)

&#x20;

AWS Roles Github Link



#### Configure AWS Tools <a href="#configure-aws-tools" id="configure-aws-tools"></a>

* Install AWS cli - [![](https://docs.aws.amazon.com/assets/images/favicon.ico)Install or update the latest version of the AWS CLI - AWS Command Line Interface](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-mac.html)
*   Install aws-vault

    `brew install aws-vault`
* Add profile to vault \[$profilename = aws-account-name]

```bash
aws-vault add profile-name vim $HOME/.aws/config
```

* Paste the following code into config file

```
[default]
region = ap-southeast-2
output = text

[profile $profilename]
region = ap-southeast-2
output = text

# App-Dev
[profile app-dev]
source_profile = $profilename
role_arn = arn:aws:iam::123456789012:role/system/admin

# App-QA
[profile app-qa]
source_profile = $profilename
role_arn = arn:aws:iam::123456789012:role/system/admin

# App-Prod
[profile app-prod]
source_profile = $profilename
role_arn = arn:aws:iam::123456789012:role/system/admin


```

#### Configure CLI Tools <a href="#configure-cli-tools" id="configure-cli-tools"></a>

*   Generate SSH key

    `ssh-keygen -t rsa -b 4096`
* Install zsh

`sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)" git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions configure ~/.zshrc`

*   Add these lines into your \~/.zshrc file and reload terminal

    `alias awsljh='aws-vault exec ljhgroup --' alias awsapt='aws-vault exec app-test --' alias awsapp='aws-vault exec app-prod --' alias awsalp='aws-vault exec atlas-prod --' alias awsalt='aws-vault exec atlas-test --' alias awscau='aws-vault exec classic-au --' alias awscnz='aws-vault exec classic-nz --' alias awsdpd='aws-vault exec data-prod --' alias awsdtt='aws-vault exec data-test --' alias awsmgt='aws-vault exec mgmt --' alias code="open -a Visual\ Studio\ Code.app" export PATH="$HOME/.tgenv/bin:$PATH"`

**Key rotation command for long term using keys**

`➜ ~ aws-vault rotate ljhooker Rotating credentials for profile "ljhooker" (takes 10-20 seconds) Done!`\


