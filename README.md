# aws-switch
Quickly switch between AWS accounts on the command line

Uses [aws-profile](https://pypi.org/project/aws-profile/) to generate AWS keys, assume role etc and spawns a new shell with these values populated.

## Prerequisites

### aws-profile

`pip install --upgrade awscli aws-profile`

## Install

Git clone and add the `aws-switch` script to your PATH

**Todo:** brew install

## Usage

`aws-switch [--help|-h] PROFILE`

Where PROFILE is defined in your [AWS config](https://docs.aws.amazon.com/cli/latest/userguide/cli-config-files.html), for example:

```
[profile my-aws-account]
region = eu-west-1
# other options, including output, role_arn, mfa_serial etc.
```

```
# aws-switch my-aws-account
Switching to AWS profile my-aws-account...

# echo $AWS_SWITCH_PROFILE
my-aws-account

# aws sts get-caller-identity
[ Verify your user details, account ID etc. ]
```

The `AWS_SWITCH_PROFILE` env var is set in the spawned shell for debugging purposes.

## Info

Originally developed by [Adam Westbrook](http://www.adamwestbrook.info)

[Licence](./LICENSE)

Source, issues and questions available on [Github](https://github.com/adamdodev/aws-switch)

Please feel free to contribute, comments, fixes and improvements using the issue tracker linked above.
