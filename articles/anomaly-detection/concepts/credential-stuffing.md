---
title: Credential Stuffing Attack Protection
description: Understand how Auth0 detects anomalies to stop malicious attempts to access your application, alert you and your users of suspicious activity, and block further login attempts. 
topics:
    - security
    - anomaly-detection
    - credential-stuffing
contentType: concept
useCase: anomaly-detection
---
# Credential Stuffing Attack Protection

Use **Automated Attack Protection** to provide a standard level of protection against credential stuffing attacks that does not add any friction to legitimate users. This protection is enabled by default for all connections. 

Credential stuffing (or *list validation*) attacks are a type of brute-force attack which attempts to compromise a large number of user accounts with stolen credentials. At Auth0, credential stuffing attacks account for, on average, nearly half of all login attempts using our platform. 

To detect this type of attack, Auth0 uses a large amount of data to identify patterns that signal that a credential stuffing attack is taking place. Using sophisticated algorithms, Auth0 can identify when bursts of traffic are likely to be from a bot or script, and performs the following:

- Provides a score that measures the likelihood of an individual operation coming from an IP associated with credential stuffing attacks. Use this score to trigger rules or custom logic in the Auth0 platform. 
- Shows a CAPTCHA (Completely Automated Public Turing Test To Tell Computers and Humans Apart) step during the sign in or sign up flows.  This CAPTCHA step helps prevent bad actors from continuing to send credential stuffing attack traffic to your tenant.

Auth0 automatically analyzes anonymized login data to detect when a customer is likely to be experiencing a credential stuffing attack.  When such an attack is detected, it throws a CAPTCHA step in the login experience to eliminate bot and scripted traffic.

Download this free [whitepaper](https://auth0.com/resources/whitepapers/credential-stuffing-attacks) to learn how Auth0 can help you combat credential stuffing attacks.

Credential stuffing attacks (also known as *list validation attacks*) occur when bad actors automate the process of trying username and password combinations (usually stolen from another site) for many accounts in a short period of time.  According to recent statistics, as many as 71% of accounts use the same password across multiple sites so a credential stuffing attack has the potential to successfully log into your system.  

Consider, for example, the number of errors caused by an incorrect email or username (identified in the logs as type `fu`) for a particular tenant, which suggests an attack occurred November 20, with some abuse patterns afterwards:

![Credential Stuffing Attack Example](/media/articles/anomaly-detection/credential-stuffing-attack.png)

## How it works

Auth0 uses a large amount of data to identify patterns that signal that a credential stuffing attack is taking place. Auth0 uses sophisticated algorithms to determine when bursts of traffic are likely to be from a bot or script. Users attempting to sign in from IPs which are determined to have a high likelihood of being a credential stuffing attack will see a CAPTCHA step. The algorithms are designed so that this only happens for bad traffic; the objective is to not show any friction to legitimate users.

![CAPTCHA Login Screen Example](/media/articles/anomaly-detection/captcha-login-screen.png)

## Keep reading

* [Enable and Disable Automated Attack Protection](/anomaly-detection/guides/enable-disable-automated-attack-protection)
* [Attack Protection Triggers and Actions](/anomaly-detection/references/attack-protection-triggers-actions)
* [Customize Blocked Account Emails](/anomaly-detection/guides/customize-blocked-account-emails)
* [View Anomaly Detection Events](/anomaly-detection/guides/view-anomaly-detection-events)