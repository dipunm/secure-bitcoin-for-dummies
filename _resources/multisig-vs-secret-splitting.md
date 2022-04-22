---
layout: page
title: Multisig vs secret splitting
---

# Multisig vs secret splitting

When considering security, most people will boast that multi-sig setups are the best option we have so far. This article will lay out the pros and cons of secret splitting compared to multi-sig setups to allow you to make your own decision.

## Multi-party setups

Imagine that you create a wallet that contains bitcoin for use by a company. How the bitcoin should be spent is not up to you only, there are two other partners who have an equal say in how the money should be spent.

### Mutli-sig
This is a perfect situation to use a multi-sig wallet; in this case, a 2-of-3 multi-sig wallet would provide the following features:

- In the case of a decision where only one party is in disagreement, the account can still be spent with the approval of only 2 of the 3 parties.
- In the case of death or disappearance of one of the partners, the funds can still be spent, allowing the business to operate.
- In the case that one of the parties loses or compromises their key, the two remaining partners can facilitate moving funds to a new wallet with 3 new uncompromised keys.
- If you disagree with both of your partners, the company funds are protected from you.

Each of the parties will be responsible for a single key, and must protect it from loss, theft and from their partners.

When it comes to signing a transaction, one party must create the transaction and sign it, then pass the signed transaction to another party who will sign over it. Only once two signatures have been added will the transaction be considered valid to the Bitcoin network.

There is no need for the signers to be in the same place when signing takes place, and there is no need for any one person to get access to another party's keys. A great wallet for multi-sig coordination is [Nunchuk](https://nunchuk.io/), allowing for secure end to end encrypted communication between parties and remote signing and coordination.

### Secret splitting
This is **not** an ideal solution for secret splitting. Secret splitting, be it XOR seed words or Shamir's secret sharing scheme, requires parties to reveal their secrets to somebody who can combine the secrets. There is no way for each party to do their part remotely without ever learning the secret of another party.

If you trust your partners, then you may still opt for this option, but for the system to be fair, each party must forget the secret that is not theirs at the time of wallet creation, and at the time of spending every time. The person who does not forget their partners' secrets ultimately owns the account and can spend from the wallet without any restrictions.


## Personal storage

Now imagine a personal wallet with no other parties. You wish to create a security setup that cannot be compromised with a single attack such as a home invasion or an online data leak.

### Multi-sig

Using a multi-sig is not a _bad_ idea. You want to keep your keys on signing devices, for example: one on a personal computer, and one on a hardware wallet; this way, when you want to spend, you can keep your keys isolated from one another.

Each key needs a backup because either of the signing devices can be broken or stolen. The backups should be geographically separated, however keeping one online and the other purely physical may be a reasonable solution.

Another solution is to create more keys with an N of M configuration (eg. 2 of 3 multi-sig). In this case, if one of the signing devices fails, breaks, or is stolen, then you can buy or create a new device and move the funds to a new multi-sig setup. This does, however, require you to know that a device is lost or broken before another is compromised, which is not always immediately obvious. Another potential downside of an N of M multisig wallet is that you will need to back up an XPUB (extended public key) -- another thing to back up.

The more keys you create as part of the setup, the more geographically isolated locations you will need to use to store your backups. Also, if you happen to be a victim of surveilance or spying, then simply by physically going to these locations, you may link the seemingly unrelated locations which may compromise the security of your backups.

Keeping physical hiding places secret is very difficult if you are working alone. In my opinion, sticking to a 2-of-2 allows you to maximise the compromise between security and convenience: 

- One key backed up online and also used by your internet enabled multi-sig wallet when signing
  - keeps that key backed up and unlikely to be lost _(which would render a 2-of-2 multisig wallet unspendable)_, 
  - but very likely to be compromised by online hackers.
- A second key kept completely offline, used only by an air-gapped hardware wallet and supported by two or more physical backups 
  - can protect you from theft _(which would also render a 2-of-2 multisig wallet unspendable)_,
  - while also protecting your wallet from being spent as the other key cannot be stolen by physical means.

With this setup, you remain vulnerable to an attacker who can access your online storage accounts _and_ one of the physical locations where you keep your backups.

A big benefit of multi-sig is that the keys are never combined, so if one of the **signing devices** become compromised, an attacker will not learn all of the keys required to spend from your wallet.

A drawback of this setup is that there is a learning curve to climb to understand how to sign a transaction for a multi-sig wallet. This in turn makes inheritance planning more difficult as the inheritor will need a crash cource in multi-sig wallets as part of their inheritance.

A commonly promoted multi-sig setup involves one service provider. A service provider will hold on to a single key while you hold on to the other two. If one of your keys is lost, you can work with the service provider to move the funds to a new account with three new keys. 

The service provider may even prove useful in the case of an untimely death, an inheritor may work with the service provider to take custody of the funds after proving ample proof of the situation, possibly for a fee. This will usually require the service provider to have your personal information in order for them to facilitate this service.

Unfortunately, although the service provider cannot steal your funds, as they hold only 1 key, they are often able to see your transactions and often will require some form of identity; this setup is not great for privacy.

### Secret splitting

Shared secrets can feel less daunting to a beginner; you only need to sign a transaction once, and although multiple keys must first be combined, it is possible to do offline with pencil and paper (using XOR), and all evidence of the combined key can be physically destroyed once complete.

Since there are no other parties, there is no need to keep the keys isolated and hidden from another key holder at the time of signing a transaction.

With secret splitting, you will use one device to sign a transaction; this makes the process much easier to understand and easier for an inheritor to sweep the funds, but if the device is compromised, then an attacker may learn the combined key when you use the device to sign a transaction.

It is important that when signing a transaction, you are either using a signing device that is difficult to tamper with and that you are confident hasn't been compromised, or you should be using it to sweep the funds to a new wallet so that an attacker has no time to take advantage of the stolen combined key.

The best signing device for this purpose will have no wifi, bluetooth or other wireless hardware, it will have a secure element with a self destruct feature enabled, and will never be plugged into a computer via a data cable such as USB.

Creating and signing a transaction will usually take place on two devices:

- An _internet enabled device_ will create a valid transaction using the latest blockchain data to ensure it is correct,
- The _air gapped hardware wallet_ will receive an unsigned transaction, sign it and return a signed transaction,
- Finally, the internet enabled device will broadcast the transaction across the internet.

There are two popular secret sharing techniques:

- Shamir's secret sharing scheme: allows for an N of M setup giving you the ability to recover in case you lose one of the parts,
- XOR seed words: allows for you to combine the secret without the use of any computer, but does not allow for an N of M setup.

For personal backups, creating an N of M setup may not be so useful when a 2 of 2 backup as described earlier can sufficiently separate your keys while allowing for multiple backups to protect from losses.

