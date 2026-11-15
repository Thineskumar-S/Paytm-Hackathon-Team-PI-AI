# Paytm-Hackathon


InsureCX-Clarivio
Insurance policy PDFs, turned into short narrated whiteboard videos by a studio of AI specialists, approved by a human first.
Built as a prototype for the Paytm Hackathon. Clarity for every customer, at every moment.
  
The problem
Insurance policies are long, jargon-heavy documents that most customers never read. That causes confusion at purchase, at claim time and at renewal, and often leads to lapsed policies. A plain chatbot can explain a policy, but it can also guess or invent details, which is unacceptable in a regulated space.
The idea
Give it a policy PDF. It produces a short, narrated whiteboard video in Paytm colours explaining that policy. A person signs off before any customer sees it.
Think of it as a small video studio staffed by AI specialists, run by a manager agent.
Policy PDF  ->  AI studio  ->  Video  ->  Human approval
Meet the AI specialists
    


Role 


What it does 


Example from a test run     


Reader 


Reads the PDF and notes facts, each with its page number and exact quote 


"Sum insured: Rs. 5,00,000", page 2   


Fact-checker 


Confirms each quote is on the cited page and supports the fact 


Threw out a made-up "60 days" fact   


Writer 


Turns verified facts into a scene-by-scene script 


8 scenes   


3 reviewers 


Check legal promises, numbers and brand style 


Sent the script back for rewrites   


Narrator 


Records each scene's voice-over with Sarvam AI 


8 audio clips   


Illustrator 


Draws each scene as a whiteboard sketch with an image model 


8 drawings   


Video maker 


Animates the drawings being drawn, over the voice 


A 2-minute MP4    
A manager agent (the orchestrator) assigns work, collects results, and sends the script back for a rewrite if a reviewer rejects it.
One studio, a video for every moment
    


Stage 


Output     


Awareness 


A short "why this cover matters" video   


Understanding 


The full walkthrough of the policy   


Support 


"How to make a claim" help   


Renewal 


Personalised WhatsApp message and short video with renewal date and premium    
Also: a win-back version for lapsed policies.
Why trust it more than a plain chatbot
Quotes verified by code. A fact with no matching quote on its cited page is deleted automatically.
Numbers checked by code. Figures in the script must match the extracted policy facts.
Drafts only. No agent can send anything to a customer directly.
Strict ready gate. A job is marked ready only if all reviews pass and the video file actually exists.
Explaining, not guessing.
Project structure
.
├── python-service/   # Agents, their skill (instruction) files, and the API that runs them
├── src/              # Dashboard (currently on sample data, not yet wired to the agents)
├── AGENTS.md         # Full list of agents, their skills and their tools
└── README.md
Getting started
Replace the commands below with the ones that match your setup.
# 1. Clone
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>


# 2. Run the agent service
cd python-service
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env        # add your API keys (see below)
python main.py              # or: uvicorn app:app --reload


# 3. Run the dashboard
cd ..
npm install
npm run dev
Environment variables
    


Variable 


Purpose     


SARVAM_API_KEY 


Voice-over generation (Sarvam AI)   


<LLM_API_KEY> 


The language model that powers the agents   


<IMAGE_MODEL_API_KEY> 


The image model that draws each scene    
Status
Hackathon prototype.
[x] Agent pipeline: read, verify, write, review, narrate, illustrate, render
[x] Code-level quote and number verification
[x] Dashboard UI with sample data
[ ] Connect the dashboard to the agent service
[ ] Human approval flow in the dashboard
[ ] Personalised renewal messages over WhatsApp
Roadmap
Multi-language narration
More policy types and insurers
Analytics on which videos reduce claim and renewal drop-off
Contributing
Issues and pull requests are welcome. For larger changes, please open an issue first to discuss what you would like to change.
License
Add your license here, for example MIT.
Acknowledgements
Built for the Paytm Hackathon. Voice-overs by Sarvam AI.
