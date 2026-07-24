---
name: chatgpt-image-gen
description: Jab user "image bana do / AI se photo generate karo" bole to ChatGPT app se sub-agent se image banwa ke download karna
---
# ChatGPT Image Gen — AI se photo banwana (sub-agent se)

Jab user bole "ek image bana do", "AI se photo generate karo", "ChatGPT se picture banwao"
jaisa kuch — to ye kaam **khud inline mat karo**. Ye lamba, screen-dekhne wala kaam hai
aur beech me 30–40 sec wait hota hai — is dauran tum block ho jaogi aur user se baat nahi
kar paogi. Isliye ye pura UI flow ek **sub-agent** ko saunp do; tum sirf prompt taiyaar
karo, kaam delegate karo, aur result pe user ko batao.

## Step 0 — Prompt taiyaar karo (ye TUM karti ho)
User ne jo choti si baat boli (jaise "ek billi jo chai pi rahi ho") usko ek **detailed
English prompt** me badlo — subject, style, background, lighting, mood sab daalo.
- Example: user "sunset wali bike" → prompt: *"A cinematic photo of a sports bike parked
  on a coastal road at sunset, golden hour lighting, dramatic sky, high detail, 4k."*
- User ne khud detail di ho to usko izzat do, apni marzi zyada mat thopo.
- Prompt English me hi banao (ChatGPT English me best image deta hai).

## Step 1 — Sub-agent ko kaam do
Sub-agent chalane wale tool se ek naya agent spawn karo aur usko YE poora kaam saunp do
(prompt ki jagah Step 0 wala detailed prompt daal do):

> "ChatGPT app kholo → new chat kholo → input box pe tap karke ye prompt type karo:
> '<DETAILED PROMPT>' → send karo → image ban-ne ka wait karo (loading khatam hone tak,
> ~40 sec) → image pe tap karo → download/Save button pe tap karo → confirm karo ki gallery
> me save ho gayi. Har step pe screen dekh ke tap karna, andhe me nahi. Ho jaye to batao
> 'saved', kahin atko to jahaan atke wahi batao."

- Ek hi image ke liye ek hi sub-agent — duplicate spawn mat karo.
- Tum khud ChatGPT app ke andar tap/type mat karo; wo sub-agent ka kaam hai.

## Step 2 — Wait ke dauran
- Sub-agent ko chalne do. User ko ek line bol do: **"Image ban rahi hai, bas thodi der 🎨"**.
- Is dauran tum free ho — user kuch aur poochhe to normal jawab de sakti ho. Sub-agent ka
  result aane ka intezaar karo, baar-baar status mat poochho.

## Step 3 — Result pe user ko batao
- Sub-agent "saved" bole → ek pyaari line: **"Ho gaya! Image ban gayi aur gallery me save
  kar di 📸"**.
- User "WhatsApp pe bhej do" bole to `photo-share` / `whatsapp_send_file` se most-recent
  photo bhej do — dobara mat banwao.

## Fail cases (sub-agent jo bataye uske hisaab se)
- Login/onboarding screen ya app hi nahi → "ChatGPT app install/login karna padega pehle."
- Image nahi bani / ChatGPT ne text me jawab diya → sub-agent ko ek baar clear prompt
  *"Please generate an image of ..."* ke saath retry karne bolo.
- Free limit khatam / "you've hit your limit" → user ko seedha batao, jhooth mat bolo.
- Download button na mile → sub-agent long-press "Save image" / screenshot try kare;
  phir bhi na ho to user ko bolo "image screen pe hai, save nahi ho paayi".
- Slow ho to sub-agent tap-tap na kare — ek hi image do baar ban ke gadbad ho jati hai.
