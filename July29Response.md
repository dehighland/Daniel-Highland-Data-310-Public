# July 29th, 2020 Lecture Response
---
## Sarcasm Classifier

**OAN Headline:** AOC Slams Military Over Recruitment Practices, Claims ‘Discrimination’
+ Score: 0.3852086

**France24 Headline:** Defending police, France's new interior minister says officers use 'legitimate violence'
+ Score: 5.3136388e-11

**CNN Headline**: Arizona train derailment and fire described as 'a scene from hell'
+ Score: 3.4732878e-08

**Jacobin Headline:** Billionaires Want to Reopen Schools Amid a Pandemic. They Might Unleash a Teacher Strike Wave.
+ Score: 4.6661057e-08

**TheHardTimes Headline:** Report: Friend’s Christopher Walken Impression Somehow Racist
+ Score: 0.99999964

**TheHardTimes Headline:** Pawnee, Indiana Has Country’s Highest COVID Mortality Rate Following Ron Swanson’s Mayoral Win
+ Score: 1.8132046e-07

**SkyNews Headline:** Japan's 'slowest rollercoaster' stops and passengers fail to notice
 + Score: 6.302623e-07

### **Analysis:**
The Sarcasm Detector was largely accurate. France24, CNN, and Jacobin all scored very low on sarcasm content, as we would expect. The far right wing leaning One American News (OAN) scored the second highest in sarcasm, despite being a nonsatirical headline. Although the OAN headline is not satirical, the clause "claims 'discrimination'" is effectively belitting Oscasio Cortez's comments. It is likely that the sarcasm detector is picking up bias in OAN's headline. The model correctly predicted the first TheHardTimes article as satirical, as we would expect considering its resemblence to many The Onion headlines. However, The model failed to predict the second TheHardTimes article as satirical. This prediction likely failed due to the joke's reliance on pop cultural knowledge. Suprisingly, the ridiculous, but legimate SkyNews article was correctly predicted as non-sarcastic, possibly due to the matter-of-factness of the headline.

---
## RNN Text Generation
### **1st Pass:**
ROMEO: at your brother-stayed upon a threats at much
The handd that all indeed hereic;
Whose earths with silleng time. Hursead in his peace.
I am a witness roturn and stay themse:
Non to your recomon opinion!
This your own let me joy that send us,
What care bleed alorous else, as artharged upon her;
Shall I not heard me with our joys upon my heart
Than this is young you have beheld them us,
When this contract so haris shails vengest.

DUKE OF YORK:
That mortal redous here in Ressabelleart.

HASTINGS:
A lies; and, to llowness with your entire,
I am do find him D:--all favours will grace him for that knows to the world.

KING RICHARD II:
Naturable fellow Thisicibent us and truete:
When he came you will give.

Second Lady:
Upon revenge, this force in others.

ANTOSIO:
Now! by the parties lla end.
Hark, on.

Justion:
Nearth that all upon you.

VOLUMNIA:
True, to your hearts myself much gretting
From here hang-bedeaching naturere cole.
Thy stag and then five justice, gentle out,
And us with allegi

### **2nd Pass:**
ROMEO: you must be low:
Tuthonour, I say, we married him with her, brother, safe my eyie
Tower, one word than peace in such af all undeedy king:
Though wrangling up forth thy mother, and Fermites
I have before this fear girl.

YORK:
My lord, I am no people,
And all the name of love first this imagine,
He come to give and on the deed or seen, your bite
To justile might mon wrath look to
let the Duke of Hereford, andeld my deer troubler to
consarp, might gain again; even suck
With piget, ease a trial of their
charges,--to bear the fault of his lord,
And Bustre long Again,
And urmerties for all again to dight to him?

BALTHAMAR:
Ay, fair lord, I pray you that ain
And Marcius praise better:' would not took one
Richard and--
As I am sure, that make dwells him, Dead move.

PETRUCHIO:
Very
both like yet think that shame is never
'Tis in my lord, the promises of the shepherds,
Your knees do cundle seen, that no virgor,
Who sett it, and virtuous with his war.
Heaven here receive't is ermodies, and was

### **Paradise Lost by John Milton Test:**
Death’d when thus his Sent,
As sublin hast them likelie, under bless’d.
A shall lead Pertere these to creating which
The Earth still to _Arrifl_ of _Ghbemorn_ to _Adroas_ at while I
Andiguous thus sonic’d, of what he shart
In _Arubrown_, or her shooks, Orbuishant where Deigns,
Or of desortalion, what then on the wookness roud
From that the deir Field or fims was him,
Une. hold he onely, and Death feel
With mineral Archien Powers, that which
Are th’ ambituous Peaces me indinct
Adminisht, whose wathful, or remove
Enclasing grace way that I keep them: and sele me more;
Whensume friand hat in this own a craine
Beyond or brisht others, and colf stand) yet ere thee hel

Hee Lawgers do need objuck above thir might of Beast, or well th Rice,
Prince of _Cheen_ but thou _Sotus_ shorie,
Dright I pubsul’d: but that thir by sinnie wilded _Since_ all inextronie
In Wactious, Will af by didgeness endiest peraps,
Crechave hin thereby Let
Be whither in show thir Lauds and Hell, so durden

### **Analysis:**
![](https://www.tensorflow.org/tutorials/text/images/text_generation_sampling.png)

The model takes a selection of characters (for instance an incomplete sentence) and tries to predict the next character. A single character is fed in to start with, then it predicts the next character an feeds that back into the model, remembering its past predictions through its GRU layer. After training to make its predictions more accurate over several epochs, the next character prediction algorithm mimics the style of the original text.

---
## Neural Machine Translation

