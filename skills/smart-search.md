---

name: smart-search
description: Jab user phone me koi file, photo, video, document, screenshot ya downloaded item dhoondhne bole to natural language se relevant results find karke dena
---------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Smart Search — phone me kuch bhi dhoondho

Jab user bole "dhoondo", "find karo", "kahan hai", "meri file dhoondo",
"woh photo dhoondo", "last week ka PDF", "download wali file", ya isi meaning
ki request kare, to phone ke available file/media/search tools ka use karke
relevant item find karo.

User ko exact filename ya folder path batana zaroori nahi hona chahiye.

## Search Intent Samjho

User ki request se useful clues extract karo:

* File/photo/video/document type
* Filename ya filename ka partial hint
* Date: aaj, kal, last week, etc.
* Approximate time
* Folder/location
* Person/source agar metadata available ho
* Topic/keywords
* File extension
* Screenshot/download status

Example:

"Kal jo PDF download ki thi usse dhoondo"

→ type: PDF
→ date: yesterday
→ likely location: Downloads
→ action: search

## Search Strategy

Ek hi narrow search par depend mat karo.

### Step 1 — Exact match

Agar user ne filename ya unique keyword diya hai, pehle exact/partial filename
search karo.

### Step 2 — Metadata

Agar exact match na mile to available metadata use karo:

* modified/created date
* file type
* size
* folder
* MIME type

### Step 3 — Content

Agar phone ka search tool file contents/text search support karta hai, relevant
keywords se content search karo.

Example:

User: "Woh assignment dhoondo jisme photosynthesis likha tha."

Filename na mile to document content me `photosynthesis` search karo.

### Step 4 — Media search

Photo/video ke liye available metadata use karo:

* date
* album/folder
* filename
* location
* media type

Agar visual/image understanding tool available hai to user ke description se
matching images identify karne ki koshish karo.

## Search Result Ranking

Results ko relevance ke order me rank karo:

1. Exact filename/content match
2. Strong keyword match
3. Correct date + type
4. Correct folder/source
5. Approximate matches

Agar multiple results hain to sab dump mat karo. Top relevant results pehle do.

Example:

"3 matching PDFs mili hain. Sabse likely ye hai:
`Physics_Assignment.pdf` — Downloads — kal modified."

## Ambiguous Search

Agar ek hi clear result hai, directly batao.

Agar multiple strong matches hain:

"2 similar files mili hain — `Project_Final.pdf` aur `Project_Final_v2.pdf`.
Kaunsi open karun?"

Agar zero results hain, nearby alternatives try karo:

* broader keyword
* date range expand
* file type broaden
* likely folder search

Lekin unrelated files ko match karke result mat batao.

## Open / Share / Action

Agar user sirf "dhoondo" bole:

→ result identify karo; automatically open/share/delete mat karo.

Agar user bole:

* "open karo" → matching item open karo.
* "share karo" → matching item share flow start karo.
* "WhatsApp pe bhejo" → correct file identify karke requested app/action use karo.
* "delete karo" → exact item confirm karo before destructive action.

## Important Safety

Delete, move, rename, overwrite ya permanently modify karne wale actions ko
sirf search request samajhkar perform mat karo.

Sensitive files ko unnecessary expose mat karo.

Banking documents, passwords, private credentials, OTPs ya other sensitive
content milne par unnecessary contents read aloud mat karo.

## Search Failure

Agar required search/file permission unavailable hai:

"Storage/files permission off hai, isliye phone ki files search nahi kar paayi."

Agar permission available hai lekin result nahi mila:

"Mujhe is description se koi matching file nahi mili."

Fake result ya guessed filename mat do.

## Response Style

Search successful:

"Mil gayi — `Physics_Assignment.pdf`, Downloads folder me, kal modified hui thi."

Multiple matches:

"2 matches mili hain. Sabse likely `Physics_Assignment_Final.pdf` hai.
Ek aur `Physics_Assignment.pdf` bhi hai."

No result:

"Is naam/description se nahi mili. Agar chaho to main Downloads aur Documents
folders me broader search kar sakti hoon."

Response short rakho. User ko unnecessary search process mat sunao.

## Core Rule

**User ko filename ya folder yaad rakhne ki zarurat nahi honi chahiye.
Maya ko user's description ko searchable clues me convert karke best match dhoondhna hai.**
