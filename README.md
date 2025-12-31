# N8N-Ninja-workflows
Just a place for some simple N8N workflows that are integrated with Anthropic (Claude AI) and NinjaOne RMM

First work flow will be a nifty little "report phish" option for Ninja Tickets. Users can forward an email they are suspicious of to the support email in Ninja that will auto generate a help desk ticket.  The user changes the subject to include "Is this legit" which is the search term N8N's trigger will be looking for.

The flow is as such: Trigger is polled ever 5 minutes -> A token is pulled from Ninja and refreshed when needed -> N8N grabs unassigned tickets -> Those tickets are filtered by messages that contain "Is this legit" in the subject line -> The content of the email is extracted -> Calude Agent analyzes the content of the email -> N8N formats the response -> N8N grabs the ticket details -> N8N updates the ticket to resolved -> The Analysis comment is then added into the body of the ticket. 

