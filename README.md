# XPipe Vault (Keep this repository private!)

This repository contains all connection information that is designated to be shared.

You can sync with this repository in all XPipe application instances the same way, every change you make in one instance will be reflected in the repository. 

## Category list

- **Connections**
  - [**Storage**](categories/0c06504c-d162-48af-af98-218781f0e1ea)
  - [**RPi**](categories/5a0a8cea-87e7-47bc-b3c6-6ad7d54161a6)
  - [**Proxmox and VMs**](categories/fc994061-6131-4a9c-8fdc-663e237b4309)
- **Scripts**
  - [**Custom**](categories/d3496db5-b709-41f9-abc0-ee0a660fbab9)
- **Identities**
  - [**Synced**](categories/69aa5040-28dc-451e-b4ff-1192ce5e1e3c)

## Connection list

**All connections / Storage**

empty

**All connections / RPi**

- [**nj-rpi-dns-00**](stores/a9489b13-bb5f-4c61-8f2f-6758da8462ec)
  - [**Shell environments**](stores/070b766a-f261-4777-a630-7dc5429d9544)
    - [**bash**](stores/bb15e78f-06fd-4d1e-bcfc-e82bb6a47487)
    - [**dash**](stores/5a94c65d-9166-496c-b7fb-796818609d0f)
    - [**sudo**](stores/fb1b9e83-a5c2-4739-af2f-ce7f5de6c0c3)
- [**nj-rpi-dns-01**](stores/7fc8acd9-f4d6-46cd-8e82-80521ab8a5fd)
  - [**Shell environments**](stores/d5c6256a-eff5-4613-a77b-361f5cf32367)
    - [**bash**](stores/0c4f6411-ab21-466a-9d93-a9173c0ead8d)
    - [**dash**](stores/ebf55676-4211-4834-84b5-63681bceb0f6)
    - [**sudo**](stores/485eee98-907e-47e4-8ae4-cc9622b53846)
- [**nj-rpi-ups-00**](stores/aa101a2b-e4ad-451a-b39e-d624eb69eb83)
  - [**Docker containers**](stores/733abdc9-613d-4d83-a13d-94e39a09446e)
    - [**default**](stores/df554429-080d-4d1f-84d2-65e55d1c9f5c)
  - [**Shell environments**](stores/01f0b6ab-e9c3-49bb-b05d-c8c4e6446eb7)
    - [**bash**](stores/d4bdcd4b-d7e2-40dd-a09f-a0837d4edb80)
    - [**dash**](stores/92b0d546-da3f-40ca-9e81-b8990d991a06)
    - [**sudo**](stores/b1a514a2-8646-40c0-a5cb-457c3caa80b3)

**All connections / Proxmox and VMs**

empty

**All scripts / Custom**

- [**My scripts**](stores/a9945ad2-db61-4304-97d7-5dc4330691a7)

**All identities / Synced**

- [**Default Login**](stores/995a8b8e-d8b3-48dc-bff4-999115225562)
- [**proxmox login**](stores/0523e2e6-35d9-4143-906e-b74b48426d71)
- [**ssh-key login**](stores/e54354a2-bd1d-4acb-a361-8a1984771fec)
- [**truenas-00**](stores/7edae3fc-e085-4885-8d72-ede760a9c366)
- [**username and password**](stores/dd0efbdd-b35c-4b3f-a73d-90ae9d5ae712)


## Secret encryption

You have the option to fetch any sensitive information like passwords from outside sources like password managers or enter them at connection time through a prompt window. In that case, XPipe doesn't have to store any secrets itself.

In case you choose to store passwords and other secrets within XPipe, all sensitive information is encrypted when it is saved using AES with either:

- A dynamically generated key file `vaultkey` (The data can then only be decrypted with that file present)
- A custom passphrase that can be set for your user in the settings menu, combined with the vaultkey file (This option can only as secure as the password you choose)

By default, general connection data is not encrypted, only secrets are.
So things like hostnames and usernames are stored without encryption, which is in line with many other tools.
There is an available vault setting in the settings menu to encrypt all connection data if you want to do that.

## Cloning the repository on other systems

Nowadays, most providers require a personal access token (PAT) to authenticate from the command-line instead of traditional passwords.
You can find common (PAT) pages here:
- **GitHub**: [Personal access tokens (classic)](https://github.com/settings/tokens)
- **GitLab**: [Personal access token](https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html)
- **BitBucket**: [Personal access token](https://support.atlassian.com/bitbucket-cloud/docs/access-tokens/)
- **Gitea**: `Settings -> Applications -> Manage Access Tokens section`
Set the token permission for repository to Read and Write. The rest of the token permissions can be set as Read.

Even if your git client prompts you for a password, you should enter your token unless your provider still uses passwords.

If you don't want to enter your credentials every time, you can use any git credentials manager for that.
For more information, see for example:
- https://git-scm.com/doc/credential-helpers
- https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git

Some modern git clients also take care of storing credentials automatically.

## Troubleshooting

### Adding connections to the repository

By default, no categories are set to shared so that you have explicit control on what connections to commit.

To have your connections of a category put inside your git repository,
you either need to right-click the category or click on the `⚙️` icon when hovering over the category
in your `Connections` tab under the category overview on the left side.
Then click on `Add to git repository` to sync the category and connections to your git repository.
This will add all shareable connections in that category to the git repository.

### Local connections are not synced

Any connection located under the local machine can not be shared as it refers to connections and data that are only available on the local system.
