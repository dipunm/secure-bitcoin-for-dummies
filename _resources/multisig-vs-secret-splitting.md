---
layout: page
title: Multisig vs secret splitting
---

# Multisig vs secret splitting

Both multisig and secret splitting can help to achieve a high level of security and assurance for those who need to protect a large sum of bitcoin, but they each come with pros and cons. Multisig is technically a better solution, but secret splitting provides some practical benefits to counter its technical trade offs.

The following table outlines some of the main differences between what can be achieved through multisig and secret splitting:

| | multisig | splitting |
|:-|:-:|:-:|
| Good for multi-party setups | Y | N |
| Can use a single signing device | N* | Y |
| Can protect against malicious or compromised hardware wallets | Y | N |
| Allows creating unique key combinations | N | Y |
| Allows cooperative signing with a third party | Y | N* |

## Good for multi-party setups

Multisig is great for setups where one or more people have joint ownership over some bitcoin. When an agreement is required for every spend, it makes sense to ask each of the owners to sign every transaction.

In some cases, in an organisation for example, you may only need majority vote. In this case, setups such as 2-of-3 or 3-of-5 (N-of-M) will allow an organisation to control its bitcoin with only N signatures avoiding hold ups from unresponsive partners.

Secret splitting is not good for a multi-party setup. Although there are multiple keys involved, there is only 1 signature required, and this signature requires someone to have all the keys together.

The person who signs a transaction will need to collect all the keys before signing and once collected, this person has ultimate, unrestricted control of the full balance within the wallet.

## Can use a single signing device

Multisig typically requires each key to use its own signing device. This isn't strictly true, however in most cases, using the same device to sign with different keys would undermine the security of a multisig setup.

The reason for adding an asteriks to the table was because a device such as the [seed signer](https://seedsigner.com/) can be used to sign with multiple keys without requiring you to bring two or more keys to the same location. Instead the seed signer can travel with you and sign with every key, one at a time.

When splitting a secret, the wallet you are protecting is a simple, single signature wallet. This means that there is only a need for one signature by one key. Each secret will need to be recombined before a signing device can do it's job, but this can be practically easier than attempting to sign a transaction multiple times across multiple devices.

It would be ideal that the device that is used to sign a transaction either is careful to forget the key after use, or it sweeps the whole wallet to a new secure destination.

## Can protect against malicious or compromised hardware wallets

Using a single signing device is a double edged sword. Even when using a multisig setup with the seed signer, if your signing device is compromised, then all the keys required to create a fully signed bitcoin transaction will be exposed to the same vulnerability.

Chain supply attacks are no joke; time and consideration should be taken before choosing a signing a device. Both personal ability and technical security risks should be considered, but when using a single signing device, you are more susceptible to these attacks; the device should also be kept in a safe place to ensure it is not susceptible to tampering.

Using multiple devices is only possible when using multisig, but it can help against both supply chain and on-premise tampering. This does not come for free however, to avoid supply chain attacks:

- You should buy products from different manufacturers, 
- avoid them passing through the same hands (eg. delivery companies), 
- avoid buying them from a single supplier.

After recieving the devices and setting them up, to avoid on-premise tampering:

- You should keep the devices in separate safe locations,
- Avoid anything that might lead anyone to find these devices and think they are related,
- Ensure you have a way to detect if the devices are replaced with decoy devices.

## Allows creating unique key combinations

In a multisig setup, you create a number of keys and use them to generate an address. It is impossible to use any other keys to sign for the wallet, and therefore you will have one set of keys, and although many combinations of these keys can sign a transaction, a single compromised key will make the other keys much more vulnerable.

Imagine a key from a 2-of-3 multisig has been stolen, the other two are now single points of failure; if either one were stolen, you could lose your bitcoin.

More importantly, when thinking about inheritance, you might share enough keys between an inheritor and an inheritance lawyer so that the bitcoin can be spent upon an untimely death. If either of the parties were to leak or fall victim to theft of their respective keys, it not only compromises the inheritance setup, but the keys in question are the same ones you use yourself.

An attacker might target you and others that they suspect will have keys in order to maximise their chances of getting access to your funds.

With a setup scheme similar to [bitcoin vaults]({{ site.baseurl }}/btc-vault/0.primer), an inheritor can rely on a different set of keys than yours, such that an attacker would need to find all of your keys, or all of the inheritor's keys to gain access to the bitcoin, even managing to steal one key from each of you will bear no success.

## Allows cooperative signing with a third party

A popular self custody setup using multisig is provided by some companies such as Casa and Unchained Capital. They offer the service of holding one or more keys on your behalf, but never enough to own your bitcoin; for example, in a 2-of-3 setup, they would hold 1 key and in a 3-of-5 setup, they would hold up to 2 keys.

This type of setup allows us to enlist a third party to assist us in creating our wallets. An important aspect is that the setup gives us full control of the wallet as long as we don't lose or compromise any of our keys, but allows us to entrust third party to secure our alternative keys securely in case we lose one of our keys.

Often, with multisig, the entrusted third party will provide the software that will assist us, and therefore it is important that we pick our third parties carefully and take care when using the software that they provide.

These companies often allow us to use their software to make transactions in tandem with their online servers to facilitate mutlisig signing in a way that feels like a simple mobile wallet. It is important to note that this type of setup will expose all transactions you make to the company and may lead to a sneaky invasion of privacy.

This type of setup allows you to keep a third key somewhere secure and hard to reach, as you will not use the key except in the case where either you lose the key on your mobile device, or the company you are using to facilitate the spending becomes unresponsive or is shut down.

With secret splitting, a similar setup can be achieved theoretically, however it is much less elegant. Instead of a third party signing transactions for you, they will reveal your secret to you over a secure channel whenever you request it and you will use that to sign the transaction yourself.

This type of setup is better for privacy, since the third party has no idea what you intend to sign, but it does have tradeoffs in terms of security depending on how it is implemented.

There are no companies offering such a service, as multisig is simply a more elegant solution, therefore although technically possible, it is not really practical.

## Scenarios and when to use one over the other

This section is purely my own opinion, but after some time, I have come to the following ideas as to what each strategy is useful for:

Multisig:
- Useful if you wish to spend sub-frequently, (eg. once a month)
- Useful if you are confident with using signing devices or are willing to learn
- When implementing inheritance, it will add a burden to the inheritor to learn a multistep recovery involving multiple devices.

Secret splitting:
- Useful for long term cold wallets that are infrequently accessed
- An inheritor may request less help to use a worksheet on paper to combine a secret, than to use multiple devices
- It is best used to harden the security of backups for a single signature wallet.
