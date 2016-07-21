# Intent

"I want to __work__ from home"  (mean VPN)
	- classification

---

# Start form classification

__Weather -> Eddie go to work__
Sunny -> go  
Sunny -> go  
Sunny -> go  
Sunny -> not go  
rain -> not go  
rain -> not go  

##### Today is a sunny day, do Eddie go to work?

---

# Mining

Sunny day 75% go to work, 25% not go to work.
Rain day 100% not go to work.

---

# NLP - Natural Language Process

"I want to work from home" -> I, want, to, work, from, home

Verbs -> Meaning

---

# component
	- protal
	- nginx
	- docker UI
	- Jankins - Daily jobs
		- sync the conversion
	- REST API
	- NER - Named Entity Recognition

---

# NER - Name entity Recognition

- who is __Austin Lee__?
	- find out the name
- my phone: 0933-641554
	- find out the phone number

- Technique
	- Regex
	- CRF - condition random fields
		- extract from self info, following info and aformentioned info

---

# A-Hong

- INPUT -> REST API -> pattern-based chatbot -> IFTTT  
	- (REST API) <-> NER
	- (REST API) <-> Tormado API
		- (pattern-based chatbot) -> Pandorabot
		- (pattern-based chatbot) -> RiveScript



