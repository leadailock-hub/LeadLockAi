LeadLock AI

Never miss another lead.

LeadLock AI is a done-for-you lead capture & response system for contractors and
service businesses doing 400–20K jobs (roofers, plumbers, HVAC, remodelers,
electricians, med spas, lawyers). When a client signs up and pays the setup fee,
the entire system provisions itself automatically — landing page, Google Business
Profile, review automation, missed-call text-back, and an AI voice agent that
answers every call and books the job.

We don't sell leads. We make sure every lead a business already pays for
gets answered, booked, and followed up.

---

How It Works

1. Client signs up via Stripe checkout (setup fee, month 1 of subscription free)
2. Stripe webhook fires into n8n → client is logged, human-in-the-loop (Robert W.) is notified for approval
3. On approval, agents provision everything:
   - Landing page + on-page SEO (Cloudflare Pages / GHL)
   - Google Business Profile + Maps + Calendar sync
   - Review-request automation (fires when job is marked done)
   - AI voice call-back agent (Retell AI) — answers missed calls, collects info, books the job
   - Missed-call text-back + website AI agent (Pro/Top)
   - Blog with organic AI-updated SEO posts (Pro/Top)
4. Monthly billing starts day 31 via Stripe subscriptions

Pricing Tiers

	Basic — "Lock-In"	Pro — "Lock-Down"	Top — "Total Lock"	
Setup fee (one-time)	197	497	997	
Monthly	97	197	397	
Landing page + SEO	✅	✅	✅	
Domain + hosting	✅	✅	✅	
GBP + Maps + Calendar	✅	✅	✅	
Review automation	✅	✅	✅	
Website widget	Chatbot	AI agent	AI voice agent	
Missed-call text-back	—	✅	✅	
AI-written blog posts	—	1/mo	2/mo	
Referral program (3%/20%)	—	✅	✅	

Tech Stack

- n8n (self-hosted, Render free tier) — orchestration & the 5-agent workflows
- Stripe — checkout, subscriptions, webhooks (payouts to bank, no card needed)
- Retell AI / Vapi — voice agents (0.11–0.24/min)
- Twilio — SMS / missed-call text-back (A2P registered)
- GoHighLevel — CRM, sub-accounts, calendars (trial → 97/mo Starter)
- Google Workspace — Sheets (master client DB), Gmail, Business Profile, Calendar, Maps
- Cloudflare Pages / Vercel — client landing pages (free tier)

Repo Contents

- `index.html` — main marketing site (deploys to `leadlock.vercel.app`)
- `workflows/LeadLock_Demo_Workflow.json` — signup auto-provisioning demo
  (Stripe webhook → plan routing → master sheet → human approval →
  Retell agent + Twilio welcome text → Stripe 200 response)

Quick Start (Zero-Budget Launch)

1. Fork this repo → import into Vercel → live at `your-app.vercel.app`
2. Deploy n8n on Render free tier → import `workflows/LeadLock_Demo_Workflow.json`
3. Create Stripe products (Basic 197 / Pro 497 / Top 997 + monthly subscriptions with 31-day trial)
4. Point Stripe webhook to `https://your-n8n.onrender.com/webhook/stripe-signup`
5. Add credentials: Google Sheets, Gmail, Retell API key
6. Create a demo Retell agent → get a demo number → hand it to a contractor and say "call this"

The 5-Agent Crew

Agent	Job	
#1 Sign-Up/QC	Receives webhook, logs client, pings human for approval	
#2 Web & Local SEO	Landing page, GBP claim, Maps/Calendar sync, schema	
#3 Voice + SMS	Retell call-back agent, text-back, welcome texts	
#4 Content & Reviews	Blog posts, review requests after job complete	
#5 Referral & Billing	Affiliate tracking, 3%/20% payouts, failed-payment flags	

Human-in-the-loop: every signup is approved by a person before provisioning starts.

Roadmap

- A2P texting registration (funded by client #1 setup fee)
- Auto GBP verification flow
- Client dashboard (live call/booking metrics)
- Review-response AI (upsell, 59/mo)
- White-label tier for marketing agencies

---

Built to run almost on autopilot — 5 agents, 1 human (Robert W.), 75% gross margin.