name: smart-share
description: Photo, file, link ya screen content ko sahi person aur app par safely share karne mein help karna
--------------------------------------------------------------------------------------------------------------

# Smart Share

User ko phone par available content ko correct person, app aur destination par safely share karne mein help karo.

Goal hai:

**Find → Identify → Verify → Confirm → Share**

Existing app-specific sharing capabilities ko reuse karo. Is skill ka purpose un capabilities ko ek simple, context-aware sharing workflow mein combine karna hai.

## 1. Kab use karna hai

Is skill ko tab use karo jab user bole:

* "Ye photo Rahul ko bhejo"
* "Ye file Mom ko share karo"
* "Ye PDF WhatsApp par bhejni hai"
* "Is link ko share karo"
* "Ye screenshot bhej do"
* "Ye document email kar do"
* "Ye kisi ko forward karna hai"

Agar user sirf WhatsApp-specific task de raha hai aur existing WhatsApp capability directly handle kar sakti hai, unnecessary duplication mat karo.

## 2. Content identify karo

Pehle determine karo ki user kya share karna chahta hai:

* photo
* video
* document
* PDF
* link
* screenshot
* selected file
* currently visible/relevant content

Agar multiple possible files hain, clarification poochho.

Example:

"Sir, do PDF files hain. Kaunsi bhejni hai?"

File ko guess mat karo.

## 3. Recipient identify karo

Recipient ko reliably identify karo.

Agar same naam ke multiple contacts hain:

"Sir, Rahul naam ke 2 contacts hain. Rahul Kumar ya Rahul Sharma?"

Recipient ko guess mat karo.

## 4. App identify karo

Agar user ne app specify ki hai, usi app ko use karo.

Example:

"WhatsApp par bhejo."

Agar app unspecified hai aur multiple reasonable options hain, clarification poochho.

Example:

"WhatsApp ya email par bhejna hai?"

## 5. Context samjho

User agar bole:

"Ye report Rahul ko bhej do."

to relevant current file/content aur recent context use karke identify karne ki koshish karo.

Lekin important content ko blindly select mat karo.

Agar ambiguity hai, short clarification poochho.

## 6. Sensitive ya important content

Important documents, personal information ya potentially sensitive content ko share karne se pehle destination verify karo.

Example:

"Sir, `medical-report.pdf` Rahul Kumar ko WhatsApp par bhejna hai. Confirm?"

## 7. Confirmation

External sharing ko automatically perform mat karo jab recipient, app ya content ambiguous ho.

Important or sensitive sharing ke case mein concise confirmation lo.

Confirmation mein preferably include karo:

* content
* recipient
* app

Example:

"`Final Report.pdf` Rahul Kumar ko WhatsApp par bhejna hai. Confirm?"

## 8. Execute

User ke clear confirmation/request ke baad available phone sharing capability use karke content share karo.

Agar user ne clearly complete command diya hai aur ambiguity nahi hai, unnecessary repeated confirmation mat maango.

Example:

"WhatsApp par ye photo Mom ko bhejo."

Agar content, recipient aur app clear hain, task execute karo.

## 9. Failure handling

Agar sharing fail ho:

* failure ko clearly batao
* reason available ho to explain karo
* practical next step suggest karo

Example:

"Sir, file share nahi ho paayi. WhatsApp open hua lekin attachment select nahi hua. Dobara try karun?"

False success claim mat karo.

## 10. Safety

Kabhi bhi:

* wrong recipient guess mat karo
* private content ko random contact ko share mat karo
* user ki permission ke bina external content share mat karo
* sensitive content ko unnecessarily expose mat karo

## 11. Concise interaction

Internal steps explain mat karo.

Instead of:

"File found. Contact found. WhatsApp opened. Share intent created."

bolo:

"`Report.pdf` Rahul Kumar ko WhatsApp par bhejna hai. Confirm?"

## 12. Goal

Smart Share ka objective hai:

**Right content → Right person → Right app → Safe sharing**

Sharing ko fast rakho, lekin recipient aur content ki correctness sacrifice mat karo.
