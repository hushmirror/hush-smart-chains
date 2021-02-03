# Hush Smart Chains - The z2z Platform

Hush Smart Chains (HSCs) are a way to create your own HUSH blockchain, with a focus on fully-shielded (z2z) chains for
maximum privacy. These blockchains can be run completely isolated from the internet and decide if they want to
interact with the main HUSH blockchain (HUSH mainnet).

## Private vs Public Hush Smart Chains

Private Hush Smart Chains are perfect for a group of people who want to use encrypted memos but do not want their
data on the public Hush mainnet. It allows groups to completely isolate their data, yet still use HUSH technology.

A Private HSC could be run on a VPN which requires credentials to even get on the network, while a Public HSC is meant
to "federate" and allow anyone on the internet with compatible software to join. Some HSC's could be in remote places,
such as a LAN of a few computers that only occassionally gets batched Internet data via radio or satellite. HSC's do
not need the Internet to operate and they can wait to transmit data, when there is a connection, or simply listen, and
never send any data out. The use casese are very flexible.


# Use Cases

A Hush Smart Chain (HSC) can be used as a factory to make isolated and compartmentalized encrypted messenger platforms.
We will describe a few use cases. HushChat is compatible with all Hush Smart Chains.


## Use Case: Medical Billing

Alice is a health-care professional who accepts health insurance. She must submit
medicall billing information to a 3rd party to receive payment for her services.
Traditionally this is done with fax machines and unencrypted email, with no concern
for privacy at all.

Insurance companies would create their own HSC's and then health-care providers such
as Alice and Bob, could use an encrypted protocol with extremely high privacy. Of
critical importance is that there is a record of thise information being transacted.
If the insurance company is suspected of doing fraud, there is cryptographically-signed
history of what happened.

The regulating entity of said insurance company could request to see a history of all
transactions, or just all transactions of a certain person, with `Hush viewkeys`. This
system discourages cheating on both sides by providing a ledger of information transfer.

## Use Case: International Medical Records

Currently if Alice would like to send medical records internationally, people resort
to fax machines, unencrypted email or physically handing them over. If individual
health care professionals create their own HSC's, their client data is completely isolated
from the rest of HUSH mainnet, which may be required for government compliance anyway.

Alice could send her doctor Bob a PDF of her medical records or a textual account of them,
or perhaps a picture of her prescription. This needs only to be seen by Alice and Bob, but
currently, if you use Gmail to email it over, you have provided Google invaluable marketing
information that they will utilize and sell, forever.

## Use Case: Client-Lawyer Communications

Alice is being persecuted by the local police for something she did not do, in sunny Portland, Oregon.
She searches the web for a lawyer that is close by. She contacts her
new lawyer Bob via HushChat on HUSH mainnet, as a way to initiate communication. Then
they immediately switch to Lawyer Bob's Hush Smart Chain PDXLAW, and then they can
communicate knowing that they are leaking information to as few people possible.

Alice can send image attachments to Bob to show him evidence and send textual chat which are encrypted
"in transit" and "at rest". What this means is that all data is encrypted in transit, while it moves on
the network, and then it's also encrypted when it's on Bob's harddrive. The data is never stored
unencrypted, unlike traditional communications with lawyers, which usually use the Plain Old Telephone System (POTS),
including fax machines, and unencrypted email.

## Use Case: OnlyFanz Club

Alice absolutely loves Boy Gaga, and wants to join his fanclub. Boy Gaga, and other celebrities,
can make their own blockchains to communicate with their fans, using HushChat as a pay-to-talk platform,
or pay-for-image, or various other use cases. HushChat is a platform for communicating about purchases,
and every HushChat can attach HUSH (or FANZ coins) to unlock more content/value/etc.

In this model, each celebrity owns their own blockchain, like owning their own label or recording study. They
are not under the thumb of whoever controls the communication or payment platforms. These blockchains can
integrate with HUSH for 51% attack protection or be completely their own entities. Some people may want to
use HUSH mainnet directly for convenience and then migrate to their own system as they expand.

## Use Case: United Nations Human Rights reports

Alice wants to report a Human Rights issue to the United Nations about something happening locally. She
is worried that it could endanger her to simply use email, or Twitter/Facebook/etc which all work with
local governments against "whistleblowers".

The United Nation could provide a service, similar to SecureDrop for journalists, to report issues in a
private manner. This also has the benefit of there being a censorship-resistant record of what is happening.
This would improve the dignity and privacy of all people. Privacy is a universal human right.

In this use case, it's important to use Delayed-Proof-of-Work to send data to HUSH, so it can be protected
by Bitcoin hashrate security.


## Developers: Creating a Hush Smart Chain

You will need the [Official Hush full node Git repo](https://git.hush.is/hush/hush3):

```
git clone https://git.hush.is/hush/hush3
cd hush3
./build.sh -j4 # uses 4 cores
cd src
```

### Zcash replica

As a first simple example, if we wanted to make a replica of Zcash called Tcash (but with many improvements):

```
hush-smart-chain -ac_name=TCASH -ac_blocktime=75 -ac_supply=0 -ac_halving=210000 -ac_reward=1250000000 -addnode=1.2.3.4
```

The above command makes the ticker of that chain `TCASH` with a block time of 75 seconds and halving every 210000 bloks with
initial reward of 12.5 TCASH. The default block time is now 60 seconds and is a good default for most use cases.


### Pirate replica

As an example, we will make a replica of the cryptocoin Pirate (ARRR) in a single command:

```
hush-smart-chain -ac_name=ARRRUKIDDING -ac_supply=0 -ac_halving=388885 -ac_private=1 -ac_reward=25600000000 -addnode=1.2.3.4
```

This replica has exactly the same mining schedule as PIRATE as well as block reward. One notable exception
is that all Hush Smart Chains are Pure Sapling, which means no 1.6GB download would be required to sync
the `ARRRUKIDDING` chain.

One may note that the halving interval looks different than the 77777 that Pirate normally uses. This was
the halving interval of the original Pirate chain, which the author mined on, but would have lead to all
mining rewards being emitted in about 5 years. Komodo internally multiplies the interval by 5 to give a
~25 year emission and that is where 3888885 comes from.

## Adding DPoW

All Hush Smart Chains support Delayed-Proof-of-Work innately, though the service must be run and data injected into the network.
DPoW is not needed for private Hush Smart Chain. Public Smart Chains that will have financial value need protection
from double spend attacks, so DPoW is highly encouraged.

## Getting Help

We are happy to help you build upon the Hush platform, please join our [Telegram](https://hush.is/telegram) and ask questions.
