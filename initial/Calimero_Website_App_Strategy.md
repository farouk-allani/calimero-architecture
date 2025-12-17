CALIMERO WEBSITE & APP STRATEGY

` `**CALIMERO**

**WEBSITE & APP STRATEGY**

**Subdomain Model + Kids-Only AI Companion App**

DEV Team



**PART 1: WEBSITE STRATEGY**
#
# **1. THE CORE CHALLENGE**

Calimero must serve TWO completely different audiences with opposite needs and legal requirements.

|**🧒 KIDS (Ages 4-12)**|**🧑 ADULTS (Ages 18-50)**|
| :-: | :-: |
|Bright, playful, animated design|Sleek, minimal, streetwear aesthetic|
|Games, videos, activities|Shop, drops, memes, culture|
|COPPA compliance, no data collection|E-commerce, accounts, purchase history|
|Safe AI chat (moderated)|Full AI features, character generator|
#
# **2. SOLUTION: SUBDOMAIN MODEL (LEGO STYLE)**
Two separate sites on subdomains with a pop-up selector on first visit. Just like LEGO uses kids.lego.com and lego.com.

|**🧒 kids.calimero.com**|**🧑 calimero.com**|
| :-: | :-: |
|Dedicated kids experience|Main adult/culture site|
|100% COPPA compliant|Full e-commerce & features|
|No cookies, no tracking|Accounts, analytics, personalization|

**Pop-up Gate (First Visit)**

When users visit calimero.com for the first time, a friendly pop-up appears:

|<p>**👋 Welcome to Calimero!**</p><p>Choose your experience:</p><p>**[ 🎮 I'M HERE TO PLAY ]     [ 🛒 I'M HERE TO SHOP ]**</p>|
| :-: |

**How It Works**

- **"I'm here to play"** → Redirects to kids.calimero.com
- **"I'm here to shop"** → Stays on calimero.com (adult site)
- Cookie remembers choice for 30 days (adult site only)
- Kids site has link to adult site in footer (for parents)
- Adult site has prominent "Kids Zone" button in header
#
# **3. KIDS SITE: kids.calimero.com**
A completely separate, child-safe environment with zero tracking or data collection.

|**Section**|**Content**|
| :-: | :-: |
|🏠 HOME|Animated landing, featured episode, game of the day|
|🎬 WATCH|Episodes, clips, AI shorts, mood-based recommendations|
|🎮 PLAY|Coloring, memory match, puzzles, dress-up, quiz, story builder|
|👋 FRIENDS|Character profiles with animations, fun facts, voice clips|
|💬 TALK|AI companion chat (text only, safe, moderated, time-limited)|
|📱 APP|Download mobile app (voice AI unlocked!)|
|👨‍👩‍👧 PARENTS|Parental dashboard (PIN protected), time controls, feature toggles|

**Design System**

- **Colors:** Yellow (#FCD34D), Green (#22C55E), soft pastels
- **Typography:** Rounded fonts (Nunito, Baloo), large text (18px min)
- **UI:** Large touch targets (48px+), bouncy animations, sound effects
- **Navigation:** Icon-heavy, minimal text, breadcrumbs for parents
#
# **4. ADULT and KIDS SITE: calimero.com**
The main site for nostalgia seekers, collectors, and culture fans.

|**Section**|**Content**|
| :-: | :-: |
|🏠 HOME|Hero banner, latest drops, featured products, culture highlights|
|🛒 SHOP|All merchandise, filters by category/size/price, size guides|
|🔥 DROPS|Upcoming releases, countdown timers, notification signup|
|🎭 CULTURE|Memes, social feed, community highlights, viral content|
|📺 NOSTALGIA|History, classic episodes, "remember when" content|
|🎨 CREATE|AI character generator, meme maker, fan art gallery|
|👤 ACCOUNT|Login, orders, wishlist, drop notifications|

**Design System**

- **Colors:** Black, white, yellow accents (#FCD34D)
- **Typography:** Sharp sans-serif (Inter, Helvetica Neue)
- **UI:** Minimal, clean, Supreme/KITH/END aesthetic
- **Navigation:** Text-based, sticky header, mega menu for shop

**E-commerce Features**

- Quick Checkout (Apple Pay, Google Pay, PayPal)
- Multi-Currency (EUR, USD, GBP, JPY)
- Global shipping with tracking
- Wishlist with restock alerts
- Size guides and fit recommendations
#
# **5. TECHNICAL ARCHITECTURE**
**Shared Infrastructure**

- **Framework:** Next.js 14 (separate builds per subdomain)
- **CMS:** Sanity or Contentful (shared content, filtered by site)
- **Hosting:** Vercel (automatic subdomain routing)
- **CDN:** Cloudflare (edge caching, DDoS protection)

**Kids Site Specific**

- **Analytics:** Plausible (cookieless, COPPA compliant)
- **AI Chat:** LLM API with strict safety prompts
- **Video:** Mux with parental controls
- **No cookies, no localStorage, no tracking pixels**

**Adult Site Specific**

- **E-commerce:** Shopify Storefront API or Medusa.js
- **Auth:** NextAuth.js with social logins
- **Analytics:** Google Analytics 4, Meta Pixel
- **AI Generator:** LLM API + image generation
#
# **6. COPPA COMPLIANCE (KIDS SITE)**

|**Requirement**|**Implementation**|
| :-: | :-: |
|No Account Creation|All features accessible without login or registration|
|No Personal Data|No forms asking for name, email, age, location|
|No Cookies|Cookieless analytics only (Plausible)|
|No Chat Storage|AI conversations never saved, fresh each session|
|Parental Gate|PIN-protected parental dashboard for controls|
|Safe AI|Multi-layer content moderation, topic restrictions|
#
# **7. LANGUAGES & TIMELINE**
**Priority Languages**

- **P1 Launch:** Italian, French, English
- **P2 :** Japanese, German, Spanish

**URL Structure**

- **Kids:** kids.calimero.com/it, kids.calimero.com/fr, kids.calimero.com/en
- **Adult:** calimero.com/it, calimero.com/fr, calimero.com/en

**Development Timeline** 

- **Phase 1 :** Foundation - Next.js, both site structures, pop-up gate
- **Phase 2:** Kids Site MVP - homepage, videos, games, AI chat
- **Phase 3:** Adult Site MVP - e-commerce, drops, accounts, AI generator
- **Phase 4:** Polish, translations, COPPA audit, launch



**PART 2: KIDS-ONLY MOBILE APP**

# **8. APP OVERVIEW**
A dedicated kids app where AI companions come alive with VOICE. This is the premium kids experience - no adult features, 100% child-safe.

|**🎯 Core Purpose**|**🛡️ Safety First**|
| :-: | :-: |
|Voice conversations with Calimero & friends|Full COPPA compliance|
|Interactive stories & games|No data collection whatsoever|
|Watch episodes offline|Parental controls with PIN|
|Learn with AI tutoring|Time limits enforced|

**Platform Support**

- **iOS:** iPhone & iPad (iOS 15+)
- **Android:** Phones & tablets (Android 10+)
- **Framework:** Flutter (single codebase, native performance)
#
# **9. AI COMPANION SYSTEM**
**Technology Stack**

- **Language Model:** LLM API with child-safe system prompts
- **Voice Synthesis:** ElevenLabs - custom trained voice per character
- **Speech-to-Text:** Whisper API (or native device)
- **Animation:** Rive for real-time character lip-sync
- **Safety Layer:** Multi-stage content moderation

**Conversation Flow**

1. Child speaks into microphone
1. Whisper converts speech to text
1. Text sent to LLM with character's system prompt
1. Response filtered through safety layer
1. ElevenLabs converts text to character's voice
1. Character animates with lip-sync while speaking
1. Conversation NOT stored (privacy)

( AssemblyAI or Eleven labs + Together AI ) 
#
# **10. THE 5 AI COMPANIONS**

|**Character**|**Personality**|**Voice**|**Best For**|
| :-: | :-: | :-: | :-: |
|🐣 Calimero|Empathetic, "It's an injustice!"|Warm, Italian accent|Emotional support|
|🐥 Priscilla|Gentle, patient, nurturing|Soft, melodic|Bedtime, calming|
|🦆 Valeriano|Bold, adventurous|Energetic, excited|Stories, imagination|
|🐦 Pierrot|Playful, silly, jokes|Bouncy, playful|Entertainment|
|🐔 Rosita|Smart, curious, facts|Clear, articulate|Learning, homework|

**Example Interactions**

- **Calimero:** "I feel sad today" → Validates feelings, offers comfort
- **Priscilla:** "Tell me a bedtime story" → Soft, calming narrative
- **Valeriano:** "Let's go on an adventure!" → Interactive story creation
- **Pierrot:** "Make me laugh!" → Age-appropriate jokes and silliness
- **Rosita:** "Why is the sky blue?" → Simple, educational explanation
#
# **11. SAFETY ARCHITECTURE (CRITICAL)**

|**Safety Layer**|**Implementation**|
| :-: | :-: |
|No Personal Data|AI NEVER asks for name, age, location, school, family, photos|
|Topic Boundaries|Only: show, friendship, hobbies, learning, imagination, feelings|
|No Chat History|Conversations NEVER stored. Each session starts completely fresh.|
|Time Limits|Parent sets daily limit. Auto-ends: "Time to play outside! See you later!"|
|Anti-Isolation|Regularly suggests: "Have you told your mom/dad about this?"|
|Emergency Response|If harm/danger mentioned: "Please talk to a grown-up right away"|
|Input Filtering|Screens child's speech for inappropriate content before processing|
|Output Filtering|Double-checks AI response before speaking it aloud|
#
# **12. APP FEATURES**
**🎤 TALK - Voice AI Chat**

- Choose from 5 characters
- Tap-to-talk or always-listening mode (parent choice)
- Visual feedback: character reacts while listening
- Session time limit with friendly warnings

**📖 STORIES - Interactive Bedtime**

- AI generates personalized stories
- Child makes choices: "Should Calimero go left or right?"
- Priscilla narrates in soothing voice
- Sleep timer with gentle fade-out

**🎮 PLAY - Games**

- Memory match, puzzles, coloring, dress-up
- Rosita hosts quiz games with voice feedback
- Valeriano leads adventure games
- Progress badges (no accounts - stored locally)

**📺 WATCH - Episodes**

- Full episodes and clips
- Offline download (parent permission required)
- AI-generated daily shorts
- "Watch with me" - characters comment on episodes

**📚 LEARN - Educational**

- Rosita helps with homework questions
- Fun facts about animals, science, nature
- Language learning basics
- Math games with voice guidance
#
#
# **13. PARENTAL CONTROLS**
All controls accessed via PIN-protected dashboard. Syncs with kids.calimero.com parental dashboard.

|**Control**|**Options**|
| :-: | :-: |
|Daily Time Limit|30 min / 1 hour / 2 hours / Unlimited|
|Voice Chat Toggle|Enable / Disable voice conversations entirely|
|Download Permission|Allow / Block offline episode downloads|
|Bedtime Mode|Set quiet hours (only Priscilla available, stories only)|
|Activity Summary|Weekly email: time spent, features used (no chat content)|
|Character Restrictions|Enable/disable specific characters|
# **14. MONETIZATION**

|**Tier**|**Price**|**Features**|
| :-: | :-: | :-: |
|Free|€0|5 voice chats/day, basic games, episode clips|
|Calimero Premium|€4.99/mo|Unlimited voice AI, all games, full episodes, offline mode|
|Annual Plan|€39.99/yr|Same as Premium (2 months free)|

**COPPA-Compliant Purchases**

- All purchases require parental account verification
- No direct in-app purchases accessible to children
- Parent dashboard manages subscription
- Family Sharing supported (iOS & Android)
#
# **15. APP DEVELOPMENT TIMELINE**

|**Month**|**Deliverables**|
| :-: | :-: |
|1-2|Flutter setup, UI framework, parental controls, PIN system|
|3-4|AI text chat integration, character animations (Rive), safety layer v1|
|5-6|Voice AI (ElevenLabs + Whisper), lip-sync, safety testing|
|7-8|Games (memory, puzzles, quiz), video player, offline mode|
|9-10|Interactive stories, learning features, bedtime mode|
|11-12|Full testing, COPPA audit, App Store/Play Store submission, launch 🚀|
#
# **16. SUMMARY**
**Website Strategy**

- **Two Sites:** kids.calimero.com + calimero.com (LEGO model)
- **Pop-up Gate:** Friendly choice on first visit
- **Kids Site:** Games, videos, safe AI chat, zero tracking
- **Adult Site:** Shop, drops, culture, AI generator, full e-commerce

**Kids App Strategy**

- **Focus:** 100% kids-only, voice AI companions
- **5 Characters:** Calimero, Priscilla, Valeriano, Pierrot, Rosita
- **Safety:** Multi-layer protection, no data, COPPA compliant
- **Revenue:** Freemium €4.99/mo with parental verification

**Next Steps**

1. Approve this strategy
1. Begin website Phase 1 (both subdomains)
1. Start voice training for 5 AI characters
1. Begin app development (Month 3)
1. Legal review for COPPA compliance

***One Brand. Two Sites. Five Friends. Safe & Fun.***

*"It is an injustice, it is!"*

— END —
Page  | Dar Blockchain
