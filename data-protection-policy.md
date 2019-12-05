# Data Protection Policy 

As a contractor for the Company, you agree to undertake the following in the daily course of business:
* Take all necessary measures to ensure that any source code, client-related data, secrets, etc. will remain in secure storage while they are being worked on.
* Promptly remove any and all assets for a client in the event of a project becoming terminated or a lapse in work for a client for a period of 6 weeks. This includes and all backups of all client-related data.
* Encrypt all backups or you will exclude from backups all source code, databases, and assets for each client.
* Utilize 2FA for services which provide them (e.g. Github).

In order to protect the Client, you agree to immediately alert the Company in any of these events:
* Any breach or potential breach of confidential information, including but not limited to: loss or theft of hard drives, backups, USB drives, laptops, computers which contain source code, assets, or databases related to client work, password managers, and unprotected (i.e. passwordless) SSH keys used to access servers.
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

Here are a number of recommendations for developers to keep their environments secure.

1. Use full-disk encryption on your computers, especially laptops.
2. Create and use SSH keys which are appropriate. (cf. https://paragonie.com/blog/2019/03/definitive-2019-guide-cryptographic-key-sizes-and-algorithm-recommendations)
3. If you are operating mobile, use a VPN to encrypt your traffic.
4. If you are using Windows, install Windows Defender and keep it updated.
5. Use passphrases on your SSH keys.
6. Never share your login with anyone. Always provide a login to them.
7. Use a different password for every service.
8. Use a password manager such as 1Password.
9. If you have no need for a secret or data, delete it immediately.
