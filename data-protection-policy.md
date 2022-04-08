# Data Protection Policy 

As a contractor or employee for the Company, you agree to undertake the following in the daily course of business:
* Take all necessary measures to ensure that any source code, client-related data, secrets, etc. will remain in secure storage while they are being worked on.
* Promptly remove any and all assets for a client in the event of a project becoming terminated or a lapse in work for a client for a period of 6 weeks. This includes and all backups of all client-related data.
* Exclude from any and all personal backups: all source code, databases, and assets.
* Utilize 2FA for services which provide them (e.g. GitHub, Cloudflare).

In order to protect the Client, you agree to immediately alert the Company in any of these events:
* Any breach or potential breach of confidential information, including but not limited to: loss or theft of hard drives, backups, USB drives, laptops, computers which contained or might have contained source code, assets, or databases related to client work, password managers, and unprotected (i.e. passwordless) SSH keys used to access servers.
* Upon discovery of unsafe or potentially liable situations including but not limited to: public availability of private keys, assets, or passwords, source code, configuration files, databases, database dumps, or any other proprietary or private information or customer-related PII.
* Any employee departure along with the employee’s SSH keys or hashes, email addresses, related logins and credentials which must be disabled or reset.

Likewise, the Company agrees to:
* Provide training and resources for the enabling of developers to access and understand best practices.
* Provide, free of charge and without compensation, time for training of key staff and persons managing developers and developer-related hardware.
* Work with the client to ensure that best practices are managed from the top of the project down to developers.
* Alert the contractor(s) to any changes or deviations from this agreement.
* Inform the client of the above in order to ensure that they understand this agreement and assent to what it says.
* Attempt to provide resources from the client which limit the exposure and liability of both the client and of the contractor to potential harm or breeches of confidential information.

# Practice and Application

Here are a number of best practices you are expected to follow to keep your environments secure.

1. Use full-disk encryption on all work computers.
2. Never copy your work onto an unapproved computer.
3. Create and use SSH keys which are appropriate. (cf. https://paragonie.com/blog/2019/03/definitive-2019-guide-cryptographic-key-sizes-and-algorithm-recommendations). As of the current writing you should be using ED25519 keys *with* a passphrase.
4. If you are operating away from home, use a VPN to encrypt all traffic.
5. If you are using Windows, install Windows Defender and keep it updated.
6. Use passphrases on all your SSH keys.
7. Never share your login or passwords with _anyone_.
8. Never use a shared login for a service. Always create separate accounts for each user and give the appropriate access.
9. Use a different password for every service.
10. Use a password manager such as 1Password.
11. If you have no need for a secret or data, delete it immediately.
