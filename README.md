# veracode-cli-shortcuts

Collection of handy `zsh` CLI shortcuts for Veracode APIs. These shortcuts use `httpie` and `jq` to make using the Veracode APIs from the command line easier.

## Setup

Clone this repository:

```shell
git clone https://github.com/tjarrettveracode/veracode-cli-shortcuts
```

Install dependencies and configure your credentials:

* [Veracode API signing tool](https://docs.veracode.com/r/t_install_api_authen)
* [jq](https://stedolan.github.io/jq/download/)
* [Veracode credentials file](https://docs.veracode.com/r/c_configure_api_cred_file) or [Veracode credentials environment variables](https://docs.veracode.com/r/t_store_creds_linux_env)

Copy the `.veracode_alias` file to your user's root directory:

```shell
cp .veracode_alias ~
```
Edit your `.zshrc` file and add the following lines:

```shell
#source aliases
ALIASFILE=~/.veracode_alias
source $ALIASFILE
```

Then open a new terminal window so that the changes to `.zshrc` take effect.

## Run

The `.veracode_alias` file contains aliases and functions that can be used to automate routine tasks using the [Veracode APIs](https://docs.veracode.com/r/c_gettingstarted). These include:

* `vcwhoami`: prints the user name associated with the currently active Veracode credentials.
* `vcexpires`: prints the expiration date for the currently active Veracode credentials.
* `vcroles`: prints the list of roles associated with the currently active Veracode credentials.
* `vcappcount`: prints the number of application profiles visible in the Veracode platform using the currently active Veracode credentials.
* `vcrenewcreds`: (REQUIRES CONFIRMATION) generates and prints to the console new API credentials for the currently active Veracode user, and sets the existing credentials to expire in 24 hours. *Caution*: You must copy these credentials from the console or they will be lost!
* `vcfindapp` (*appname*): Looks for applications with names that match `appname` and returns the GUID for the first matching application.

*Note*: Typing `vc` and then tabbing at the command line will list all the available commands that start with `vc`.

## Contributing

Got an idea for more Veracode command line shortcuts? Want to improve one of the current ones? We accept pull requests!
