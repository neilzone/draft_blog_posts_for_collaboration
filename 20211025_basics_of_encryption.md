The end-to-end encryption debate: 1: the (very) basics of "encryption"
-

Someone - sadly, I cannot remember who - asked if there was a good, neutral, explanation of the end-to-end encryption debate.

I have not found one, and I think it would be useful[^2], so here is my attempt.

This is going to be a multi-part series of posts, rather than one long post.

This post offers a *very* high level introduction to "what is encryption", because there is little point jumping into arguments and regulatory approaches if you are not familiar with at least the basics of the topic at hand.

If you're an experienced cryptographer, you can (and probably should) skip this, unless you want to read it and [send me feedback on any errors I've made](https://decoded.legal/contact/).

# Is there lots of complicated maths in this post?

No. No maths.

# What do you know about encryption and encryption policy?

I'm not a cryptographer. I've only got a GCSE[^1] in maths.

I use encryption daily (as does pretty much everyone; see below!). I also try to offer [a range of communications options](https://decoded.legal/communications_options/) to cover the range of needs of clients and potential clients.

I am a lawyer with a reasonably long involvement in UK tech policy (especially Internet and telecoms policy), including encryption debates. (If you're in the UK government or civil service, reading this with your head in your hands, thinking "it's that bloomin' Neil interfering again", my apologies.) 

I have advised on a range of encryption-related matters, some of which I can talk about (e.g. the implementation of public-facing DNS-over-https infrastructure, corporate network-level traffic inspection, encryption as a facilitating factor for data protection, "cryptoshredding" and anonymity of personal data) and more which I cannot.

# What is encryption / what can encryption achieve?

Encryption is the use of an algorithm to grant, or attempt to grant, additional properties to a set of information, or to a communication, typically through the use of secret information.

Although it is common to equate "encryption" with "making it harder for unauthorised persons to turn encrypted information into something they can read" - and this, known as **confidentiality** *is* a common use of encryption - confidentiality is *only one* of the things routinely accomplished by encryption.

In addition to confidentiality, an encryption system may provide (not necessarily guarantee; see below) some, all, or none of the following:

**Anonymity**: keeping the identity of a party unknown. This may be unknown to the other party or parties, or to one or more service providers.

**Asynchronicity**: the ability for someone to send a message, even though their intended recipient is offline, or for someone to receive a message, even though the sender of that message is offline.

**Authentication**: checking that the encrypted information was encrypted correctly, using the chosen encryption algorithm.

**Causality preservation**: checking that multiple messages were delivered in the order in which they were sent.

**Destination validation**: checking that the actual recipient was the intended recipient.

**Forward secrecy**: preventing someone who obtains the secret information from decrypting previous encrypted communications.

**Future secrecy**: preventing someone who obtains the secret information from decrypting previous encrypted communications.

**Integrity**: checking that the message which you have received the same as the message that was sent.

**Message repudiation**:  preventing a third party who knows that one person sent a particular message from identifying them as the source of other messages.

**Message unlinkability**: preventing a third party who knows that one person sent a particular message from identifying them as the source of other messages.

**Participant consistency**: checking that the parties to the conversation are the same for all parties.

**Participant repudiation**: providing the identity of the sender only to the recipient(s), such that a third party cannot tell whether someone was the sender of a message.

## Why does this matter?

This matters for a couple of reasons:

- Because if you think about encryption policy only through the prism of confidentiality, you may not take into account some of the other things which people rely on encryption providing.
- If you think you have identified a problem, not considering the full range of things encryption can be provide may mean that your solution is incomplete because you have not fully defined the problem you are trying to address.

# Does encryption require computers?

Just like mathematics more generally, not all functionality of encryption requires computers.

Some functionality - in particular, confidentiality - can be attained, to some standard, [with a pen, paper, and dice](https://www.revk.uk/2017/06/pen-paper-cryptography-people-always.html?m=0).

However, in some situations - for example, to encrypt a synchronous / real time audio or video call - encrypting without using a computer is unlikely to be realistic.


# What can be encrypted?

In the digital environment, anything. It is not limited to text-based messages. Encryption can be used for audio- and video messaging too.

If you want to encrypt a synchronous / "real time" audio or video call, you need to ensure both sender and recipient can encrypt and decrypt rapidly enough to maintain their conversation. 

Conversely, if you want to send a message for asynchronous interaction - for example, an email, or information which is to be transferred on a USB drive, or printed out - you do not have the same limitation.

Different encryption systems may work better in one situation or another.

In other words, there is no one way of doing encryption, and each system involves compromises and trade-offs.

# Does encryption guarantee security or safety?

No.

First, "encryption" is a concept. In practice, encryption is carried out through algorithms, and not all algorithms are the same, or attempt to do the same things. Some algorithms have more flaws than others. Some algorithms demand more from users than others (e.g. more computational resources, or more technical skill).

Second, it's generally unwise to talk about security or safety in absolute terms. Typically, one would identify the threats they face, and the resources they have to protect themselves against those threats (bluntly, probably their budget), and work out which set of compromises get them closest to what they want to achieve.

Some of the questions one might ask to assess security or safety are:

- Secure against *whom*? The average person in the street who might be interested in something obviously valuable or salacious but who is not going to try too hard? A skilled and determined adversary (perhaps an abusive partner, or a company engaged in corporate espionage), willing to throw some money / equipment / competent people at it? A nation state, with a massive budget and access to top of the range equipment and large numbers of skilled people? 

- How valuable is the information to the attacker? Linked with the identity of the attacker is the value of the information to them. A nation state, for example, may be willing to throw significant resource at something which they think might be seriously harmful to national security, but may not be willing (or legally permitted) to spend their budget or resource on something more trivial, such as the encrypted shopping list of someone who is not a person of interest.)

- Secure for *how long*? Does an attacker need to obtain the information, or identify or attribute the sender or recipient(s), very quickly (e.g. the information has a short "shelf life"), or would it be worth their while to spend a long time trying to get what they want? Could they wait potentially years and years, until a different way of computing is available to them?

A corollary of this is that if someone promises "absolute security" or "perfect security", I would suggest you are very wary indeed.

# What is "military grade encryption"?

Marketing fluff.

# What is "end to end" encryption?

There is no legal definition of "end to end encryption". Nor, as far as I am aware, an agreed / common technical definition.

This means that different people may attempt to argue that their own definition is the "correct" definition, or that their proposal does not interfere with end to end encryption (a position which could be politically savvy) because of how they have defined it.

Security expert Alec Muffett has [proposed a definition of "end to end secure messaging"](https://datatracker.ietf.org/doc/draft-muffett-end-to-end-secure-messaging/03/).

My interpretation of "end-to-end encryption" is that, within the confines of a particular system[^3], only the sender and intended recipient(s) of a message are able to decrypt the message (i.e. that confidentiality is maintained between sender and intended recipient(s)). Whether other qualities of encryption are involved will depend on the system.

An end-to-end encrypted communication may still transit through a centralised routing system, or rely on signalling from a centralised routing system, but the content of that communication is not visible to / capable of decryption by the operator of that system.

In nearly all of the policy debates I have seen, or been party to, the distinction which many of those involved are attempting to draw is between:

- Not end-to-end encrypted: a system where a message is encrypted between sender and an intermediary, and from that intermediary to the recipient, with a plain text gap in the middle, which permits the intermediary to determine the sender and receiver of the message, and to see the content in plain text, and take action based on it (such as sharing it with a third party), or to decide not to forward it to B, or potentially to manipulate it.
  - e.g. A wishes to converse with B, but their choice of system entails A sending the message to Platform P, and Platform P decrypts it, re-encrypts it, and forwards the re-encrypted message to B.
  - the reason I say "sender and intended recipient" in my sort-of definition is that some people argue that even this example is "end to end" encrypted, it's just that the intermediary - Platform B - is an "end" for both of the legs. I don't think this is credible.
- End-to-end encrypted, a system which does not permit those things, because the intermediary does not, or cannot, have the access required. Only the sender and intended recipients have the ability to that.

There is, in my view, scope for discussion as to whether the use of software on a sender's or recipient's device, which can "do something" to the content of communication before it is encrypted or after it is encrypted, means that the resulting system is no longer "end to end encrypted". This may depend on whether that software is "doing that something" at the user's behest, or at the best of a third party.

For example, my personal view is that:

- if a user chooses to block messages based on post-decryption filtering, or to file messages in a particular way, that system remains end-to-end encrypted.
- if a third party can access (e.g. forward, manipulate, or take action based on) the content of a message post-decryption, because that is how the system is designed, then that system is not "end to end encrypted".

# Who uses encryption?

I'm generally fearful of talking in absolutes, because life is often more nuanced. 

However, my feeling is that it is true to say that everyone who plays, works, chats, or otherwise engages online uses encryption.

## Transport encryption

Transport encryption refers to encryption of the connectivity - the transport or transmission - between two points.

This means that someone spying on your network connection may be able to tell where you are sending your traffic, and they may be able to derive conclusions based on the "shape" of your traffic, but they cannot see what is in that traffic unless they can break that encryption, or unless they are in the path of that encryption and can terminate it.

You are using - or have just used - transport encryption *right now*.

You are reading this blog. The connection between your device and my web server is encrypted. Or, if someone has deployed a network surveillance device to monitor your traffic, your connection to their surveillance device is probably encrypted, with them pretending to be my web server, and - hopefully - the connection between their inspection device and my web server is encrypted.

If you use email, one would hope that the connection between your email software (mail user agent) and your email server (mail transfer agent) is encrypted each and every time. And - hopefully - the connection between your server and the server your email recipients' use is also encrypted.

When you use online banking, or shop online, the connection between your computer and the bank's site, or the online shop, or their backend payment service, is - hopefully - encrypted in transmission.

The connection between a payment system in an offline shop and their payment processor? Encrypted. So you might be using encryption in all sorts of situations without knowing it.

Your Wi-Fi connection, between your phone/computer and your wireless access point? Your traffic - calls, messages, data sessions - over the air interface of a cellular network? Both encrypted in transmission (hopefully!).

## Content encryption

As well as encrypting a transport link, encryption can be used to encrypt the payload: the *content* of the transmission, as opposed to the connectivity.

This means that, if someone is able to intercept your transmission despite your use of transport encryption (e.g. someone monitoring your network connection, for content filtering purposes), or if the system design means that they can terminate the transport encryption (for example, email services), they may be able to tell some things about your traffic, but not the actual content. Exactly what they can tell will vary based on the service, and the encryption system, and what other information is available to them.

Depending on the encryption system, you may also get some reassurance that the file you have received is the unmodified file the sender sent, and some of the other functions of encryption described above.

A simple example of content encryption is if you encrypt a file and put it on a USB stick, and post it to someone. The transmission may be relatively insecure, but the content of what you are sending is encrypted.

Similarly, if you encrypt a file before you upload it to a third party file storage or sharing system, you are using content encryption (probably in addition to transport encryption). This should mean that, even if someone at that file storage service takes a peak at what you've uploaded, they are less likely to be able to tell what you have stored. If you had just used transport encryption, a rogue employee at that organisation, or a hacker who manages to access your files, could see what you had uploaded.

If you use PGP when you email me, you use content encryption (albeit an encryption system without many of the functionalities set out above; it's far from ideal).

Do you use Signal, or WhatsApp, or matrix, or cwtch? These messaging services use both transport *and* content encryption.

Hopefully your computer's or phone's software update system also uses content encryption, to help verify that the files they are using to update your systems are the genuine, unmodified files. And, perhaps, that they originated from the "right" organisation.

## Does that mean criminals use encryption?

If everyone who engages online uses encryption, yes, it follows that criminals also use encryption. Criminals also use cars, wear clothes, hopefully brush their teeth, and so on.

(One for the next blogpost in this series, looking at some of the arguments in encryption policy, but note that criminals are not known for following for the law. They are probably the worst group for that. So a "ban on encryption" is unlikely to affect people - including criminals - intent on using encryption. The maths is out of the bag.)


[^1]: General Certificate of Secondary Education, which is an exam students in England sit - or sat; I'm old, and I don't know what the current education system here offers - around 15/16 years of age. It's basic stuff only.

[^2]:  Although I am (pessimistically? realistically?) not convinced that it will catch on, because I think some will find it beneficial to advocate or argue from a position of relative ignorance.

[^3]: I don't consider it a failure of end-to-end encryption, or that a system is rendered "not end-to-end encrypted", if an intended recipient can share a message they have correctly received with someone else. (e.g. A sends B an encrypted message via Platform P, and B tells C about it.)
