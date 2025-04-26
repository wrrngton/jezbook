# AWS CLI, SDK and Cloud Shell

There are 3 ways to access AWS:

1. The web console
2. AWS CLI
3. AWS SDKs

The CLI is open source and allows you to make operations from the command line.

The SDKs allow you to access AWS programatically through API calls using a set of language specific APIs, including: JS, Node, PHP, Python, .NET, Ruby, Java, Go, C++.

## AWS CLI

You need to use an access token to setup the AWS CLI. You define access tokens per user and then user :

`aws configure` to create access for that user from the command line. 

## Cloudshell

You can use cloudshell in the AWS console as well. 

This will automatically use the active user's credentials. It allows for :

- File downloads
- Uploads
- etc etc

It is only available in some regions, however.
