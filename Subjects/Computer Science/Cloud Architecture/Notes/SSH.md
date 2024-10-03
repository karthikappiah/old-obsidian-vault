# SSH

SSH is a network protocol that connects authenticated users to remote servers and services over an insecure network.

## Usage

Use the SSH agent to generate a public and private key pair on the local computer.

```shell
ssh-keygen -t ed25519 -C "username@email.com"
```

Write the public key's contents to `~/.ssh/authorized_keys` on the remote computer to grant the local computer access to the remote computer.

SSH into the remote computer from the local computer.

```shell
ssh -i ~/.ssh/private_key username@hostname
```

Add the key pair to the SSH agent to skip specifying the private key's path.

```shell
ssh-add -l
ssh-add ~/.ssh/private_key
```

## SSH into GitHub

1. [Generate a new SSH key and add it to the SSH agent.](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
2. [Add the SSH key to GitHub](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)
3. [SSH into GitHub](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection)