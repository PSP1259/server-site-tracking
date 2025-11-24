# 02_server-side Event Flow

## Goal
Define the exact data path for server relayed events so that later comparisons are unambiguous.

---

## Event Transport Flow

Step 1  
User interacts with website in browser.

Step 2  
Web Tag Manager captures the interaction and builds an event payload.

Step 3  
Web Tag sends the payload to the first party collection endpoint.  
Example endpoint: https://ss.example.com/collect

Step 4  
Server Container receives the request and evaluates routing rules.

Step 5  
Server Container forwards the event to destinations.

Destinations can include:
GA4 Measurement Protocol  
Meta Conversion API  
TikTok Events API  
Google Ads Enhanced Conversions  
Custom HTTP endpoints

---

## Payload Rules
Server side receives event scoped data first party.  
Only compatible dimensions and parameters are forwarded per destination.

Typical normalization actions on server:
Parameter mapping  
PII hashing if required  
Consent gating  
Deduplication using event_id  
Enrichment with server level context (ip, ua, geo)

---

## Identity and Deduplication
Server side should implement:
event_id on all events  
client_id pass through  
optional user_id pass through if available

Deduplication is based on:
event_id  
timestamp  
client_id

---

## Comparison Notes
Client side and server side must produce:
Same event names  
Same parameter schema  
Same test case flows

Only the transport path differs.
