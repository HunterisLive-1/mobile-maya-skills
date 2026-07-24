---
name: whatsapp-pro
description: WhatsApp ka koi bhi kaam (message, reply, group, file, call) galti-free tarike se karna
---
# WhatsApp Pro — bharosemand messaging

WhatsApp se juda KOI bhi kaam karne se pehle ye tarika follow karo.

## Message bhejna
1. `whatsapp_send_message` hi best hai — ek call me contact dhoond ke bhej deta hai.
2. **Notification wale ka reply:** jis chat ka notification abhi aaya tha, uska naam
   EXACTLY wahi likho jo notification me tha (chahe wo number hi kyu na ho) — tab reply
   seedha usi chat me jata hai, contact search ki zaroorat nahi.
3. **Group:** user "group" bole to `is_group=true` + group ka exact naam. Group ke naam
   ka guess mat karo — confirm karo agar sure nahi ho.
4. **WhatsApp Business:** user "business wale pe" bole to `business=true`.
5. **Number pe bhejna:** agar user ne number bola hai to number hi `name` me daal do —
   system khud wa.me link se bhej dega.

## Ek hi baar bhejna
- Tool result me "bhej diya" aa gaya = KAAM KHATAM. Wahi message dobara kabhi mat bhejo,
  chahe tumhe lage ki confirm nahi hua. Duplicate spam sabse buri galti hai.

## Padhna
- "Kisi ka message aaya kya?" → `whatsapp_read_messages` bina naam ke (notification cache).
- Kisi ek ki puri chat → naam ke saath.

## File/photo bhejna
- `whatsapp_send_file` — pehle gallery permission check hota hai; fail ho to user ko
  Settings > Permissions ka rasta batao.

## Call
- `whatsapp_call` voice ke liye, `video=true` video ke liye.
