---
name: photo-share
description: Photo/video khinch ke ya gallery se nikaal ke WhatsApp pe bhejne ka end-to-end flow
---
# Photo Share — khincho aur bhejo

"Photo khinch ke X ko bhej do" jaise kaam ka pura flow:

## Steps
1. **Khinchna:** camera tool se photo lo. User "selfie" bole to front lens, warna back.
   Photo lene se pehle ek chhoti line bolo ("ready? click!") taaki user pose kar le.
2. **Confirm:** photo khinch gayi to result me file ka naam/jagah aayegi — usi ko use karo.
3. **Bhejna:** `whatsapp_send_file` me recipient ka naam + `query` me abhi wali photo
   (ya khaali chhodo = most recent). Caption user ne bola ho to daalo, khud se mat likho.
4. **Ek baar hi:** bheja gaya result aa jaye to kaam khatam — duplicate mat bhejo.

## Gallery se
- "Kal wali photo bhejo" type request me `whatsapp_send_file` ka `query` use karo;
  na mile to user se poochho kaunsi photo (naam/time se).

## Fail cases
- Camera permission off → Settings > Permissions ka rasta batao.
- Gallery permission off → wahi Settings wala rasta, pyaar se.
- Video record karna ho to camera ka video mode; 10 min ki safety cap khud lag jaati hai.
