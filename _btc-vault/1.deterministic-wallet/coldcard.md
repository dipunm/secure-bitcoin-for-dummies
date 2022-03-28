---
layout: page
title: Using the ColdCard
parent: Creating a deterministic wallet
nav_order: 1
---
# Creating a deterministic wallet

{:.note}
A deterministic wallet, is simply a set of private keys and their addresses derived from a single master key. The master key is often displayed as a 12 of 24 word mnemonic code and a computing device is required to reveal and control all the bitcoin within the derived addresses.

## You will need
- A ColdCard (MK3 or later)
- One or more 6 sided dice
- Scrap paper and pen

The scrap paper will be used to store sensitive information as we set up our vault. Be sure to handle with care, and **do not use a digital device**. We will need to destroy the information leaving no trace once we are complete to properly secure our vault.

## Reference material
This section will lean heavily on the setup documentation from the official ColdCard website. The site provides a few similar guides which I will link here for convenience:

- The ultra-quick guide: <https://coldcard.com/docs/ultra-quick>
- The official quick guide: <https://coldcard.com/docs/quick>
- The middle-ground guide: <https://coldcard.com/docs/middle-ground>
- The paranoid guide: <https://coldcard.com/docs/paranoid>

Have a skim of them, you can even take the time to familiarise yourself with the ColdCard’s features before beginning, however keep in mind that we will be creating a brand new empty wallet in this guide, so avoid sending any money to the device just yet.

## Instructions

Using any of the guides above, check the device for tampering, ensure it is genuine. If you are following the paranoid guide, you should update the firmware. Finally, set up and record your access pin and anti-phishing words on a piece of scrap paper.

{:.note}
Do not use a scrapbook or notepad as an alternative to a blank sheet of paper and write on a hard surface that will not leave an imprint of what you are writing. We will be destroying the scrap paper at the end of this guide.

This guide recommends reading the middle-ground and/or the paranoid guide before setting up your seed words. To set up our seed words, select `New Wallet`. Once we are presented with 24 words, press the (`4`) key to add dice rolls and enter at least 10 dice rolls before pressing the OK (`✔`) button.

Once complete, the ColdCard will present you 24 words and ask you to write them down. Write this onto your scrap paper and underline the last word (we will refer to this last word later in this guide).

The device will then ask you to prove that you wrote the words down by having you re-confirm the words in a random order. Once you have completed the test, you will have a new empty wallet.

{:.note}
We do not recommend setting up a passphrase for a vault. The passphrase would become a secret that must be shared between each of our access points and will complicate our set up unnecessarily.

Your coldcard now has an identity fingerprint. This is a short code that can be used for comparison when restoring your wallet later, to confirm that you have restored it correctly. You can find this fingerprint by navigating the menus: `Advanced` > `View Identity`. Write down this fingerprint code as it will be useful later on in this guide.

The final step is to reset and restore our wallet. We haven't sent any bitcoin to our wallet yet, so this is the perfect opportunity to familiarise ourselves with the process. To reset the device, use the navigate the menu: `Danger Zone` > `Seed Functions` > `Destroy Seed`. You will need to read and follow any instructions or warnings presented.

To restore our wallet, we navigate: `Import Existing` > `24 words` and enter our 24 words. To confirm that everything went correctly, visit: `Advanced` > `View Identity` and verify that the fingerprint is the same.

## To recap

1. Check the device for tampering
2. Update the firmware (optional)
3. Setup our access pin
4. Record our pin and anti-phishing words on scrap paper
5. Select `New Wallet`
6. Press 4 and add at least 10 dice rolls
7. Write down the 24 word mnemonic onto scrap paper
8. Underline the last word
9. Complete the verification test
10. Select `Advanced` > `View Identity`
11. Write your fingerprint onto scrap paper
12. Reset the device: `Danger Zone` > `Seed Functions` > `Destroy Seed`
13. Restore your device: `Import Existing` > `24 words`