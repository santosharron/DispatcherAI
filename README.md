# DispatcherAI
<Image src="/assets/image 17.png" alt="DispatcherAI Header" width={1200} height={400} />

## Summary

India’s national emergency helpline, **112**, receives millions of calls every year—many during natural disasters, peak city hours, and regional crises. Yet, the reality on the ground is that our emergency response systems are overstretched and outdated. Call centers face staff shortages, and responders often lack the critical real-time context needed to act swiftly.

**DispatcherAI** is our response to that problem.

Built by a team of technologists and AI engineers who deeply understand both systems and people, DispatcherAI is an intelligent triage and routing platform that transforms how emergency services are delivered in India. Powered by live transcription, NLP-based emergency classification, and geolocation inference, it provides real-time assistance during high-volume, high-stakes emergency scenarios.

DispatcherAI doesn't just take the call—it understands it.

---

## Vision

Our mission with DispatcherAI is simple but ambitious:  
**Make every second count during emergencies.**

DispatcherAI uses artificial intelligence not as a novelty, but as infrastructure—reducing dispatch lag, improving accuracy of response, and ensuring no critical call ever goes unheard.

---

## System Architecture

<Image src="/assets/Frame 28 (2).png" alt="DispatcherAI Header" width={1200} height={400} />

DispatcherAI is a real-time, multi-layered platform built on the foundation of low-latency APIs, serverless compute, and distributed AI inference. Calls are transcribed, analyzed, prioritized, and surfaced to responders—all within seconds.

---

## Core Technology Stack

### AssemblyAI – Live Transcription Engine

We selected [AssemblyAI Real-Time Transcription](https://www.assemblyai.com/docs/walkthroughs#realtime-streaming-transcription) to power our voice-to-text layer. Its low-latency streaming and high transcription accuracy make it ideal for parsing life-or-death voice interactions.

### Twilio – Voice Infrastructure

Using [Twilio's Programmable Voice API](https://www.twilio.com/docs/voice), DispatcherAI captures inbound calls directly from users. With support for WebSockets and robust call control, Twilio allows us to plug into the telephony layer without provisioning physical PBX hardware or dealing with complex SIP routing.

### HuggingFace – NLP Classification & Entity Recognition

We integrated multiple transformer models via [HuggingFace’s Inference API](https://huggingface.co/inference-api):

- **Named Entity Recognition (NER)**  
  - [`dbmdz/bert-large-cased-finetuned-conll03-english`](https://huggingface.co/dbmdz/bert-large-cased-finetuned-conll03-english) – for person and location detection  
  - [`Jean-Baptiste/roberta-large-ner-english`](https://huggingface.co/Jean-Baptiste/roberta-large-ner-english) – fallback, slower but higher accuracy  

- **Zero-Shot Classification**  
  - [`facebook/bart-large-mnli`](https://huggingface.co/facebook/bart-large-mnli) – categorizes calls into:
    - Medical Emergency
    - Fire Emergency
    - Traffic Accident
    - Crime in Progress
    - Other

### DigitalOcean + Cloudflare – Secure Hosting & Tunneling

Our backend runs on a [DigitalOcean](https://www.digitalocean.com/) VPS, securely exposed via [Cloudflare Zero Trust Tunnels](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/). This ensures encrypted, low-latency communication between Twilio, AssemblyAI, and our backend.

### Firebase – Realtime Sync

We use [Firebase Realtime Database](https://firebase.google.com/docs/database) for state management. All transcriptions and AI-inferred data are pushed to connected clients with millisecond-level sync, providing operators full visibility during ongoing calls.

---

## Frontend & Developer Experience

### Vite + React

[Vite](https://vitejs.dev/) and React were chosen for their speed and modularity. Combined, they enabled us to develop and test new features rapidly while keeping the UI performant and reactive.

### Chakra UI

We used [Chakra UI](https://chakra-ui.com/) for accessible, scalable component design. Chakra helped us maintain design consistency while enabling us to ship quickly.

### GitHub & Live Dev

Version control was maintained via Git and hosted on [GitHub](https://github.com/santosharron?tab=repositories). VS Code Live Share was used for real-time collaboration, enabling faster iteration and reduced coordination overhead during the hackathon.

---

## Call Simulation Scripts

To test DispatcherAI’s flow, dial **+1 (408) 617-9557** and use any of the following scripts:

### Armed Robbery
“Hello, my name is John. I'm on 2nd Street and I just witnessed an armed robbery. The suspect is still nearby. Please dispatch help immediately.”

###  Fire
“Hi, I'm Bob at 532 Geary Street. There's a fire in my building. I'm outside now but others may still be inside. Send assistance urgently.”

### Gunshot
“My name is Noah. I'm at 600 Carmel Ave. I heard a gunshot nearby. I'm safe, but someone could be in danger. Please respond quickly.”

### Car Accident
“Lucas here. I’m at 501 4th Ave. Someone just crashed into my car as I was exiting the garage. My child is with me and I’m unable to move my legs. I need help now.”

## The Road Ahead

DispatcherAI is more than a hackathon project—it's a prototype of the future of emergency dispatch in India. We believe this technology can help modernize the country's response system, providing critical infrastructure support where it is needed most.

As a student, I see DispatcherAI not just as a tool, but as a commitment:  
No call goes unheard. No life goes unseen. Every second counts.


