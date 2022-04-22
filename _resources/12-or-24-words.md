---
layout: page
title: 12 or 24 words?
---
# 12 or 24 words?
12 words will produce 128 bits of entropy, and 24 words will produce 256 bits of entropy.

You may have heard that 12 words provide enough entropy for a wallet. Technically, the master key for your wallet is 256 bits long, but due to eliptic curve mathematics, this only produces 128 bits of security. This is documented in the official [BIP-32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki#master-key-generation) specification.

> _... the produced keys are only 256 bits long, and offer about half of that in terms of security._

This means that a SHA256 over 128 bits of entropy would be equivalent to the final wallet and anything more is "wasted entropy".

{:.note}
The way we can reason about our security, is by considering the following: given a 128 bit long hash of a message, is it easier to guess the original message, or the hash itself. The lowest common denominator is the maximum security of the key.

## I guess that's settled then, ... right?
Generating entropy relies on having a good source of randomness. Any slight bias in a dice, or any patterns in a sample of sound can cause the entropy to drop slightly. 

Typically, if you attempt to derive exactly 128 bits of entropy, you may end up with slightly less, like 125 bits. That's still pretty secure and is likely to be secure enough for anyone, but if you don't want to have any less than 128 bits of security, then generating more than enough entropy gives us room for error.

A slightly biased die might produce 251 bits of entropy when attempting to produce 256 bits, and although the final master key will compress this to 128 bits of security, you can rest assured that you have that **full** 128 bits of security and no less.

## 24 words is the winner!
Not quite. The other side of the argument is that 24 words is harder to remember, it is harder to manage and easier to mess up.

Afterreading a few online sources*, I'd recommend anything over ~90 bits of entropy is considered pretty uncrackable and safe enough for long term secret keys.

So depending on how you plan to handle your keys and how much bitcoin you plan to store in that wallet, you may opt for 12 words over 24.

*sources:
- <https://en.wikipedia.org/wiki/Password_strength#Required_bits_of_entropy>
- <https://iocane.com.au/talking-passwords-and-entropy/>
- <http://rumkin.com/tools/password/passchk.php>
- <https://planetscale.com/blog/using-entropy-for-user-friendly-strong-passwords>

Keep in mind, that entropy is not simply based on the length and range of the characters that your password uses, randomness is an important factor too.

Articles about the entropy of **passwords** tend to avoid the ugly truth that `awordbasedlongpassword` is not completely random, and therefore provides less entropy than you would calculate depending on what common patterns apply to the password that attackers tend to look for.

(see: [Wikipedia: Human generated passwords](https://en.wikipedia.org/wiki/Password_strength#Human-generated_passwords)).