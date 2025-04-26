## Identity Access Management (IAM)

This is a global service.

A root account is created first, but it shouldn't be used thereafter, we should create new users instead.

Users can be grouped.

Groups only contain users, not other groups.

A user can be in multiple groups, and users don't *need* to be in groups.

## IAM permissions

User permissions are defined as *policies*, which are JSON documents that manage user permissions. 

AWS follows the **least privilege principle**, meaning you don't give more permissions than a user needs. 

## Policy inheritence 

User inherit policies from the team(s) they belong to. But you can also create an **inline policy**, which is a policy just for one user, assuming they don't belong to a group. 

If a user belong to 2 groups, they will inherit the permissions from both groups. 

## IAM Policy

Consist of:

1. Version
2. ID
3. Statement

Statements consist of ids, effects, principals, actions and resources. 

## Protecting your account

There are two main ways to protect an account, a password policy and Multi Factor Authentication (MFA)

### Password policy

This policy defines what type of password users can store (character and length etc) but also how often the password resets, whether the user can use the same password more than once etc.

### MFA

This is an additional step during login and requires a user to type in an additional code once they have submitted their password. There are four ways to do this:

1. A virtual device like Google Authenticator
2. A security key (U2F) device
3. Hardware key fob
4. Hardware key fob (

## Protecting your account

There are two main ways to protect an account, a password policy and Multi Factor Authentication (MFA)

### Password policy

This policy defines what type of password users can store (character and length etc) but also how often the password resets, whether the user can use the same password more than once etc.

### MFA

This is an additional step during login and requires a user to type in an additional code once they have submitted their password. There are four ways to do this:

1. A virtual device like Google Authenticator
2. A security key (U2F) device
3. Hardware key fob
4. Hardware key fob (for AWS GovCloud US)

## IAM roles for services

Sometimes we need services to perform actions for us. For example we can have an EC2 instance and we need that instance to manage our AWS account.

To do this we use IAM Roles. 

For example, we create a role that is trusted by a service, such as EC2. This role may have permissions like accessing `IAMReadOnlyAccess`. Now our EC2 instance can read our IAM.

## Security tools

### IAM Credentials Report

This lists all users and their credentials.

### Access Advisor

This lists individual users and the permissions granted to them, including them they last accessed the services. This allows you to understand which services the users has access to and which you might want to revoke. 

## Best practices for IAM

- Don't use root account except for setup
- 1 physical users should = one AWS user
- Assign users to groups and assign permissions to groups
- Create strong pw policy
- Use and enforce MFA
- Create Roles for giving permissions to AWS services
- Use access keys for programmatuc access
- Audit permissions using Access Advisor
-  Never share IAM user & access keys

## Overview

- Users are physical users and each have their own access
- Groups contain users only
- Policies are JSON docs with permissions
- Roles give features AWS access
- Security: MFA + p/w policy
- CLI/SDK are programmatic acesss
- Access keys : give programmatic access
- Audit users with credential reports and access advisor
