---
layout: page
title: Let's be paranoid
---
# Let's be paranoid
{:.no_toc}

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

Protecting your bitcoin is often difficult because it requires **keeping a secret™**. We know that intuitively, information is hard to keep secret and once it's out, it's out.

This is why bitcoiners are paranoid; the thing about a _bitcoin secret_ is that a it can be worth a lot of money. The good news is that keeping a secret is easier when you take the time, and prepare to protect it.

{:.note}
<div>
Let's be clear, the **secret** we are talking about is our private key which we are usually told to keep safe and secure. It is usually presented to us in the form of 12 to 24 random words that look like this:

  <pre class="seed">list initial manual mad escape episode excess inform evil ancient hungry toward rabbit unique stuff</pre>
</div>

## The hard and fast rule

Simplified, the basic rule of thumb is:

- Don't trust anyone to keep your secrets
- Don't trust any company to keep your secrets
- Don't trust any hardware to produce a fair random number
- Don't trust any software to limit its use of hardware

When creating a Bitcoin secret, we need to think about 2 factors:

- How unique is my secret?
- How secret is my secret?

### To produce a fair secret, we need to use a fair random source.

When using a computer, we can't really know _how_ it produces randomness unless we build it ourselves. Without getting into the complexities, there are many ways that either the software, or the hardware, could compromise the uniqueness and unpredictability of a generated secret.

Using a coin or some dice and rolling your own randomness is fair; even when the dice are biased, enough rolls will produce more randomness than is predictable.


### To keep a secret, we need radio silence

It is quite difficult to find a computer without wifi and bluetooth these days, and yet in order to finalize our secrets and in order to sign transactions, we need them.

We call these operations "sensitive operations" as we are entrusting the computer to not broadcast our activity out using this hardware while we do these operations.

Using linux based privacy focused software is a good option for non-tech savvy individuals; [TailsOS](https://tails.boum.org/) is considered the defacto standard for those who need to complete sensitive tasks on a computer.

For the more advanced users, a cheap option is the Raspberry Pi Nano. This tiny device comes in at about £5!

The Nano has no wifi or bluetooth to abuse; it does require time to learn, but it can be fun and educational too.

## Don't trust

Let's lay down the hammer here. This section describes what not to do. The goal here is to provide a sense of what dangers to look out for, and what to consider when carefully considering how to handle anything Bitcoin related.

### Don't trust the exchange
It might seem obvious, Bitcoiners are constantly declaring that storing bitcoin on exchanges are not secure.

Exchanges holding onto your bitcoin might sound like a simpler solution, but exchanges are honey pots for attackers, they are subject to the same risks as individuals, and yet they optimise for convenience and use identity based security systems that are subject to fraud.

Worse still, there are no guarantees that they can protect your bitcoin, that they will take responsibility if your account is ever compromised, or that they will release it to you if they go insolvent. Their risks are your risks, yet you have no control over their security setups.

### Don't trust your computer

Using computers (including your iPhone!) can be pretty convenient for many things, but when dealing with our hard earned money and personal security, these devices are too easy to compromise, and we should avoid them for as much as possible anyway.

- Brand new computers and devices can come pre-installed with sneaky spyware and bloatware which can hint about where and how we might keep our digital secrets to the world wide web.
- Personal devices are constantly being targeted by attackers online who find ways to intercept our online activities to get malware onto our devices, or trick us into performing actions that would compromise our devices.
- Public or even unattended personal computers can be fitted with keyloggers that track what we type in the hopes of collecting sensitive information.

Anti-virus companies would lead you to believe that their software will protect you, but they tend to give us a false sense of security while underdelivering on their promises and making your computer feel slow and sluggish. I've also noticed many non-tehcnical people fall victim to bad actors on the internet who target users by creating fake advertisements and convincing people to install their fake anti-virus software. 

Even if a computer is perfectly safe and secure right now, malware that infects your computer in the future can find and broadcast, even potentially deleted data.

![data leaks kill]({{ site.baseurl }}/assets/data-leaks-kill.webp)

Software like TailsOS can help, but there are some checks to make before using them:

1. Do a little research: An online search can be quite invaluable, look out for people warning about it being a scam.
2. Take care to download the real deal: Scammers often advertise their malware with similar names to things we want to use.
3. Follow instructions carefully: If there are instructions on how to safely download and verify the software, follow it.

### Don't trust storage devices

It might seem like a good idea to save your keys on a USB drive, but when that drive is connected to an infected computer, malware can sniff out and broadcast anything on it.

If the computer is offline while you use a USB drive, malware can still hold onto information and broadcast it later when it has access to the internet. There is also always a chance that someone might find your drive some time in the future and plug it into an infected computer and remember: once a secret is out, it's out.

Another thing to note is that electronic devices are not designed to last forever. Heat and usage can affect the reliability of a drive over long periods of time; issues that arise can vary from corrupt files, to completely unresponsive drives.

Finally, USB drives are vulnerable to ransomware attacks where your data is as good as deleted (technically encrypted). Attackers typically do this to demand payment from you with a false promise to restore that data.

### Don't trust service providers

Service providers might seem like a good idea: big companies with experts, all looking after our data; think Google Drive, Apple iCloud, Amazon Web Services, or even Microsoft services like Outlook, Office 365 and OneDrive.

These companies create pretty advanced security setups, but their solutions are designed for very complex products that require a constant battle between security, convenience, and customer satisfaction.

Bitcoin security doesn't have to be so complicated because:
- we don't need copies distributed around the world, 
- we don't need instant access to it at any time of the day,
- and we also don't need surveillance tools to detect illegal or copyrighted content to satisfy business responsibilities.

Worse still, service providers specialise in identity based security. When we create a Google account, we provide personally identifying information and this is the reason why identity theft is so lucrative. Using stolen personal information to access online services is very effective for attackers to get access to our personal and private data.

![they don't got your back]({{ site.baseurl }}/assets/they-dont-got-your-back.jpg)

### Don't trust the supply chain

If you are buying a "crypto" or Bitcoin related product, then there is likely a trail of information online with your name, address and possibly other personal information, all tied to a subject that is synonymous with wealthy individuals. It doesn't really matter if you are wealthy or not, this is enough data that if leaked or misused, could put a target on your back.

{:.note}
This is not a problem unique to Bitcoin; imagine storing gold or jewellery, you might choose to buy a safe or vault, yet the act of buying it can be an indicator for someone who is looking to steal valuables. The bigger the vault, the more someone can assume you are protecting something valuable.

When buying things like a hardware wallet, there are some basic things to consider:

- Try to buy directly from the manufacturer to reduce the number of middlemen that know who you are and what you are buying
- Try to collect physically to avoid involving delivery companies
- Avoid marketplaces like Amazon who leave their products in a warehouse allowing for potential tampering

Not only do these things protect you and your home against opportunists who might get access to your data, but they also protect you from product sabotage. Electronic products can be compromised without your knowledge, for example, check out these articles: 
- <https://www.wired.com/story/plant-spy-chips-hardware-supermicro-cheap-proof-of-concept/>
- <https://theintercept.com/2019/01/24/computer-supply-chain-attacks/>

![spy chips are deceiving]({{ site.baseurl }}/assets/spy-chips.png)

A common piece of advice you might find online, is to use "multi-sig" to create a wallet that is protected by multiple keys, each secured by a different hardware device. The idea here being that even if one of the devices were compromised, your coins would still be safe.

### Don't trust yourself

One of the biggest reasons why people avoid self custody is because they don't trust themselves. This section is here to ease your mind; you don't need to trust yourself completely because smart engineers and enthusiasts have been thinking about human error and have embedded things like checksums into the standards that we use when securing our bitcoin.

Take for example our 24 word mnemonic phrase, the last word is always the checksum. That means that it represents a number that can be used in a mathematical formula to confirm that the 23 words before it are correct. If a word were missed, mispelled, or re-arranged, the checksum would fail and guides like this one would expose that when it has you double check your work.

### The government in the room

You may not see the government as your enemy, you may believe that the government has your best interests at heart and that they are competent at protecting your global saftey and freedoms. The government is still the elephant in the room.

![the government in the room]({{ site.baseurl }}/assets/the-government-in-the-room.webp)

Private information must be kept private. Not just from the guy next door, but also from the hacker around the world. When we learn the lengths that our government goes to surveil and control individuals, it isn't hard to appear paranoid.

There are many real examples of our government system misusing power and spreading injustices in the courtroom, bailing out banks, spying on innocent citizens, and unapologetically causing or allowing harm to fall on its country. Some actions can be negligence or unintended consequences, but many are intentional atrocities; either way, we should protect ourselves from our governments negligences and its atrocities.

Some of the lesser known, but relevant government actions include embedding backdoors into security products <sup>[[1](https://www.wired.com/2015/12/researchers-solve-the-juniper-mystery-and-they-say-its-partially-the-nsas-fault/)][[2](https://www.wired.com/2013/09/nsa-backdoor/)]</sup>, and badly implemented policies like KYC.

Backdoors can compromise the way we generate our secrets, and jeopardize our security setups. Fortunately, Bitcoin does not rely on any of the suspectedly compromised algorithms.

KYC and other such policies put businesses into bad situations, requiring them to collect personal information which in turn leads to data leaks enabling identity theft, and can also lead to targeted attacks on people in their own homes.

Criminals, who the policies are designed to target, learn to work around these systems, and even use the systems to disguise their activities, meaning that the victims of these policies are mostly innocent individuals and those who are wrongly accused of crimes and disporportionately punished.

## The takeaway

As mentioned before, the purpose of the [Dont trust](#dont-trust) section was not to scare or deter you, but to give a sense of the dangers we should be considering when thinking about Bitcoin security.

I hope that this will be helpful to readers to properly consider their actions and avoid a data leak of their own as they create much simpler, yet much more effective security setups.
