---
layout: page
title: Using TailsOS
parent: Creating a deterministic wallet
nav_order: 2
---
{% include_relative intro.md %}

## Why TailsOS
You may have a different hardware wallet or you may not yet be willing to invest in a hardware wallet.

Buying a ColdCard may leave a paper trail associating your purchases, and even your delivery address, with a Bitcoin related company.

TailsOS is free, and is open source. It allows the use of a general purpose computer or laptop to work with sensitive information, but it isn't a smoking gun:

- although privacy focused, as a multi-functional operating system, it is still vulnerable to bugs and malware.
- it cannot protect against physical surveillance tools such as keyloggers or compromised hardware.
- it can be compromised by malware if exposed to compromised storage devices or the internet.

To be extra cautious, we will:
- disconnect all unnecessary accessories such as printers, extra keyboards, or charging mobile phones,
- avoid connecting to the internet, 
- avoid connecting storage devices,
- rely on physical dice to introduce randomness,
- use the computer as little as possible

## You will need
- A personal laptop or desktop computer (see [supported specs](https://tails.boum.org/doc/about/requirements/index.en.html))
  - Mac M1 processors are **not** compatible with TailsOS
- A spare 8GB+ usb storage drive 
  - ensure it has no important data on it as it will be wiped
- One or more 6 sided dice
- Scrap paper, ruler and pen

## Reference material
TailsOS is an open source operating system that runs directly from a USB stick and tries to leave no traces of your activity when you shutdown. Each time you log into TailsOS will be like a fresh installation.

- TailsOS website: <https://tails.boum.org/>
- TailsOS installation guide: <https://tails.boum.org/install/index.en.html>
- https://tails.boum.org/doc/encryption_and_privacy/virtual_keyboard/index.en.html

The two main reasons for using TailsOS is to either avoid the cost of the ColdCard, or to avoid using Bitcoin specific hardware. This guide will require some calculations to be made on paper using a worksheet. It will be useful to print or write down the following materials:

- Seed words mapped to hexadecimal numbers: <https://seedxor.com/files/wordlist.pdf>
- Seed XOR worksheet: <https://seedxor.com/files/worksheet.pdf>

## Instructions
### Creating our source of random entropy
All private keys are generated from some source of random entropy. Hardware wallets like the ColdCard come with a TRNG (true-random-number-generator) chip that claims it can provide a good source of randomness, however computers and laptops do not typically come with such hardware.

Computers and laptops use PRNG (pseudo-random-number-generator) software to make random looking numbers which can be used for simple applications and games, but is often not reliable for high security applications.

To avoid any sleight of hand from our computer, we will generate our entropy **by hand** using one or more dice.

To start, we should roll our dice to get 140 different values, writing them down as we go. Be sure to write them as you go along and choose a strategy for reading the dice in a consistent order. 

{:.note}
Rolling the dice in a small box or tupperware can help to ensure that the dice have plenty of surfaces to bounce on, reduce sliding, and prevent them from rolling away and getting lost.

Take these 140 values, and fill in the `Rolls` column of the XXX worksheet; there should be 140 blank spaces to fill.

To complete the `Outcome` column, we need to take each pair from the `Rolls` column and use the table below to map them to a 3 character outcome.

{:.table-sm}
|       | 1 | 2 | 3 | 4 | 5 | 6 |
|------:|:-:|:-:|:-:|:-:|:-:|:-:|
| **1** | 0 | 1 | 2 | 3 | 4 | 5 |
| **2** | 1 | 0 | 6 | 7 | 8 | 9 |
| **3** | 2 | 6 | A | B | C | D |
| **4** | 3 | 7 | B | A | E | F |
| **5** | 4 | 8 | C | E | C | D |
| **6** | 5 | 9 | D | F | 6 | E |


**Pay attention to the order of each pair and match the row for the first value and the column for the second.** As an example, one row might look as follows:

{:.table-sm}
|            | Rolls                  | Outcome |
|-----------:|:-------------------------:|:-----:|
| **Outcome 01** | (3,2) - (5,6) - (6,5) | 6 D 6 |

{:.note}
You may have noticed that 4 of the outcomes have a 3/36 chance of being rolled, whereas the rest have only a 2/36 chance.\
\
There **is** a small bias added by the above table which technically reduces our source of entropy from 256 bits to ~254 bits. This is still more than secure enough, but if you wish to remove this bias, you can simply treat `(5, 6)`, `(6, 5)`, `(5, 5)` and `(6, 6)` as invalid and re-roll for each invalid pair. \
\
This will mean more rolls, and more time and energy spent looking for invalid pairs; it's up to you, but it is tedious work!


### Installing TailsOS
Depending on your operating system, you may need to use different software. Use the appropriate installation guide for your computer to download and install TailsOS onto your USB Stick. You can find the appropriate gude here:

- Windows: <https://tails.boum.org/install/windows/>
- Mac: <https://tails.boum.org/install/mac/>
- Linux: <https://tails.boum.org/install/linux/>

Be sure to:

- Download the image
- Verify the download
- Download and install balenaEtcher
- Install TailsOS onto your USB stick
- Unplug all unneeded accessories such as printers and secondary mouse and keyboards
- Restart and boot into TailsOS

### Configure offline mode and log in
Once booted into TailsOS, you are presented with a welcome screen. You can change the keyboard layout, language and calendar formats if you want to; choosing the correct keyboard layout may be more necessary.

Underneath, we see **Additional Settings**; click the plus (`+`) button and choose `Offline Mode`. You should see an option called: `Disable all networking`; choose this option and click the `Add` button at the top of the window.

Finally, click the `Start Tails` button to log in.  

### Create a secure program by hand



```
           |       Rolls             | Outcome
outcome 01 | (__ __) (__ __) (__ __) | __ __ __
outcome 02 | (__ __) (__ __) (__ __) | __ __ __
outcome 03 | (__ __) (__ __) (__ __) | __ __ __
outcome 04 | (__ __) (__ __) (__ __) | __ __ __
outcome 05 | (__ __) (__ __) (__ __) | __ __ __
outcome 06 | (__ __) (__ __) (__ __) | __ __ __

outcome 07 | (__ __) (__ __) (__ __) | __ __ __
outcome 08 | (__ __) (__ __) (__ __) | __ __ __
outcome 09 | (__ __) (__ __) (__ __) | __ __ __
outcome 10 | (__ __) (__ __) (__ __) | __ __ __
outcome 11 | (__ __) (__ __) (__ __) | __ __ __
outcome 12 | (__ __) (__ __) (__ __) | __ __ __

outcome 13 | (__ __) (__ __) (__ __) | __ __ __
outcome 14 | (__ __) (__ __) (__ __) | __ __ __
outcome 15 | (__ __) (__ __) (__ __) | __ __ __
outcome 16 | (__ __) (__ __) (__ __) | __ __ __
outcome 17 | (__ __) (__ __) (__ __) | __ __ __
outcome 18 | (__ __) (__ __) (__ __) | __ __ __

outcome 19 | (__ __) (__ __) (__ __) | __ __ __
outcome 20 | (__ __) (__ __) (__ __) | __ __ __
outcome 21 | (__ __) (__ __) (__ __) | __ __ __
outcome 22 | (__ __) (__ __) (__ __) | __ __ __
outcome 23 | (__ __) (__ __) (__ __) | __ __ __

tail:      | (__ __)                 | __


__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________
__ __ __ | ________________

```

```console
amnesia@amnesia:~$ python3 code.min.py Ed8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6d8 6
your seed XOR words are:
----------
6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 6D8 626
----------
```

## Recap