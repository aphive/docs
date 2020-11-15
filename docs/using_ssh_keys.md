## Choosing an Algorithm and Key Size
I use **ecdsa** should you be wondering as I use in the examples.

!!! quote
    SSH supports several public key algorithms for authentication keys. These include:

    **rsa** - an old algorithm based on the difficulty of factoring large numbers. A key size of at least 2048 bits is recommended for RSA; 4096 bits is better. RSA is getting old and significant advances are being made in factoring. Choosing a different algorithm may be advisable. It is quite possible the RSA algorithm will become practically breakable in the foreseeable future. All SSH clients support this algorithm.

    **dsa** - an old US government Digital Signature Algorithm. It is based on the difficulty of computing discrete logarithms. A key size of 1024 would normally be used with it. DSA in its original form is no longer recommended.

    **ecdsa** - a new Digital Signature Algorithm standarized by the US government, using elliptic curves. This is probably a good algorithm for current applications. Only three key sizes are supported: 256, 384, and 521 (sic!) bits. We would recommend always using it with 521 bits, since the keys are still small and probably more secure than the smaller keys (even though they should be safe as well). Most SSH clients now support this algorithm.

    **ed25519** - this is a new algorithm added in OpenSSH. Support for it in clients is not yet universal. Thus its use in general purpose applications may not yet be advisable.

    ~ [Source: ssh.com](https://www.ssh.com/ssh/keygen/)

!!! important
    Remember to change the defaults I'm noting below so this works for you. If you need more than one key, keep that in mind also so you are not overwriting your keys.

## Generating your Key(s)

Run the following command to generate your key, repeat as needed to create more. To explain the command a bit:

* `-t ecdsa` - Which Algorithm to use to build the key.
* `-b 521` - How many bits to apply to the key.
* `-C "your_message"` - Add a custom message to the key. You can leave this out if you choose.
* `-f "/home/usrname/.ssh/key_name_here"` - Where to save the key.

```
ssh-keygen -t ecdsa -b 521 -C "your_message" -f "/home/cayobuay/.ssh/id_ecdsa"
```

You will now be prompted to enter your passphrase, while this is not mandatory; we strongly suggest using one.

```
Generating public/private ecdsa key pair.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```

Once the key is generated, you will see an output like this:

```
Generating public/private ecdsa key pair.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/usrname/.ssh/id_ecdsa
Your public key has been saved in /home/usrname/.ssh/id_ecdsa.pub
The key fingerprint is:
SHA256:vEcqEgn2oHbtJkV5Niscgd1SZKDC6UpURuy5n4Iva4Q message
The key's randomart image is:
+---[ECDSA 521]---+
|  o+oo=+         |
|. +o.o+.         |
| ==..+.+         |
|oo.*+.+.o        |
|o+ .== .S .      |
|E...o..  +       |
|o ..ooo o .      |
| + .o+ . .       |
|..+..            |
+----[SHA256]-----+
```

That's it, you have SSH Keys that you can use where needed. Github for example.

## Adding your SSH Keys to your SSH Agent

Start the SSH Agent in the background
```
eval "$(ssh-agent -s)"
```

Add your key:
```
ssh-add ~/.ssh/id_ecdsa
```

Autoload keys into your keychain. I use vim, but change vi to your editor of choice.
```
vi ~/.ssh/config
```

Paste in the following
```
Host *
  AddKeysToAgent yes
  IdentityFile ~/.ssh/id_ecdsa
```

Run the following command
```
ssh-add -K ~/.ssh/id_ecdsa
```

List all managed keys
```
ssh-add -l
```

That's it, your keys are ready to be used.
