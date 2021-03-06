# tools to run ThreeFold web env

starting point to run all wiki's and websites on your local machine

- wiki's
- websites

## to install

copy the following in your terminal, will install the tools (OSX only for now).

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/crystaluniverse/publishtools/master/scripts/install.sh)"
```

## Requirements

Make sure your ssh-key is loaded and you have it in your github account

## quick instructions

### install & run

```bash
#install the publishtools
publishtools install
#re-install (if something is wrong, do an install -reset)
publishtools install -reset
#re-install and pull newest website code in
publishtools install -reset -pull
#list the known sites(will show if changes in the repo)
publishtools list
#start development mode of website cloud (specify part of name of website is good enough)
#is using gridsome
publishtools develop -r cloud
#run the webserver for the wiki's
publishtools develop
#build all websites & wiki's, will take long time
publishtools build
#specify to build for 1 specific website (name is part of name)
publishtools build -r cloud
```

> remark: this will checkout all relevant repo's on ~/codewww <BR>

### develop / commit

```bash
#list repo's show if there are changes
publishtools list
#commit changes, specify repo name
publishtools commit -r info_cloud
#commit changes, specify part of repo name
publishtools commit -r info_
#commit changes, specify commit message
publishtools commit -r info_ -m 'my message'
#commit changes, specify commit message, no quotes, cannot have spaces then
publishtools commit -r info_ -m mymessage
#commit same message on all repo's
publishtools commit -m mymessage
#commit & push changes (message & repo are optional)
publishtools pushcommit -r info_ -m 'my message'
#pull changes from github (repo name is optional)
publishtools pull -r info_
#push changes to github (repo name is optional)
publishtools push -r info_
```

## edit code for a website/wiki

```bash
#open code editor (visual studio code)
publishtools edit -r legal

```

remarks

- when specifying a name for edit, will open the first repo it finds which matches the name
- for using edit, you need visual studio code installed with command line integration
  - see https://code.visualstudio.com/docs/setup/mac the launching from command line
- make sure your ssh-agent is loaded !

## work with your ssh keys

see [instructions](docs/sshkey.md)

## recommended tools

- sourectree (manage your git repositories)
- ms visual studio code

## advanced usage

```bash
#will go over all repo's and update the repo's after cleaning up e.g. the wiki's
#a lot of automation happens here, be careful
publishtools install -clean
```
