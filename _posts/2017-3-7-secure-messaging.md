---
layout: post
title: Secure Messaging
---

Today, information was released regarding the CIA and their surveillance of civilians. The messaging services such as Telegram and Signal appear to be compromised.

You can read about Wikileaks' latest leak [here](https://twitter.com/i/moments/839221561026498560).

If you truly want safe and secure messaging, you should not be using a service that requires your phone number.

Telegram and Signal are both great messaging services. I personally use Telegram. However, if you are looking to make sure the CIA is not spying on you, you should consider alternatives.

If you are not familiar with the Tor Project, [you should be](https://www.torproject.org/).

[Ricochet](https://ricochet.im/) is an application that uses Tor to deliver secure messaging. When you use Ricochet, it sets up a Tor Hidden Service on your machine. The hostname of this hidden service is the ID that others can use to message you.

Using this style of messaging, your traffic goes through Tor and you are anonymous. The only thing that identifies you is your hidden service hostname.

For messages that are very important, you can encrypt with GPG encryption.
Make a file called message.txt with the contents of your message.
Then open your terminal and navigate to where you saved your message.
Type `gpg -c message.txt`.
Now enter your passphrase and a file called message.txt.gpg will be created.
This file is encrypted.

You can convert this file to human readable text with Base64 Encrypton.
In your terminal, type `cat message.txt.gpg | base64`.
Now you can copy this text and send it to the recipient.

Decrypting the message is just as easy as encrypting in.
First, Copy the Base64 encoded text to your clipboard.
Next, type `echo $encoded | base64 --decode > message.txt.gpg`,
where `$encoded` is the Base64 encoded text.
Now you have a file called message.txt.gpg.

Type `gpg message.txt.gpg`.
Now the file has been decrypted and the content of the message is in a file called message.txt.
