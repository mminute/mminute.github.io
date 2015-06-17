---
layout: post
title: "ENIAC wasn't first?..."
date: 2015-06-16 19:13:20 -0400
comments: true
categories: 
---

{% img https://upload.wikimedia.org/wikipedia/commons/e/e4/Frontal_view_of_the_reconstructed_Colossus_at_The_National_Museum_of_Computing%2C_Bletchley_Park.jpg %}

Try taking a tour of an engineering building at Penn without someone telling you about how ENIAC was the first digital computer.  Seriously, try it.  I bet you a million dollars they mention it.  Seriously, bet me.  Please?  I could use the cash or there may be a significant increase in my ramen consumption quite shortly.  No?  Fine.  Whatever.

I believed those professors and tour guides because 1) I figured that they knew what they were talking about, and 2) I’d seen it in books.  Everything in books is true, right? #bible.  Turns out tour_guides.liar_liar_pants_on_fire? returns true.

There is a YouTube channel called ‘Computerphile’ that puts out videos digging down into some of the minutiae of the history and inner workings of those magical thinking boxes that we all carry around.  Ever wonder about the discrete cosine transformation used to encode jpeg images or the significance of the Altair 8800? No?  Well if you did you could hear all about it from experts in the fields.  It, along with it’s sister channel ‘Numberphile’, are worth a look.

Anyway, back to the issue at hand… I ran across one of Computerphile’s vids this past Monday.  The topic: Colossus, the world’s first (at least partially) programmable electronic digital computer.  The prototype, Colossus Mk 1 was operational in December of 1943 and put into service February 5, 1944, preceding ENIAC (completed in November of 1945) by nearly two years.  Bonus points for having a way better name.

<iframe width="640" height="390" src="https://www.youtube.com/embed/9HH-asvLAj4" frameborder="0" allowfullscreen></iframe>

The Colossus was designed and built by engineer Tommy Flowers, assisted by William Chandler, with Sidney Broadhurst working on the auxiliary electromechanical parts at the Government Code and Cypher School (GC&CS) in Bletchley Park in order to break the cryptography of the Lorenz SZ42 cipher machine used to encrypt messages transmitted by the German High Command and Army Commands.  Though the better known Enigma was more common (due to its greater portability), it was used more in the transmission of tactical information, while the Lorenz, a far more complex cipher, was used to securely transmit information of a more strategic nature; ‘securely’ at least until Colossus came along.

Colossus was the first example of program-controlled logic, parallel processing, variable programming, hardware interrupts, optical reading of punched paper tape, and shift registers, all concepts that would become critical in the future development of computing.

It is worth taking a moment to note how much more complex the challenge was facing Colossus in comparison to the challenge facing Turing’s ‘Victory' (not ‘Christoper’, sorry Cumberbatch) electromechanical computer.

Enigma:
3 rotors (Army and Air Force) or 4 rotors (Navy) with 26 settings each.  The three rotor version could be configured in:
158,962,555,217,826,360,000 different ways.  Thats 159 million million million.

Lorenz:
12 Rotors, each with a different number of possible settings.

Rotor Number => Possible settings.

{1=> 43, 2=> 47, 3=> 51, 4=> 53, 5=> 59, 6=> 37, 7=> 61, 8=> 41, 9=> 31, 10=> 29, 11=> 26, 12=> 23}
which combined to form:
104, 970,795,887,142, 501,519,944,408, 859,713,937,438, 238,568,341,584, 154,526,205,632, 598,745,732,639, 647,278,021,173, 163,831,071,764, 896,225,159,592, 365,198,842,461, 226,688,733,330, 753,486,243,770, 471,723,522,422, 795,262,754,816 different possible settings.

100 million million million million million million million million million million million million million million million million million million million million million million million million million million million million. POSSIBLE. SETTING.

In scientific notation thats written as 1.04 x 10^(shit-ton).


And to compare the two, the Lorenz could be set to: 660,349, 198,000,000,000, 000,000,000,000, 000,000,000,000, 000,000,000,000, 000,000,000,000, 000,000,000,000, 000,000,000,000, 000,000,000,000, 000,000,000,000, 000,000,000,000, 000,000,000,000, 000,000,000,000 TIMES more combinations than the Enigma.

660,349 million million million million million million million million million million million million million million million million million million million million million million million million.  TIMES. MORE.

 Yeeeeesh.

So why haven’t we heard of Colossus?  Well, it was highly classified through the late 1970’s, long after ENIAC had been revealed to the public in 1946 and hailed as the first electronic ‘Giant Brain’.  It’s hard to unseat a 30 year-old reputation.  Furthermore, Churchill ordered all but two of the 11 machines destroyed shortly after V-E Day in 1945.  The remaining machines were used for training and research purposes before being scrapped a number of years later.

As far as I can tell the only reason one might prefer ENIAC over Colossus is that it was the first example of a Turing complete machine, whatever that mean.  You’ll have to look that one up for yourself; it went a bit over my head.  Then again Professor Benjamin Wells of the Departments of Computer Science and Mathematics, University of San Francisco, has showed that a Universal Turing Machine could run on ten Colossus computers and argues that this means that Colossus satisfies the definition of Turing completeness. Soon, there’s that?

Sources-
This isn’t a scholarly work so I’m not going to go back and cite anything, but here are a few places that were helpful:

http://billtuttememorial.org.uk/codebreaking/the-lorenz/
https://www.youtube.com/watch?v=9HH-asvLAj4
http://www.wired.com/2007/09/dead-media-be-1-17/
http://history-computer.com/ModernComputer/Electronic/Colossus.html
http://cryptomuseum.com/crypto/colossus/index.htm
