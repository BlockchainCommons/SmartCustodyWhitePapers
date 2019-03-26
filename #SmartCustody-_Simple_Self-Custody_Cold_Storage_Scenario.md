# #SmartCustody: Simple Self-Custody Cold Storage Scenario

**Best Practices for Protecting Your Personal Digital Assets Using Cold Storage**

#### _Part of the [#SmartCustody](https://www.SmartCustody.com) project of the [Blockchain Commons](https://www.blockchaincommons.com/)_

**_Version: 2019-03-25 Release 1.0.0_**

### Disclaimer

_The information below is intended to inform a set of best practices. It may not address risks specific to your situation, and if it does not, you should modify appropriately. While this information may inform best practices, there is no guarantee that following this advice will sufficiently ensure the security of your digital assets. In addition, this information is only a window on best practices at a specific moment in time. Be aware that the Bitcoin & blockchain ecosystems may have evolved and the risk assessments of specific products may have changed since the publication of this draft. In other words: be cautious, be careful, and be aware of the current Bitcoin & blockchain landscape before you use this information._

### Copyright & Contributing

Unless otherwise noted, the contents of this white paper are Copyright ©2017-2019 by Blockchain Commons and are licensed CC-BY-SA. ![https://creativecommons.org/licenses/by-sa/4.0/](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)

Please give attribution by linking to the https://www.SmartCustody.com website.

Any questions or issues concerning this white paper or contributions of updates via pull requests can be made via our Github repository at https://github.com/BlockchainCommons/SmartCustodyWhitePapers.

### Credits

**Lead Authors:** Christopher Allen [@ChristopherA](https://twitter.com/ChristopherA), Shannon Appelcline [@Appelcline](https://twitter.com/Appelcline)

**Contributors:** Bryan Bishop [@kanzure](https://twitter.com/kanzure)

**Reviewers:** Adam Shostack [@adamshostack](https://twitter.com/adamshostack), Angus Champion de Crespigny [@anguschampion](https://twitter.com/AngusChampion), Glenn Willen [@gwillen](https://twitter.com/gwillen), Greg Maxwell, Jonathan Wilkins, Nicolas Bacca [@LedgerHQ](https://twitter.com/LedgerHQ), Pamela Morgan [@pamelawjd](https://twitter.com/pamelawjd), Tuur Deemester [@TuurDemeester](https://twitter.com/TuurDemeester)

**Sponsors:** [Adamant Capital](https://www.adamantcapitalfund.com/), [Blockstream](https://blockstream.com/), [Cryptoasset Inheritance Planning](https://t.co/hsLxiZdQya) by Pamela Morgan, [Digital Contract Design](https://contract.design),  [CryptoTag](https://cryptotag.io/), [Ledger](https://www.ledger.com/), and [Winstead](https://www.winstead.com/Practices/Corporate-SecuritiesMA/Fintech-Cryptocurrencies-Emerging-Technologies)

## PREFACE

### What is #SmartCustody?

> _**"The use of advanced cryptographic tools to improve the care, maintenance, control, and protection of digital assets."**_
>

Our goals:

* To raise the bar on best practices for digital-asset custodianship by building a greater understanding of different custody use cases, risk models, and adversary threats.
* To prepare for new custody technologies that break old models for custodianship.

To accomplish these goals, we are creating a series of best-practices white papers and also offering a series of different workshops on these topics. We are additionally collaborating with cryptographic industry and regulatory stakeholders to establish standards, improve best practices, and create new cryptographic key-management and custody technologies.

This is the first of our [#SmartCustody](https://www.SmartCustody.com) best-practices white papers. To be informed of the release of future best-practices and other educational white papers and to learn about future workshops, subscribe to our email newsletter at https://tinyletter.com/SmartCustody.

### The #SmartCustody Team

[#SmartCustody](https://www.SmartCustody.com) is a project of [Blockchain Commons](https://www.BlockchainCommons.com), which supports blockchain infrastructure, internet security, and cryptographic research.

The leads for these [#SmartCustody](https://www.SmartCustody.com) efforts are Christopher Allen ([@ChristopherA](https://twitter.com/ChristopherA)), Shannon Appelcline ([@Appelcline](https://twitter.com/Appelcline)), and Bryan Bishop ([@Kanzure](https://twitter.com/kanzure)). For more information see [Author Bios](#author-bios) at end of this white paper.

The procedures and contents of this white paper have been comprehensively peer-reviewed by a number of experts in the digital-asset ecosystem, including contributors to open-source project like Bitcoin Core and [The Glacier Project](https://glacierprotocol.org/), employees of blockchain technology companies like Blockstream, Ledger, and Tokensoft, and attorneys from a variety of disciplines. We expect to iterate these procedures and update this document regularly as new digital asset technologies and best practices become mature.

## INTRODUCTION

Digital assets are only as safe as the procedures of their custodian. Many digital-asset holders don't practice minimal safety, and this could result in the loss of all of their Bitcoins, Ether, other digital currencies as well as non-fungible digital assets. The following procedures detail simple and practical setups that can be used as the foundation of safer digital-asset management. The base scenario requires just a few hours setup and then a semi-annual check to make sure everything remains secure.

### About The Base Scenario

The base scenario presumes the following audience:

* A holder with a significant amount of digital assets (>5% of net worth);
    * with full and legal custody of the assets and no fiduciary responsibility to others;
    * and 100% of those assets shared with a spouse, if present, in estate planning.
* A holder who largely holds investments long term, and is not actively trading them.
* A holder who lives in the first world, and thus is less concerned about issues like government attack, kidnapping, or privacy violations.
* A holder who has sufficient computer skills to comfortably install and run apps.

This scenario suggests that a comprehensive cold-storage procedure would be the best practice to maintain and protect this holder's digital assets. Though simple, this scenario is also a foundation for more complex custodial procedures. It introduces many of the basic approaches for managing digital assets, explains their importance, and presents the adversaries that could steal or ruin the holder's digital assets.

This scenario advocates the basic procedure to address nine major types of adversaries, while the optional procedures can help protect against five further adversaries. Additional categories of "Non-Theft Crimes", "Loss by Government" and "Privacy-Related" adversaries are not strongly considered in this scenario. See [Appendix III: A Brief Overview of Digital-Asset Adversaries](#appendix-iii-a-brief-overview-of-digital-asset-adversaries).

For simplicity, this document focuses on Bitcoin, but is easily adaptable to other digital assets supported by our suggested hardware wallet.

If you don't meet the description of the holder for this scenario, it will still be useful, but you will have to adapt it for you specific needs. If you are unsure as to whether you should use a cold-storage scenario, please see [Appendix I: Why Cold Storage?](#appendix-i-why-cold-storage).

## PROCEDURES

The following procedure will help ensure the safety of a simple self-custody cold-storage scenario for managing digital assets. It is important that you initiate it when you have a large block of time: usually at least two hours when you will not be interrupted and when you will not be distracted. You don't want to make mistakes, and to avoid that it's best to do everything in one go.

### Be Careful!

**_General rule: Don't rush and don't take cold storage lightly!_**

If you make a mistake you could lose your bitcoin today, or you could expose secret data that would allow an attacker to steal your funds months or years into the future.

Here are some of the more tedious steps, and why they're important:

* **_Verify Your Recovery Phrase (D)._** Double-checking your recovery phrase ensures that you can rebuild access to your digital currency if you ever lose your hardware wallet(s). By doing it after a small test transaction, you're minimizing your potential loss. **_15 minutes, but tedious._**
* **_Setup Fireproof Key Recovery Phrase (F)._** Embedding your recovery phrase in steel or titanium strongly protects you against [Disaster](#disaster), and also gives you a backup for your hardware wallet and paper recovery phrase. However, it takes a long time to stamp 96 letters. **_1 hour._** Be sure to also repeat step D for the phrase you saved in your metal-device. **_15 minutes, and still tedious._** If you choose the "Cryptosteel" alternative, that will be equally long.

Don't skimp on any of these phases just because they take a while; don't figure that you'll get back to them later. The goal is to ensure that you protect your digital investments from problems _before_ you make any real investments.

### Adversaries

This process in this basic scenario has been optimized to avoid risks from nine adversaries listed below — simplified by not addressing the risks of all possible adversaries (over 25+). In particular, these adversaries were the ones selected as most likely to impact a self-custodian in the first world. Adversaries related to "Non-Theft Crimes", "Loss by Government" and "Privacy-Related" are not strongly considered in this scenario.

Some additional processes for this scenario are offered as options—but be careful to avoid [Process Fatigue](#process-fatigue).

1. [Key Fragility](#key-fragility) — _an accidental key loss_
2. [Transaction Error](#transaction-error) — _incorrect transaction details leading to loss_
3. [User Error](#user-error) — _an operator mistake leading to loss_
4. [System Network Attack](#network-attack-systemic) — _a server online attack_
5. [Death / Incapacitation](#death--incapacitation) — _a mortal loss or disability that could endanger funds_
6. [Disaster](#disaster) — _a sudden, large-scale destructive event_
7. [Personal Network Attack](#personal-network-attack) — _a personal online attack_
8. [Denial of Access](#denial-of-access) — _physical denial that prevents use of funds_
9. [Process Fatigue](#process-fatigue) — _errors caused by the complexity of the overall procedure_
10. [Physical Theft, Casual](#physical-theft-casual) — _an opportunistic physical theft_


The most notable of these adversaries may be "Systemic Network Attack", an adversary that is very problematic in hot-wallet scenarios, but largely nullified by removing private keys into cold storage. In many ways, it's the prime adversary overcome by this scenario.

See [Appendix III: A Brief Overview of Digital-Asset Adversaries](#appendix-iii-a-brief-overview-of-digital-asset-adversaries) for a brief overview of the adversaries covered in this document, and [Adversaries — Case Studies for Securing Digital Assets Against Loss]() _(available late Spring 2019)_ for a more extensive list and discussion.

### Requirements

The following items are necessary for this procedure, and should be purchased in advance of your setting up this scenario.[^1].

* ❑ Small Home Safe (For example: https://www.amazon.com/AmazonBasics-Security-Safe-0-5-Cubic-Feet/dp/B00UG9HB1Q/ )

* ❑ Safety Deposit Box at Bank or other institution

* ❑ Existing Laptop or Desktop Computer capable of running [Ledger Live](https://www.ledger.com/pages/ledger-live)[^2], preferably able to boot from a USB drive

* ❑ 1 Fine-point Permanent Marker (Sharpie https://www.amazon.com/Sharpie-Plastic-Point-Resistant-1742663/ or equivalent)

* ❑ 1 Package Waterproof Laser Paper (TerraSlate, made of 1-PET https://www.amazon.com/TerraSlate-Paper-Waterproof-Printer-Sheets/dp/B00NWVGOF4 or Rite in the Rain All-Weather Copier Paper, made of coated recyclable wood https://www.amazon.com/Rite-Rain-All-Weather-Copier-8511/dp/B0016H1RYE/ or equivalent)

* ❑ 2 Ledger Nano S[^3], Factory sealed, not used https://www.ledgerwallet.com/products/ledger-nano-s or https://www.amazon.com/gp/product/B01J66NF46

* ❑ One CryptoTag[^4] https://cryptotag.io/products/cryptotag-starter-kit/

* ❑ 2 USB cables appropriate for connecting your computer's USB ports to the Ledger (offered as set at https://www.ledgerwallet.com/products/ledger-otg-kit

  _**Optional Steps** (described later) may require  purchases of additional items._

### Final State

This procedure will secure your Bitcoin private keys by keeping the more sensitive information in a safety deposit box and the less sensitive information in a home safe, as follows:

| Home Safe | Safe Deposit Box |
| :--- | :--- |
| Ledger Device #1 | Ledger Device #2 |
|  | Ledger PIN |
|  | Paper 24-word seed |
|  | CryptoTag 24-word seed |
| Instructions for heirs and xpub and cold storage addresses | Duplicates of instructions for heirs and xpub and cold storage addresses |

### The Basic Procedure

#### **A. Setup Safes**

1. ❑ Install Home Safe[^5]

    1. Ideally it should be physically secured by mounting it to floor or wall joists, or even more securely, directly to a foundation.
2. ❑ Order Safe Deposit Box[^6]

      2. Recommendations:
        1. Associate it with a joint bank account with at least one of your heirs.
        2. Have sufficient funds in the joint bank account for several years of bank fees and box fees.
        3. Have the safety deposit box be in both person's names.[^7]

#### **B. Setup Computer** [^8]
1. *This optional action is omitted in this basic procedure. Enable it with "Use a USB Drive" if you are concerned about [Bitrot](#bitrot) or [Personal Network Attack](#personal-network-attack).*
2. _This optional action is omitted in this basic procedure._
3. _This optional action is omitted in this basic procedure._
4. ❑ Install Ledger Live for Mac, Windows or Linux https://support.ledger.com/hc/en-us/articles/360006395553
    1. Download It
    2. Install It

#### **C. Create Master HD Seed on Ledger**[^9][^10]
1. ❑ Start Up Ledger Live
    1. If necessary, verify for your operating system that you want to run this downloaded app
    2. **On Ledger Live (LL:)** Click "Get started"
2. ❑ Upgrade Ledger (if Needed)
    1. Plug Ledger into computer holding down the right button (furthest from the plug).
    2. Watch for the screen to say "Recovery"; hit both buttons, then hit them again, so that "Settings" pops up on the Ledger.
    3. **LL:** Click "Manager"
    4. **LL:** Click "Use an Initialized Device"; choose your Ledger type and hit "Continue".
    5. **LL:** Just click "Yes" on the Security Checklist questions; they're not actually relevant currently.
    6. **LL:** Click "Check Now" on the Ledger Genuine Check.
        1. If it stalls out, it's probably because you didn't hit both buttons to get your Ledger to the App screen, which should say "Settings".
        2. On your Ledger, right-click to "Allow Ledger Manager" when requested.
        3. When it's done, hit "Continue".
    7. **LL:** Choose a password for your Ledger Live software on your computer.
    8. **LL:** Turn off Analytics and Bug Reports on the Bugs and analytics page, to minimize any potential attack surface.
    9. **LL:** Click "Open Ledger Live", then "Got It", then "Open Manager"
    10. At last, you're ready to check the firmware version on your Ledger!
    11. **LL:** If your Ledger does not have the most up-to-date firmware (currently 1.5.5), hit the "Update" button to the right.
        1. Follow the instructions you see on screen.
        2. Make sure to verify that the identifier matches between your screen and your Ledger, to ensure the security of this update.
        3. You may also need to update the MCU. If so, Ledger Live will alert you. You'll need to disconnect the Ledger, then plug it back in while holding the left button this time.
        4. You will usually see that the Bootloader is updating, then the MCU, then the Firmware. (Whew!)
    12. Disconnect your Ledger from your computer; exit Ledger Live.
3. ❑ Initialize Your Ledger
    1. Restart Ledger Live; enter your password; and plug your Ledger back into your computer.
    2. Click both buttons on your Ledger when it says "Welcome"; this is generally how you clear a screen.
    3. Click both buttons again.
    4. You should now see "Configure as new device" with an "X" to the left and a "√" on the right. This means that you hit the left button to choose "No" ("X") and the right button to choose "Yes" ("√"). Click the right button.
4. ❑ Create Your PIN
    1. Hit both buttons on your Ledger to create a PIN
    2. Create at least a 6-to-8 digit PIN
    3. If you desire PIN compatibility with Trezor, don't use the number "0".
    4. Hit both buttons to verify your PIN
    5. ❑ Write the PIN and the Date that the key was generated using permanent marker on waterproof paper page
5. ❑ View Recovery Phrase
    1. Hit both buttons on your Ledger to view your 24-word Recovery Phrase
    2. Afterward, you can hit the right button to go to the next word
6. ❑ Write down Recovery Phrase, adding it to the waterproof paper page
    1. Write it in 6 rows, with 4 words in each row
    2. Beware of homonyms or similar words
    3. Leave some room at the bottom of the page for notes
    4. Afterward, go back through all 24 words, and look at each character in the words to make sure you got them right
    5. Hit both buttons to exit the word list, then hit both buttons to verify your Recovery Phrase
    6. You'll need to verify all 24 words; expect this to take some time.
    7. You should see "Your device is now ready".
7. ❑ Install Bitcoin on your Ledger[^11]
    1. **LL:** Choose the "Manager" in Ledger Live
    2. Hit the right button on your Ledger to Give Permissions
    3. **LL:** Install Bitcoin
    4. **LL:** Hit "Close"
    5. **LL:** Repeat for any other cryptocurrency you want to use
8. ❑ Create Your Bitcoin Account
    1. **LL:** Click the "+" next to Accounts to Add Accounts
    2. **LL:** Choose Bitcoin and hit "Continue"
    3. On your Ledger, hit the right button to navigate to the Bitcoin app, then both buttons to run it
    4. Click the right button to allow your Ledger Live wallet to access your Ledger
    5. **LL:** Hit "Continue" in Ledger Live
    6. **LL:** Name the account (e.g. "Investment Cold Storage"), select the checkmark, and hit "Add Account"
    7. Hit the "X" button; you're done: you now have an account to send and receive bitcoins; discount the Ledger
9. ❑ Write the date the key was generated, the Ledger firmware version number, and the Bitcoin app version number on waterproof paper.[^12]

#### **D. Verify Recovery Phrase**

1. ❑ Restart Ledger Live, plug in your Ledger Nano, and login to both.
2. ❑ **LL:** Click "Manager", and find "Recovery Check" in the List of Apps. "Install".
3. ❑ Navigate to "Recovery Check" on your Ledger. Hit both buttons to enter it.
4. ❑ Select both buttons on your Ledger to begin the check. Hit both buttons twice more.
5. ❑ Select 24 words with both buttons, then hit both buttons again.
6. ❑ Enter your 24 words, selecting letters one at a time.
    1. The Ledger will only list possible letters.
    2. The Ledger will provide you with complete word possibilities after you enter two to four letters from each word.
    3. When offered word options, hit the right arrow until you get to the correct word.
    4. Select the right word with both buttons, then hit both buttons again to go on to the next word.
7. ❑ If you see "Recovery Phrase Matches", you have verified your phrase!
    1. If you didn't, check for simple mistakes. If you see them, repeat step D.
    2. Otherwise, restart from step C-3.

#### **E. Create Test Transaction**[^13]
1. ❑ Generate a test receive address
    1. **LL:** Select the "Receive" Menu item on Ledger Live
    2. If necessary navigate to the Bitcoin app on your Ledger and open it
    3. **LL:** Click "Confirm" and you'll see a receipt address on your computer screen with a QR code.
    4. You will also see the address on your Ledger; carefully compare all the digits and if it is the same, hit the right button to confirm
    5. Write down, copy, or scan the Bitcoin address
    6. If you write it by hand, double check the address: read it aloud as you look at both the original and your copy.
2. ❑ Send yourself a small Bitcoin transaction to that address. Wait for confirmation.
    1. If you instead request a transaction from someone, best practice is to send them the address via two secure communications methods that are out of band with each other (or else: show them a QR code in person).
    2. After sufficient time has elapsed, you should see the transaction in your Bitcoin account on Ledger Live
3. ❑ OPTIONAL: Use the "Send" menu item in Ledger Live to send some (but not all) of your test funds back to a different Bitcoin wallet. This confirms that your wallet can not only receive bitcoins, but spend them too[^14]. Again, wait for confirmation.
4. ❑ Export account info from Ledger Wallet Bitcoin
    1. Select your account (e.g. "Investment Cold Storage")
    2. Click "Edit Account" (the wrench) on the right
    3. Click "Advanced Logs"
    4. Write, copy, or print the xpub and the address path, along with the account name
    5. ❑ OPTIONAL: Write the name of the account, the xpub, and the root path on your waterproof sheet
    6. Repeat for additional accounts.
5. ❑ Once you've confirmed receipt of your transaction, and possibly spent part of it, disconnect the Ledger

#### **F. Setup Fireproof Key Recovery Phrase**[^15]
1. Set up your CryptoTag
    1. ❑ Stamp the the first four letters of each word in your Recovery Phrase into your CryptoTag.
        1. Place the Bit Holder over each row before you begin stamping that word.
        2. Carefully check each letter before you stamp it, to be sure you haven't grabbed a look-alike letter. Watch for "O" and "Q" in particular, because they look the same and are near to each other.
        3. Be sure the word "CryptoTag" is facing you, so that the letter will be face-up.
        4. Stamp forcefully to ensure that the stamped letter is distinct and easy to read. You may find that two blows are necessary to get it sharp and distinct; if so, be sure not to move the stamp in between.
        5. Consider taking a break after stamping the first 12 words, to keep your stamps strong and deep.
        6. The first four letters of each word are sufficient to distinctly identify each word.
        7. If you make a mistake during this process which renders the tag unusable (missing or wrong words, wrong order, etc) consider starting over with a new seed; it is difficult to adequately destroy a partially created CryptoTag.
    2. ❑ After completing all 24 words, reclip the CryptoTag.
    3. See: https://cryptotag.io/tutorial/ for a video tutorial.

#### **G. Verify Recovery Phrase & Software Standards Conformance**

1. ❑ Use same PIN and restore Recovery Phrase on second Ledger.
    1. Use the Recovery Phrase from your Cryptosteel, to verify its accuracy.
2. ❑ Connect the Ledger to your computer and run Ledger Live. Verify that the test transaction is listed and confirmed.

#### **H. Transfer Existing Cold Funds**

1. ❑ Generate new receive addresses and transfer existing cold funds to the new master seed protected by the Ledger. Wait for confirmation.
    1. Have an appropriate amount of paranoia for the amount of funds you're transferring and your own peace of mind.
    2. Never put enough into a single transaction that it would be catastrophic to lose.
    3. Perhaps start transferring small amounts, increasing over the course of several transactions.
    4. Be sure to see actual confirmations from each transfer before transfering again.

#### **I. Print Next Cold Storage Address**

1. ❑ **LL:** Open Ledger Live and enter password, click "Receive", and hit "Continue" once the right account has been selected.
2. ❑ Plug in your Ledger, enter the PIN, navigate to the Bitcoin app, and hit both buttons to sellect it.
3. ❑ **LL:** Hit "Verify" and double-check the address on your screen against the one on your Leder.
4. ❑ Write on a separate waterproof sheet the new Receive Address.
    1. After you write it, carefully double- and triple-check it.
    2. Look not just for mistakes, but also where your printing might be ambiguous.
    3. If you prefer, scan the QR code.

#### **K. Duplicate USB drive**

_This optional step is omitted in this basic procedure. Enable it with "Use a Second USB Drive" if you are concerned about [Bitrot](#bitrot) or [Key Fragility](#key-fragility). You must also have enabled "Use a USB Drive" previously._

#### **L. Prepare Instructions for Heirs and/or Executor**

1. ❑ Print instructions for Heirs and/or Executor on waterproof paper, with information on bitcoin exchange accounts, spare hot wallets, and other digital assets. See example letter below.

#### **M. Store in Safes**[^16]
1. ❑ Sign the plastic case of your Ledgers with a permanent marker, or use an engraving tool to sign it.[^17]
2. ❑ OPTIONAL: Store materials in tamper-resistant bag and sign it;
❑ OPTIONAL: Store materials in fire resistant bag.
3. ❑ Place encrypted key-related devices and non-key devices in your Home Safe, including one Ledger, the your instructions for heirs, and one copy of the xpub and cold storage addresses. The safe should NOT have a copy of any unencrypted recovery phrases or the PIN.
4. ❑ Place unencrypted key-related materials in the safety deposit box, including the CryptoTag and the paper Recovery Phrase and PIN. Also store duplicates: the second Ledger, the second copy of instructions, and one copy of the xpub and cold storage addresses.

#### **N. Check Storage A (Spring)**[^18][^19]
1. ❑ Confirm contents of Home Safe.
2. ❑ OPTIONAL: If using any tamper-evident bags, check for tampering.
3. ❑ Check to see if there have been any exploits against the Ledger hardware, the Ledger firmware, Ledger Live, or your OS. If there are, you may need to recreate your OS drive from scratch before connecting it to the Ledger.
4. _This optional action is omitted in this basic procedure. Enable it with "Use a USB Drive" if you are concerned about [Bitrot](#bitrot) or [Personal Network Attack](#personal-network-attack)**_.
5. ❑ Connect your Ledger, open Ledger Live, and confirm balances.
6. ❑ OPTIONAL: Save any transaction logs on waterproof paper and store in Home Safe.
7. ❑ OPTIONAL: If you have used your cold storage address, print new set.

#### **O. Check Storage B (Fall)**[^20][^21]
1. ❑ Sign in to check contents of safety deposit box. Check safety deposit box signature logs to see if anyone else has signed in.
2. ❑ OPTIONAL: If using any tamper-evident bags, check for tampering.
3. ❑ Check to see if there have been any exploits against the Ledger hardware, the Ledger firmware, Ledger Live, or your OS. If there are, you may need to recreate your OS drive from scratch before connecting it to the Ledger.
4. ❑ OPTIONAL: If you have an extra USB drive in the safety deposit box, take it home and boot from USB drive. Do only essential security updates; open Ledger Wallet and confirm balances.
5. ❑ OPTIONAL: Save any transaction logs on waterproof paper and store in safety deposit box.
6. ❑ OPTIONAL: If you have used your cold storage address, print new set.

## OPTIONAL STEPS

**Created Adversary:** [Process Fatigue](#process-fatigue)

_The following optional steps can be added to this procedure to improve its robustness and its security._

_Each optional step addresses certain adversaries, but adding them ultimately adds to the [Process Fatigue](#process-fatigue) of the entire procedure, so care should be taken to ensure that new steps are both important and understood._

**_Optional Steps:_**

* Erase Your Ledger(s)  — for [Physical Theft, Casual](#physical-theft-casual), [Physical Theft, Sophisticated](#physical-theft-sophisticated)
* Hire a Lawyer — for [Death / Incapacitation](#death--incapacitation), [Denial of Access](#denial-of-access), [Institutional Theft](#institutional-theft)
* Seal Metal Tiles — for [Institutional Theft](#institutional-theft), [Internal Theft](#internal-theft)
* Use Bags (Fire-Resistant) — for [Disaster](#disaster)
* Use Bags (Tamper-Evident) — for [Institutional Theft](#institutional-theft), Internal Theft, [Physical Theft, Sophisticated](#physical-theft-sophisticated)
* Use a (USB) Laser Printer — for [Key Fragility](#key-fragility), [Transaction Error](#transaction-error), [User Error](#user-error)
* Use Metal Alternative (Cryptosteel) — alternative for [Disaster](#disaster), [Key Fragility](#key-fragility)
* Use Metal Alternative (Steel Tile & Engraver) — alternative for [Disaster](#disaster), [Key Fragility](#key-fragility)
* Use Metal Enhancement (Redundant Metal Devices) — for [Denial of Access](#denial-of-access), [Disaster](#disaster), [Institutional Theft](#institutional-theft), [Key Fragility](#key-fragility)
* Use a USB Drive — for [Bitrot](#bitrot), [Personal Network Attack](#personal-network-attack)
* Use a (Second) USB Drive — for [Bitrot](#bitrot), [Disaster](#disaster)

See [Securing Digital Assets: Adversaries]() (available late spring 2019) for a full discussion of adversaries. The following adversaries appear for the first time in this section:

11. [Bitrot](#bitrot) — _a hardware, software, or media failure leading to loss_
12. [Institutional Theft](#institutional-theft) — _a theft by a trusted institution or its employee_
13. [Internal Theft](#internal-theft) — _a theft by a trusted person such as an heir or executor_
14. [Physical Theft, Sophisticated](#physical-theft-sophisticated) — _a purposeful physical theft of private keys_

### ❑ Optional Step: Erase Your Ledger(s)

**Obstructed Adversary:** [Physical Theft, Casual](#physical-theft-casual), [Physical Theft, Sophisticated](#physical-theft-sophisticated)

**Created Adversary:** [Disaster](#disaster), [Key Fragility](#key-fragility), [User Error](#user-error)

**Suggested Complements:** Use Redundant Metal Tiles

_A Ledger is a risk for digital-asset management, not just because it's an additional avenue through which the private keys can be accessed, but also because it's a signal flag shouting that the owner has Bitcoins. By erasing a Ledger after its initial setup, issues of **"Loss by Crime / Theft"** can thus be reduced. For this optional step, the xpub information is usually excluded too, with the theory being that the Ledger and its information can be restored from the keys and used whenever it's needed._

_The problem, of course, is making sure that the keys aren't lost; reducing the number of places that a key is stored increases the problem of [Key Fragility](#key-fragility) and may also make a procedure more prone to [Disaster](#disaster). So, this step should only be taken by someone who is **very, very** comfortable with the rest of this scenario, and who has also taken additional steps to backup their keys._

_The **Redundant Metal Tiles** enhancement step is a particularly good complement to this one because it ensures private keys are still redundantly stored, but maintains the same high level of protection introduced through this option by scattering the keys across multiple locations._

**_Replace step "M" of your procedure as follows, to erase your Ledger before storage:_**

#### **M. Store in Safes**

1. ❑ Erase each of your Ledgers by entering an incorrect PIN three times to clear the master key from device. You will see "Your device has been reset."
    1. Place your Ledgers wherever you want; they no longer need to be secured.
2. ❑ OPTIONAL: Store materials tamper-resistant bag and sign it;
❑ OPTIONAL: Store in fire resistant bag.
3. ❑ Place non-key devices in your Home Safe, including your instructions for heirs, and one copy of the cold storage addresses. The safe should NOT have a copy of any unencrypted recovery phrases.
4. ❑ Place unencrypted key-related materials in the safety deposit box, including the CryptoTag and the paper Recovery Phrase and PIN. Also store duplicates: the second copy of instructions and one copy of the cold storage addresses.

**_Replace action #5 of Step "N" of your procedure as follows, to restore your Ledger as part of maintenance:_**

1. ❑ Connect your Ledger and rebuild it.
    1. Hit both buttons to move through the first two screens.
        1. Hit the **_LEFT_** button to refuse to "Configure as New Device".
        2. Hit the right button to  "Restore Configuration".
        3. Reenter the same PIN and verify, per step "C-3".
    2. ❑ Hit both buttons to "Enter your recovery phrase".
        1. Choose to restore "24" words.
        2. Enter your Recovery Phrase from the waterproof sheet.
        3. Enter letters one at a time, selecting with the left and right arrows, then choosing by hitting both buttons.
        4. The Ledger will only list possible letters.
        5. The Ledger will provide you with complete word possibilities after you enter two to four letters from each word.
        6. When offered word options, hit the right arrow until you get to the correct word.
    3. ❑ Hit both buttons when words are finished processing, then hit both buttons to open the Bitcoin app.
    4. ❑ **LL:** Open Ledger Live and confirm balances.
    5. ❑ Erase Ledger by entering an incorrect PIN three times to clear the master key from device. You will see "Your device has been reset."

**_Similarly, replace action #4 of Step "O" of your procedure as follows:_**

1. ❑ OPTIONAL: If you have an extra USB drive in the safety deposit box, take it home and boot from USB drive. Do only essential security updates. Connect your Ledger and rebuild it.
    1. Hit both buttons to move through the first two screens.
        1. Hit the **_LEFT_** button to refuse to "Configure as New Device".
        2. Hit the right button to  "Restore Configuration".
        3. Reenter the same PIN and verify, per step "C-3".
    2. ❑ Hit both buttons to "Enter your recovery phrase".
        1. Choose to restore "24" words.
        2. Enter your Recovery Phrase from the waterproof sheet.
        3. Enter letters one at a time, selecting with the left and right arrows, then choosing by hitting both buttons.
        4. The Ledger will only list possible letters.
        5. The Ledger will provide you with complete word possibilities after you enter two to four letters from each word.
        6. When offered word options, hit the right arrow until you get to the correct word.
    3. ❑ Hit both buttons when words are finished processing, then hit both buttons to open the Bitcoin app.
    4. ❑ **LL:** Open Ledger Live and confirm balances.
    5. ❑ Erase Ledger by entering an incorrect PIN three times to clear the master key from device. You will see "Your device has been reset."

### ❑ Optional Step: Hire a Lawyer

**Obstructed Adversary:** [Death / Incapacitation](#death--incapacitation), [Institutional Theft](#institutional-theft)

**Created Adversary:** [Process Fatigue](#process-fatigue), [Institutional Theft](#institutional-theft)

_A lawyer can store sealed files for you and will have a fiduciary responsibility to maintain them safely and privately[^22]. This can reduce the problem of [Institutional Theft](#institutional-theft) for those concerned about various privacy or legal issues regarding safety deposit boxes, but you obviously must ensure the lawyer is trusted. This option can also increase the odds of your heirs or family accessing your digital assets, because the lawyer will know what to do if [Death / Incapacitation](#death--incapacitation) occurs. But there is new danger of [Process Fatigue](#process-fatigue), if nothing else because a lawyer is an ongoing cost._

**_Replace the safety deposit box in action #4 of step "M" and in step "O" with a lawyer; or, alternatively supplement your safety deposit box to also include the same information with a lawyer in a sealed envelope._**

### ❑ Optional Step: Seal Metal Tiles

**Obstructed Adversary:** [Institutional Theft](#institutional-theft), [Internal Theft](#internal-theft)

**Created Adversary:** [Process Fatigue](#process-fatigue)

_Metal tiles can be dangerous because they leave cryptographic seeds in plain text. One solution for this problem is to use a sealant to place a unique opaque cover over the words, so that looking at the words would be tamper-evident (because the sealant would have to be removed). For the sealant to be truly tamper-evident, it needs to have a unique cover that you can recognize when you revisit it, so that you know no one has removed it, then recovered it. Glitter is applied over the sealant for this purpose. This can counter [Institutional Theft](#institutional-theft) and [Internal Theft](#internal-theft)._

_The deficit of sealing your plates in this way is that it'll make the plates very hard to access. That's fine for the emergency when you need to use them to recover your funds, but less so if you want to check them every once in a while, thus there is definite [Process Fatigue](#process-fatigue)._

_This process is not likely to work equally well for all sorts of metal devices. It's probably better for an ad hoc method, like using an engraver on a metal tile. It might work on CryptoTag, though it's untested. It's definitely not appropriate for something like CryptoSteel._

### **_Add the following actions to Step "F" if you are using one or more CryptoTags or metal tiles:_**

1. Seal the metal tile with a plastic coating.
2. Use a glitter polish to give the coating a unique finish.
3. Photograph the unique pattern of the glitter finish.
4. Store photograph in alternate location.

**_In Step "O", when you check your safety deposit box, you should always compare your photograph to the finish on the metal tile._**

**_Add the following to your requirements list:_**

* Plastic Sealant – https://www.amazon.com/dp/B00I9SK8XY
* Glitter Polish — https://www.amazon.com/essie-luxeffects-nail-polish-stones/dp/B007RS4R9I

### ❑ Optional Step: Use Bags (Fire-Resistant)

**Obstructed Adversary:** [Disaster](#disaster)

**Created Adversary:** [Process Fatigue](#process-fatigue)

_Fire-resistant bags can increase the fire resistance of printed materials, and thus protect against [Disaster](#disaster). If used in combination with a fireproof safe, they may add to the rated time. However, note that fire-resistant bags are not specifically designed for protecting electronics: they are intended to protect non-electronic materials. They may not add any additional protections to computers, hardware wallets, USB sticks, or other such devices, and they may not even protect InkJet-printed material. So, don't overly depend on this optional step._

**_Add the following action to step "M" of your procedure:_**

1. ❑ Store all materials in fire-resistant bags.

**_Add the following to your requirements list:_**

* 2 Fireproof Bags — 11 x 15" https://www.amazon.com/gp/product/B01NCVKZXG or 11 x 7" https://www.amazon.com/gp/product/B01KWTE9ZU

_One bag is used for your home safe, one for your safety deposit box._

### ❑ Optional Step: Use Bags (Tamper-Evident)

**Obstructed Adversary:** [Internal Theft](#internal-theft), [Institutional Theft](#institutional-theft), [Physical Theft, Sophisticated](#physical-theft-sophisticated)

**Created Adversary:** [Process Fatigue](#process-fatigue)

_Tamper-evident bags can be used to reduce [Internal Theft](#internal-theft), [Institutional Theft](#institutional-theft), and [Physical Theft, Sophisticated](#physical-theft-sophisticated) because it becomes more difficult to surreptitiously look at key material. For paper materials they slightly decrease risk of damage due to water used by firefighters, and thus may help a little in [Disaster](#disaster)._

_They can also increase [Process Fatigue](#process-fatigue) because of the need to replace the bags whenever examining the key material._

**_Add the following action to step "M" of your procedure:_**

1. ❑ Store materials in tamper-evident bag and sign it.

**_Add the following to your requirements list:_**

* 2 Opaque Tamper-Evident Deposit Bags https://www.amazon.com/MMF-Industries-2362010N06-12-Inch-Tamper-Evident/dp/B000J05F06

_One bag is used for your home safe, one for your safety deposit box._

### ❑ Optional Step: Use a (USB) Laser Printer

**Obstructed Adversary:** [Key Fragility](#key-fragility), [Transaction Error](#transaction-error), [User Error](#user-error)

_Printing information from your computer rather than hand copying it can improve [Key Fragility](#key-fragility) and can reduce [Transaction Error](#transaction-error) and [User Error](#user-error)._

**_Add the following action to step "B" of your procedure:_**

5. ❑ Install printer drivers for USB Printer

**_Instead of writing, print out your receive bitcoin addresses (I.4), the extended public key (E.7), and anything else from Ledger Live, all on waterproof laser paper._**

**_Add the following to your requirements list:_**

* USB Laser Printer (do not enable ethernet or wifi)

### ❑ Optional Step: Use Metal Alternative (Cryptosteel)

**Obstructed Adversary:** [Disaster](#disaster), [Key Fragility](#key-fragility)

**Created Adversary:** [Physical Theft, Casual](#physical-theft-casual), Disaster, or [Institutional Theft](#institutional-theft)

_Cryptosteel is primarily an alternative to CryptoTag, which means that it can similarly increase protection against [Disaster](#disaster) or [Key Fragility](#key-fragility). The advantage of using Cryptosteel is that it's the most precise of all the metal-device options: you put specific letters into the Cryptosteel case, so there's no opportunity for unreadable text. The disadvantage is that its fiddly and may not be entirely [Disaster](#disaster) resistant — it has been [reported](https://medium.com/@lopp/metal-bitcoin-seed-storage-stress-test-21f47cf8e6f5) that in one high-temperature torch test that the Cryptosteel twisted and some of the letters popped out._

_As with any unencrypted copy of your master seed, you should protect it somewhere like a safety deposit box, or you'll increase your vulnerability to [Physical Theft, Casual](#physical-theft-casual). However doing so increases the likelihood of [Institutional Theft](#institutional-theft), so be sure to assess which is more likely given your situation._

_This is one of three possible options for maintaining a copy of your Recovery Phrase using a metal-device to increase its durability and [Disaster](#disaster) resistance. CryptoTag is our default choice, as we believe it best combines fire resistance [^23] and preciseness. Of our two optional choices: Cryptosteel is more precise but more fiddly; while a Metal Tile & Engraver are cheap and simple, but can lead to precision problems with messy transcription._

**_Replace the first action in step "F" of your procedure; alternatively, add this action to step "F" if you want to use a Cryptosteel in addition to CrypoTag._**

1. Set up Cryptosteel
    1. ❑ To open your Cryptosteel, rotate the two sides counter-clockwise.
    2. ❑ To unlock one side of your Cryptosteel, rotate the screw 90 degrees counterclockwise, then push down the pawl in the inset toward the bottom right. Afterward, swing open the locking arm. Be sure you're starting with the "1"-"12" side.
    3. ❑ Set the letter tiles for the first four letters of each word in your Recovery Phrase into the CryptoSteel.
        1. Carefully check each letter as you place it, to be sure you have the right side, and you haven't grabbed a look-alike letter.
        2. The first four letters of each word are sufficient to distinctly identify each word.
        3. Some letters will slide easily, some will need to be pushed with the small screwdriver you used to open your Cryptosteel. Occasionally, you may get one that doesn't fit at all.
        4. Lock the arm when you're done, and repeat on the "13"-"24" on the other side.
    4. ❑ After completing all 24 words, on both sides, close the Cryptosteel.

**_In step "M", store the Cryptosteel in your safety deposit box._**

**_Add the following to your requirements list:_**

* Cryptosteel Master Mnemonic https://cryptosteel.com/ or https://www.amazon.com/gp/product/B0756P57M8
* Small flathead screwdriver

### ❑ Optional Step: Use Metal Alternative (Single Metal Tile & Engraver)

**Obstructed Adversary:** [Disaster](#disaster), [Key Fragility](#key-fragility)

**Created Adversary:** [Physical Theft, Casual](#physical-theft-casual) or [Institutional Theft](#institutional-theft)

_A Metal Tile with an Engraver is primarily an alternative to CryptoTag, which means that it can similarly increase protection against [Disaster](#disaster) or [Key Fragility](#key-fragility). The advantage of using a Engraved Metal Tile is that it's simpler and cheaper; the disadvantage is that it's more prone to [User Error](#user-error), as it can be harder to read the letters. Both Steel and Titanium options are available: be aware that Steel has a slightly lower melting point than Titanium. Of course, having a engraved tile in addition to the high-end CryptoTag can increase protection even more._

_As with any unencrypted copy of your master seed, you should protect it somewhere like a safety deposit box, or you'll increase your vulnerability to [Physical Theft, Casual](#physical-theft-casual). However doing so increases the likelihood of [Institutional Theft](#institutional-theft), so be sure to assess which is more likely given your situation._

_This is one of three possible options for maintaining a copy of your Recovery Phrase using a metal-device to increase its durability and [Disaster](#disaster) resistance. CryptoTag is our default choice, as we believe it best combines fire resistance [^24] and preciseness. Of our two optional choices: Cryptosteel is more precise but more fiddly; while a Metal Tile & Engraver are cheap and simple, but can lead to precision problems with messy transcription._

**_Replace the first action in step "F" of your procedure; alternatively, add this action to step "F" if you want to use a metal tile & engraver in addition to CrypoTag._**

1. Use Steel or Titanium Tile & Engraving Pen:
    1. ❑ Engrave the 24 word Recovery Phrase on metal plate (recommend 4 rows of 6 tiles )
        1. Write in ALL CAPS for clarity.
        2. Separate words with "/"s or some other mark.
        3. Push hard enough to make a solid, readable mark, but not quite hard enough to stop the engraving pen's motor.
        4. It can be very challenging to write clearly with an engraving pen. You'll get better with practice. If something isn't clear, cross-out and repeat.
        5. You are only required to write the first four letters of each word to recover, but you may wish to write the entire words for improved clarity.

**_In step "M", store the metal tile in your safety deposit box._**

**_Add one of the following metal tiles to your requirements list:_**

* Design Ideas Identity Plate https://shop.designideas.net/product/identitycase-holder-give-taketake or

* Steel Tile https://www.amazon.com/Art3d-Backsplash-Kitchen-Bathrooms-Blushed/dp/B01ITO9X3I or https://www.amazon.com/Art3d-4-Pieces-Stainless-Backsplash-Brushed/dp/B01DBN6D7Q or

* Steel Tile https://www.amazon.com/Art3d-4-Pieces-Stainless-Backsplash-Brushed/dp/B01DBN6D7Q or

* ColdTi Titanium Tile https://www.amazon.com/TopHat-Technologies-ColdTi-Cryptocurrency-Storage/dp/B077CYKHZ6

**_AND add one of the following engravers to your requirements list:_**

* Manual scribe https://www.amazon.com/gp/product/B06XYZVJJ6 or

* Battery-powered engraver https://www.amazon.com/gp/product/B075Z2QR1 or

* Dremel Industrial Engraver https://www.amazon.com/Dremel-290-05-120-Volt-Industrial-Engraver/dp/B000VZIGA0/ with Dremel Diamond Tip https://www.amazon.com/Dremel-9929-Engraver-Diamond-Point/dp/B00004UDJU

### ❑ Optional Step: Use Metal Enhancement (Redundant Metal Devices)

**Obstructed Adversary:** [Disaster](#disaster), [Institutional Theft](#institutional-theft), [Key Fragility](#key-fragility)

**Created Adversary:** [Death / Incapacitation](#death--incapacitation), [Process Fatigue](#process-fatigue), [User Error](#user-error)

_Cryptosteel, CryptoTag, and engravable steel or titanium tiles are great for preventing disastrous loss of your key, but introduce a real danger since you're forced to leave an unencrypted copy of your master seed in plain sight. An alternative is to use any of these methods to create a redundant set of three metal-protected copies of your master seed, where each copy contains only two-thirds of your words, and any two copies can recover your seed completely[^25]. This continues to protect you from [Disaster](#disaster) and [Key Fragility](#key-fragility) but also introduces robust protections against **Loss by Crime / Theft**, primarily focusing on [Institutional Theft](#institutional-theft) (since you'd usually be protecting your unencrypted master seed in a safety deposit box)._

_The downside of using a two-of-three metal tile strategy is that it introduces complexity into your procedure. When you set up your tiles, [User Error](#user-error) could leave you with an incomplete set of 24 words, if you don't break them up correctly. Later, having to constantly collect two out of three tiles can introduce [Process Fatigue](#process-fatigue). Finally, the complexity of this setup might increase the danger of **Danger/Incapacitation** resulting in your digital fortunes being lost._

**_Enhance step "F" of your procedure as follows_**

* Divide the 24 recovery words among the three metal tiles or Cryptosteel devices, placing sixteen words on each, such that any two tiles gives you all of the words.
    1. ❑ Engrave, stamp, or set recovery words 1-16 on the first metal device.
    2. ❑ Engrave, stamp, or set recovery words 1-8 and 17-24 on the second metal device.
    3. ❑ Engrave, stamp, or set recovery words 9-24 on the third metal device.
* If you're etching or stamping a tile, be sure to number your words or place them in the appropriately numbered spaces, so that you know their proper order

**_Replace the entirety of step "G" of your procedure:_**

1. ❑ **Test Metal Devices A & B.** Use the same PIN to initiate your second Ledger. Rebuild the recovery phrase from devices A & B, to verify their accuracy and your ability to rebuild the complete Recovery Phrase from them.
    1. ❑ Connect the Ledger to your computer and run Ledger Live. Verify that the test transaction is listed and confirmed.
    2. ❑ Disconnect and reconnect the second Ledger and enter an incorrect PIN three times to clear the master key from device. You will see "Your device has been reset."
2. ❑ **Test Metal Devices B & C.** Use the same PIN _again_ to initiate your second Ledger. This time, rebuild the recovery phrase from devices B & C, to verify their accuracy and your ability to rebuild the complete Recovery Phrase from them.
    1. ❑ Connect the Ledger to your computer and run Ledger Live. Verify that the test transaction is listed and confirmed.
    2. ❑ Disconnect and reconnect the second Ledger and enter an incorrect PIN three times to clear the master key from device. You will see "Your device has been reset."
3. ❑ **Test Metal Devices A & C.** Use the same PIN _one more time_ to initiate your second Ledger. This time, rebuild the recovery phrase from devices A & C, to verify their accuracy and your ability to rebuild the complete Recovery Phrase from them.
    1. ❑ Connect the Ledger to your computer and run Ledger Live. Verify that the test transaction is listed and confirmed.
    2. Don't reset it again! Now that you've tested all the combinations of your metal tiles, this is your backup Ledger.

**_In step "M", store one of the metal devices in your home safe and one in your safety deposit box. The third tile should be placed somewhere else reasonably secure. If you _Hire a Lawyer_, that's a great location. Alternatively, consider something like a work safe or a safe at your parents' house_**

**_In step "N" and "O", pick up the third device at the alternative location, then check it in conjunction with the tile stored at the locale that you are checking._**

**_Add the following to your requirements list:_**

* TWO extra Steel or Titanium Tiles; or TWO extra Cryptosteels; or TWO extra CryptoTags.

### ❑ Optional Step: Use a USB Drive[^26]
**Obstructed Adversary:** [Bitrot](#bitrot), [Personal Network Attack](#personal-network-attack)

**Created Adversary:** [Process Fatigue](#process-fatigue), [User Error](#user-error)

_Your main computer is constantly being updated, and it's quite possible that are some point it'll be updated to a version that no longer works with your cryptocurrency software. This is particularly dangerous when you're using open-source software whose maintenance has degenerated or proprietary software whose company has disappeared. To offset the danger of [Bitrot](#bitrot), you can preserve the operating system that you use for cryptocurrency work on a USB Drive, and boot from it whenever you plan to send or receive money. This can also offset some [Personal Network Attack](#personal-network-attack) dangers, because your cryptocurrency OS will be used infrequently, shielding you from malware.

_The downside of using a USB Drive is that it requires both a fair amount of work to setup and more technical sophistication on the part of the holder than the base scenario: expect at least an hour of additional time, with a somewhat advanced procedure. And, it's a bit of a pain to have to boot it up everytime you want to do anything with your digital assets. These elements can add [Process Fatigue](#process-fatigue) and [User Error](#user-error)._

**_Add the following to Step "B":_**

1. ❑ Create a new bootable operating system on a USB Memory Stick (or USB hard drive)
    1. Format the external USB device
    2. Download the installer for your OS
    3. Install the OS to the external USB drive
2. ❑ Boot drive from USB (This will be very slow! It is ok.)[^27]

    1. Many newer operating systems, including MacOS and Windows, disable booting from an external device by default for security reasons. You'll need to flip a security switch to allow it. If you have this issue, your computer should give you a clear message about what to do when you try to boot.
3. ❑ Update with all security updates, but no optional updates and no apps

**_In step "M", store the USB Drive in your home safe._**

**_Add the following to Step "N":_**

1. ❑ Boot from USB drive from your Home Safe; do only essential security updates

**_Add the following to your requirements list:_**

* 1 USB Drive (a new, unopened Memory Stick, rated for fastest speed you can find, that will work with your laptop). I like this dual A & C USB Memory Stick https://www.amazon.com/Patriot-Stellar-C-Type-C-Flash-PIF64GSTRCOTG/dp/B015OYNHY2 or just a one small small USB Hard Drive.

### ❑ Optional Step: Use a (Second) USB Drive

**Obstructed Adversary:** [Bitrot](#bitrot), [Disaster](#disaster), [Systemic Network Attack](#systemic-network-attack)

_If you already "Use a USB Drive", you may want to double-up with a second copy. Any usage of a secondary electronic device can protect against [Bitrot](#bitrot): since you'll be updating your first USB drive in spring and this second USB drive in fall, if a problem arises with an upgrade, you'll still have a clean copy of the OS on your other drive. Similarly, if a operating system is compromised by [Systemic Network Attack](#systemic-network-attack), you have a backup._

**_Add the following step "K" to your procedure:_**

#### **K. Duplicate USB drive**

1. ❑ Reboot computer, and image copy first USB drive to to second USB drive (e.g., with Carbon Copy Cloner)
2. ❑ Confirm that both boot.

**_In step "M", store the second USB Drive in your safety deposit box._**

**_Add the following to your requirements list:_**

* 1 (more) USB Memory Stick (new, unopened, rated for fastest speed you can find, and will work with your laptop). I like this dual A & C USB Memory Stick https://www.amazon.com/Patriot-Stellar-C-Type-C-Flash-PIF64GSTRCOTG/dp/B015OYNHY2 or 1 (more) small USB Hard Drives.

## ALTERNATIVE SCENARIOS

The base scenario suggests a secure way to maintain your digital assets in cold storage. A number of optional steps are all available to you in order to increase your security. Following are some ways in which you may combine those optional steps to serve specific needs.

* Avoiding Private Key Loss
    * Hire a Lawyer, Use Bags (Fire-Resistant, Tamper-Evident), Use a USB Drive, Use a (Second) USB Drive
* Avoiding Private Key Theft, Level 1
    * Hire a Lawyer, Use Bags (Tamper-Evident)
* Avoiding Private Key Theft, Level 2
    * Erase Your Ledger,  Hire a Lawyer, Use Bags (Tamper-Evident), Use Metal Enhancement (Redundant Metal Tiles)

#### Alternative: Avoiding Private Key Loss

**Optional Steps:** Hire a Lawyer, Use Bags (Fire-Resistant), Use Bags (Tamper-Evident), Use a USB Drive, Use a (Second) USB Drive

**Who Should Use This:** People afraid that they will lose their digital assets due to misadventure.

If you're afraid that the base scenario doesn't protect you against accidental loss of a key, you may be right: that's probably the most likely way to lose your digital assets, particularly due to [Disaster](#disaster) or simple [Key Fragility](#key-fragility). To avoid that, you can incorporate a few of the optional steps that all relate to increasing your redundancy, with the understanding that they also tend to increase your vulnerability to various types of purposeful "**Loss by Crime / Theft**".

| Home Safe | Safety Deposit Box | Lawyer |
| :--- | :--- | :--- |
| Ledger Device #1 | Ledger Device #2 | |
| USB Drive (OS) #1 | USB Drive (OS) #2 | |
| | Ledger PIN | Ledger PIN |
| | CryptoTag 24-word seed | |
| | Paper 24-word seed | Paper 24-word seed | |
| Instructions for heirs and xpub and cold storage addresses | Duplicates of instructions for heirs and xpub and cold storage addresses | Duplicates of instructions for heirs and xpub and cold storage addresses |
| All in a fire-resistant bag | All in a fire-resistant bag | All in a tamper-evident bag, itself in a fire-resistant bag |

#### Alternative: Avoiding Private Key Theft, Level 1

**Optional Steps:** Hire a Lawyer, Use Bags (Tamper-Evident)

**Who Should Use This:** People with _some_ fear of key theft and little need to trade coins.

If you don't think the base scenario sufficiently protects your unencrypted keys, a few steps can notably increase your security about **Theft**, mainly by taking banks out of the equation. This has some detrimental effects on your accessibility, but they're relatively minor.

| Home Safe	| Lawyer |
| :--- | :--- |
| Ledger Device #1 | Ledger Device #2 |
| | Ledger PIN |
| | CryptoTag 24-word seed |
| | Paper 24-word seed |
| Instructions for heirs and xpub and cold storage addresses | Duplicates of instructions for heirs and xpub and cold storage addresses |
| All in a tamper-evident bag | All in a tamper-evident bag |


#### Alternative: Avoiding Private Key Theft, Level 2

**Optional Steps:** Erase Your Ledger,  Hire a Lawyer, Use Bags (Tamper-Evident), Use Metal Enhancement (Redundant Metal Tiles)

**Who Should Use This:** People with _strong_ fear of key theft, a _strong_ ability to not lose keys themselves, and no need to trade coins.

The increased protection of Level 1 theft protection might be insufficient if you think you are a prime target of cryptocurrency theft or if you don't feel there is anyone you can trust with potential access to this currency. In this case, you don't want to leave your private key accessible at any location. You keep your Ledger clear when it's not in use and your separate your keys into 2-of-3 sets. In order to somewhat reduce the dangers of [Key Fragility](#key-fragility) and [Death / Incapacitation](#death--incapacitation), a lawyer is involved to ensure that someone besides you knows how (and why) to put everything back together.

| Home Safe | Safety Deposit Box | Lawyer |
| :--- | :--- | :--- |
| Words #1-16 on metal dev. | Words #1-8,17-24 on metal dev. | Words #9-24 on metal dev. |
| Instructions for heirs and cold storage addresses | Duplicates of instructions for heirs and cold storage addresses | Duplicates of instructions for heirs and cold storage addresses |
| | | All in a tamper-evident bag |

## APPENDICES

### Appendix I: Why Cold Storage?

Cold storage is primarily intended for digital-asset custodians who do not actively trade their digital assets. It offers a high level of protection for digital assets, because keys are secured offline or in hardware and _should_ _never be on networked computers._

However, cold storage should be considered as an option for _everyone_ who is managing digital assets. It can be the secure foundation for a more complex scenario that also involves hot wallets, offering the maximum security for whatever percentage of funds don't need to be actively available at all times.

A few questions can help you determine if you can move some of your funds from hot wallets to cold storage:

1. How much quick liquidity do you need?
2. How often are you moving your digital assets?
3. How often are you exchanging your digital assets?

After you answer these questions, you may discover that you don't actually need all of your funds to be always available. The remainder should then be moved off of exchanges into a cold-storage scenario, and the following can provide a model for that.

Even if you determine that all of your funds must remain hot, this cold-storage scenario still suggests a variety of best practices for managing digital-asset keys, and does so in the context of risks and adversaries that will be used to model other scenarios later in this course.

### Appendix II: Sample Digital-Assets Letter

_The following is a sample letter which could be used by a digital-asset holder to alert their heirs of the existence of the digital assets. For a more complete book on this topic, see Pamela Morgan's book [Cryptoasset Inheritance Planning](https://t.co/hsLxiZdQya)._

Dear [Heir],

Today's date is [Date]. This letter is intended to inform you that I own digital assets that are not held or controlled by third parties. I want to be sure that you can access them in case someday I can't. Do not access these digital assets unless I am dead or mentally incapacitated.

Please read through this letter completely before you take any action, and get the help of someone knowledgeable about digital assets such as [a trusted person or persons familiar with digital assets].

Remember, these assets aren't held by a bank and mistakes can't be fixed; the transfers must be done correctly or the funds could be lost forever. Closely watch everyone who helps and make sure you understand everything that is happening. Be extremely careful with PINs, passwords, and "wallet backups" because anyone who sees them can steal the digital assets.

To date I've used [digital-asset exchange brokerage] as my digital-asset-to-US-dollars exchange. This exchange account is connected to my [insert traditional bank name] [checking, savings, or brokerage] account ending in [last 4 digits of the account number]. My exchange account  is registered with the account name  [account name] and password is [reminder of a password that you previously shared with the Heir(s)]. As of the date of this letter, there are no funds in [brokerage]; I only move digital assets there for the briefest amount of time possible in order to exchange to/from US dollars. However, you may need to access [brokerage] just in case there are any funds there in-progress; to do so, you'll need access to my phone for 2FA (two-factor authentication) to move any funds away. The PIN on my phone is [PIN, or reminder of a PIN that you previously shared with the Heir(s)] and the app [app-name] will give you the code to authorize transactions with [brokerage]. If you need to sell digital assets to US dollars, I recommend you set up your own accounts rather than use my [exchange] account. In all cases, you should work with the companies by going through their processes to gain legal access to my account, as it may be illegal for you to use my account and password directly.

Most of my digital assets are held under my master secret, which is a computer-generated 24-word recovery phrase. These words are stored at [where they're stored, and an explanation of whether any additional work is required to decrypt them]. Be very careful with these 24 words as with them anyone can steal my digital assets. It is safer to use [a hardware device containing the private keys], which is located at [location]. [Include a photo of the device too.] It is secured by [PIN, or preferably, an clue of what the PIN is that the Heir will recognize]. Try using that first with anyone helping you move or exchange digital assets and leave the 24 words in the safety deposit box as a last resort.

As of today there are [number] kinds of digital assets stored under my master secret: [a list of what they are]. In the future there may be more or less. Using that master secret, the funds can be recovered from anywhere, but the easiest method is to use my [hardware device] and [software program], which is accessible through a USB stick stored with my other materials.

There may be some other 24-word keys or passwords at [storage location]. These may have smaller amounts of money for [other endeavors] or for lesser incidental use while I'm traveling.

*[Discussion of non-digital assets or important accounts, such as brokerage and email accounts, may also be appropriate for such a letter.]*

Signed, [Digital Asset Holder]

### Appendix III: A Brief Overview of Digital-Asset Adversaries

When creating a scenario for protecting digital assets, a custodian makes choices in his procedures to address vulnerabilities to a specific set of adversaries.

Our term “adversary” is slightly different from the more common term “risk” used by other security analysis models. By anthropomorphizing these threats, we can consider their motivations. This helps a custodian to gain some distance from the scenario by making it less personal; this makes it easier for him to determine which adversaries actually are of greater risk to him personally.

Following is a brief summary of the fifteen adversaries (from a list of over twenty-five) that this particular scenario addresses. Additional categories of "Non-Theft Crimes", "Loss by Government" and "Privacy-Related" adversaries are not strongly considered in the procedures offered by this scenario.

For a complete list of digital-asset adversaries, along with motivations, abstract & historical case studies, risks, and potential process solutions for each, see [Adversaries — Case Studies for Securing Digital Assets Against Loss]() _(available late Spring 2019)_.

#### CATEGORY: Loss by Acts of God

_A loss that wasn’t caused by any intelligent attacker._

##### Death / Incapacitation

_A mortal loss or disability that could endanger funds._ “I am your last firing neurons, and I seek to drag everything you ever knew down with you, into the darkness.”

##### Denial of Access

_Physical denial that prevents use of funds._ “I want to control your movements, to keep you from getting to your bank or to your house. As is often the case, I have a deeper motivation, but it probably has nothing to do with your cryptocurrency. Instead, my motives likely relate to an instability in your city, state, or country. I might be a riot, a political insurgency, or a popular uprising.”

##### Disaster

_A sudden, large-scale destructive event._ “I want to destroy. I want to crumble and burn. I want to ruin with water, to blow things into the air. I am bombs, bullets, and explosions. I am sudden and unexpected but disastrous destruction.”

#### CATEGORY: Loss by Computer Error

_A loss caused by computer hardware or software._

##### Personal Network Attack

A personal online attack._ “I want to control your movements, to keep you from getting to your bank or to your house. As is often the case, I have a deeper motivation, but it probably has nothing to do with your cryptocurrency. Instead, my motives likely relate to an instability in your city, state, or country. I might be a riot, a political insurgency, or a popular uprising.”

##### Bitrot

_A hardware, software, or media failure leading to loss._ “I am entropy writ large. I want to break down your storage, crash your hard drives and degrade your optical media. I want to prevent your computers from booting, your programs from running, and your data from reading; in the end, I always win.”

#### CATEGORY: Loss by Crime, Theft

A loss caused by a criminal taking your keys (and thus funds) from you.

##### Institutional Theft

_A theft by a trusted institution or its employee._ “I pretend to be a good employee, but I’m always waiting for my chance for a great score. I want to sift through the goods entrusted to my company and to take the best for myself. However, I don’t want to be caught, so I need to be cautious in my larceny.”

##### Internal Theft

_A theft by a trusted person such as an heir or executor._ “You trusted me with your private keys. I intend to violate that trust because I want to steal your funds for my own use. And, I’ll do my best to cover it up.”

##### Network Attack, Systemic

_A server online attack._ “I’m a big kahuna among hackers. I don’t go after your little bitcoin wallets, I go after the exchanges or other bitcoin sites instead. Nonetheless, you might just find yourself at a literal loss when I bankrupt the company holding your wallet.”

##### Physical Theft, Casual

_An opportunistic physical theft_ “I just want an easy score, and your house looks like it. Obviously, I’m taking your jewelry and your electronics. But, if you got a safe, I’ll try to take that too. I have no idea what I’ll do with it, or with the contents if I can get it open. If I see some weird numbers, I’ll probably just trash them.”

##### Physical Theft, Sophisticated

_A purposeful physical theft of private keys._ “I know you have cryptocurrency and I want to steal your keys. I’m not a fancy hacker or email spoofer. Instead, I’m someone who can successfully stage a real-world crime. I’ll break into your house or your safety deposit box. Cut the music for my heist scene.”

#### CATEGORY: Loss by Mistakes

##### Key Fragility

_An accidental key loss._ “I am entropy writ small. All I need to do is mislay a digit or two from a ridiculously large number, and my job is done. Perhaps you could make my job easier by encoding or obscuring your key or by maintaining just a single copy; complexity and singularity both beget fragility in different ways..”

##### Process Fatigue

_Errors caused by the complexity of the overall procedure._ “I am laziness and exhaustion. I want to encourage you to skip the most time-consuming steps of a procedure, because they’re too much trouble. I want to introduce small errors as you go, because you’re tired of this repetitive yet mindful task. I want to turn your procedure against itself, so that the very process intended to protect your funds causes you to lose them.”

##### Transaction Error

_Incorrect transaction details leading to loss._  “I am the slightest error in a transaction. I’m the script that can’t complete, the address that goes to the wrong place, or even the fee that wasn’t big enough. I want your transaction to do something that you don’t expect. I am startling results that are ultimately detrimental to you.”

##### User Error

_An operator mistake leading to loss._ “I’m that niggling mistake that wouldn’t be a major problem in most financial situations. I want you to make a typo or to use the wrong address, so that you don’t get your money or send it to the wrong place. I want you to lose your keys, so that you can’t recover your funds. I am all the anxieties you have about Bitcoin made real.”

## AUTHOR BIOS

**_Christopher Allen_** is an entrepreneur and technologist who specializes in collaboration, security, and trust. He worked with Netscape to develop SSL and co-authored the IETF TLS internet draft that is now at the heart of secure commerce on the World Wide Web. More recently, he was Principal Architect at Blockstream, where he led blockchain standards efforts. Christopher is today co-chair of the W3C Credentials CG working on standards for decentralized identity and founder of Blockchain Commons. He also founded and facilitates the semi-annual Rebooting the Web of Trust design workshops, which have generated over 40 collaborative white papers about the next generation of internet privacy, security, and identity software.

**_Shannon Appelcline_** is a technical writer with expertise in blockchain, cryptocurrency, and digital identity who specializes in making technical concepts accessible. He has regularly written for Bitmark, Blockchain Commons, Blockstream, and Certicom, and his work has made the front page of Hackernoon. He is also the editor-in-chief for Rebooting the Web of Trust. In the non-technical sector, Shannon wrote a four-book history of the roleplaying field, _Designers & Dragons_, and recently co-authored _Meeples Together_, a study of cooperative game design, with Christopher.

**_Bryan Bishop_** is a Bitcoin Core contributor and independent technology consultant. Bryan previously spent 4 years at LedgerX, the first CFTC- regulated bitcoin options exchange and clearinghouse. At LedgerX, he implemented an industry leading solution for the secure storage of digital assets and cryptographic keys protecting many millions of dollars. Bryan's background began in software, especially in web application development at various startups. Separately in his biotech activities, he co-founded the "Culture Shock" open-source electroporator project. Additionally, he serves on the technology working group and intellectual property working group for Genome Project-Write, an organization tasked with reducing the costs of human genome synthesis by 1000x within 10 years.

## Notes

[^1]: These items should ideally be sent to your work address or to a UPS or FedEx store for pickup, not a home address, so as not to correlate your Bitcoin holdings and your real name.

[^2]:Current requirements are: macOS 10.9 (64-bit), Windows 8 (64-bit) or Linux Ubuntu 16.10.

[^3]:We were forced to make a decision between two major hardware wallets: the Ledger and the Trezor. Both are good, mature solutions with well-reviewed code and solid ecosystems. We ultimately selected the Ledger because it stores its private keys on a cryptographic chip. Since we advocate keeping a hardware wallet in a less-secure home safe, this was a requirement, as it offsets the adversary of Casual Physical Theft. There are disadvantages to the Ledger as well: its cryptographic chip is proprietary, thus unlike the Trezor all of its code isn't open source. Thus, our understanding of its security is ultimately somewhat limited. If another hardware wallet were to appear with an open cryptographic private-key store and open-source code, we would recommend that instead. In the current market, however, we believe that the Ledger device is the best for this scenario. You may substitute a Trezor for this scenario as the tradeoffs are somewhat subjective.

[^4]:We similarly chose the CryptoTag because we thought it the best option when compared to alternatives like Cryptosteel and engraved tiles: more discussion of this can be found in the Optional Steps section.

[^5]:Note that most home safes do not offer enough [Disaster](#disaster) resistance to sufficiently protect your digital assets. At best they are rated to protect paper against fire. The primary goals of a home safe are to store your PIN-protected key on on a redundant Ledger, to help protect against [Physical Theft, Casual](#physical-theft-casual), and to provide a secondary location to store a redundant PIN-protected Ledger key in case of physical [Denial of Access](#denial-of-access) to your safe deposit box.

[^6]:It could be argued that this Safe Deposit Box should not be in the same town as your home safe. If a earthquake or fire strikes Berkeley, it is not likely to be as bad in San Jose, and vise versa. You will be visiting it at least once a year, so it should not be too inconvenient. If you are near an international border (for instance in Seattle or Vancouver), it can be useful to have your Safe Deposit Box in another country from your residence to assist against Legal Forfeiture. However, it is more important to be sure that both you and your heirs have easy access to it.

[^7]:Joint names associated with a joint account should make it more difficult for legal physical [Denial of Access](#denial-of-access) to box by the heirs, however, the rules for this differ state-by-state. Ideally this account should be in the form of "joint tenancy" and "tenancy by the entirety". You should seek advice of a local lawyer. See http://www.weisslawstl.com/2008/02/16/joint-tenancy-accounts-safe-deposit-boxes-will-substitutes-will-substitute-will

[^8]:Higher security scenarios will require the initialization of computer devices and keys generated in a room with no windows, all cell phones turned off, laptop cameras and microphones turned off and taped over, and limited internet connectivity (no wifi). This is not required for this base scenario, but is cheap and easy to do.

[^9]:One of the most important principles of these procedures is that the Recovery Phrase (which is the Master Private Key Seed for all of your digital assets) is generated on trusted hardware certified for key creation, and from that point the Recovery Phrase or Master Private Key Seed never resides physically on a network-attached computer.

[^10]:Though not supported by Ledger Live today, some other wallet software allows the encryption of the Recovery Phrase with an additional password using BIP38. We recommend in this base scenario AGAINST encrypting the Recovery Phrase. The loss of a password in an encrypted Recovery Phrase is one of THE most common reasons for bitcoin loss. In this procedure the Recovery Phrase is unencrypted in the most secure location and is thus available as last resort.

[^11]:Though we describe here how to install Bitcoin on your Ledger, the Ledger software actually supports multiple cryptocurrencies. The same procedures can be adapted for any other cryptocurrencies that you are holding.

[^12]:Why? Because if there is ever a systematic attack on the chips (as happened with the Infineon chip in the YubiKey), firmware (as happened with the Trezor), firmware app, or client software, you can know if you were possibly affected.

[^13]:You may be tempted to skip this step. **Don't.** Transmitting cryptocurrency is a somewhat technical, somewhat unforgiving task. As discussed in the Adversaries white paper, there are numerous ways that errors can be introduced into cryptocurrency transmission, such as accidentally writing down the wrong address or recording a spoofed address. Sending a small amount of cryptocurrency to an address before committing larger amounts will address some of these potential errors and is a critical (if minimal) step to protect your electronic investment. Even after that initial test, you should still be extremely careful every time you send cryptocurrency, to avoid devastating problems like forgetting to return your change to a change address.

[^14]:Obviously, if you don't spend your test transaction, you'll lose it if you choose to erase your devices and start over with a new Recovery Phrase.

[^15]:I recommend titanium; as it has a melting point of 3287°C it will likely survive a disastrous fire. Steel is good, with a melting point of between 1300° - 1500°C will survive most common fires. Either, combined with fireproof envelope and stored in a bank safe deposit box, should survive most disastrous situations.

[^16]:The safe at home is not required, but is convenient. It's most important that there be at least one additional place, besides the safe deposit box, that is somewhat secure against [Physical Theft, Casual](#physical-theft-casual) and that will also protect you against physical [Denial of Access](#denial-of-access), if you are locked out of your safe deposit box.

[^17]:Like using tamper-proof bags, there are some questions as to how much security is added by physically signing the cases of the hardware, as any attacker sophisticated enough to create a working fake that functions with your PIN could also duplicate the case. However, it is a low cost and easy thing to do.

[^18]:I suggest spring & fall for reviews, to avoid winter and summer holiday times.

[^19]:For my spring review, as it is near tax time and April Fool's, I focus on the accounting — I check transactions against my balances on my exchange, consider if I need to balance my portfolio, and in general focus on "foolish" mistakes I may have made.

[^20]:For my fall review, near Halloween and the Day of the Dead,  I focus on updating my instructions to heirs, confirming with my heirs that they know about my digital assets and how to get help if they need it, etc.

[^21]:It is particularly important that you sign in to your safe deposit box yearly. There have been cases where lack of regular access to a box has been interpreted as it being "abandoned" or "dormant", causing its seizure as "unclaimed property" and sale by the state. This has happened in the states of Georgia & California. See http://abcnews.go.com/GMA/story?id=4832471

[^22]:Before giving any digital asset key material to a lawyer, make sure the materials are sealed in an opaque envelope in a tamper-evident bag. Never tell your lawyer your 24 words over the phone and never ask the lawyer to write down your 24 words.

[^23]:https://twitter.com/crypto_tag/status/1073206843525222400

[^24]:https://twitter.com/crypto_tag/status/1073206843525222400

[^25]:Note that there is some danger if an adversary accesses one of your three metal-devices. Whereas the 24 words gives you 256 bits of entropy, if an adversary knew 16 words but not the remaining 8, you'd drop down to 80 bits of entropy. This is still relatively safe given the state of modern computers, but is far below the recommended entropy for protecting cryptocurrency long-term. If you lost one of your three metal devices, you should immediately reset your master seed and transfer your currency.

[^26]:This USB drive is mostly for convenience, to assist against the form of Bitrot that is upgrade rot and to protect against some forms of active attack. The USB drive never has any key material on it, but it does allow you to return to a known working state without adding new code to the system. If a USB drive dies, it can be replaced.

[^27]:In my case, I confirmed that the USB drive booted on multiple Macintosh models, not just my primary laptop.
