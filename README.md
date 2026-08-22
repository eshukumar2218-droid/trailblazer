# Trailblazer — PWABuilder se Play Store tak

Is folder mein aapki app PWA-ready ban chuki hai:
- `index.html` — aapki app
- `manifest.json` — app ka naam, icon, colors define karta hai
- `sw.js` — service worker (PWA ke liye zaroori)
- `icons/` — 3 placeholder icons (192px, 512px, maskable) — chaho to apna
  khud ka logo bana kar inhi filenames se replace kar do

## Step 1 — Files ko host karo (zaroori hai)
PWABuilder ek **live URL** maangta hai, local files nahi. Free hosting:
- **GitHub Pages** (free, sabse aasan) — github.com par account banao,
  naya repo banao, yeh saari files upload karo, Settings → Pages → Enable
- Ya **Netlify** / **Vercel** — free tier, seedha yeh folder drag-drop karke
  deploy ho jata hai (netlify.com → "Deploy manually")

Deploy hone ke baad aapko ek URL milega jaisे:
`https://your-app.netlify.app` ya `https://username.github.io/trailblazer`

## Step 2 — PWABuilder par jao
1. https://www.pwabuilder.com kholo
2. Apna live URL daalo (Step 1 wala), "Start" click karo
3. Yeh automatically manifest + service worker detect karega, ek score dega
4. "Package For Stores" par click karo
5. **Android** select karo
6. Package name do: `com.trailblazer.walking` (ya apna koi bhi unique naam)
7. "Generate Package" — yeh aapko `.aab` file dega (Play Store ke liye ready)

## Step 3 — Play Console par upload
1. https://play.google.com/console — $25 one-time fee (agar pehle nahi diya)
2. "Create app" → naam, category, etc bharo
3. Store listing: screenshots, description, **Privacy Policy URL** (zaroori)
4. Production → Create release → `.aab` file upload karo
5. Content rating form bharo → Submit for review (1-7 din)

## Zaroori baatein
- **Privacy Policy**: kyunki app login/data store karti hai, ek Privacy
  Policy URL chahiye hoga. Free mein banega — termly.io ya
  freeprivacypolicy.com se generate karo, GitHub Pages par hi host kar do.
- **AI Coach feature**: is app ka ek hissa seedha Anthropic API ko call
  karta hai bina API key ke — yeh sirf Claude.ai ke andar kaam karta tha.
  Live URL par yeh call **fail hogi**. Play Store par publish karne se
  pehle: ya to yeh feature hata do (coach button/section), ya apna khud
  ka backend banao jo API key ke saath call kare.
- **Icons abhi placeholder hain** — `icons/icon-192.png`, `icons/icon-512.png`,
  `icons/icon-512-maskable.png` ko apne khud ke design se replace kar sakte ho
  (same filename, same size rakhna).
- Ek baar app publish hone ke baad **package name badal nahi sakte**, isliye
  wahi naam soch ke do jo permanent rakhna hai
