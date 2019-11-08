---
description: Creating a Google Assistant app to get realtime public transport information
---

# Voice assistant

Most of us have experienced this before. You wake up in the morning, eat some breakfast, get dressed and run out of the door to catch a train or bus. Only to find out it is cancelled, or there are major delays.

While it's impossible to have every train and bus running on time, open data can at least prevent needless runs to the station by letting you shout at your Google Home, Echo Speaker, or your phone to ask about the next bus before you leave. Today we will create our own voice assistant app to provide us with real-time transport data through Google Assistant.

Example code is written in PHP, but any language works. All frameworks are free. No \(credit\) card is required for sign-up. You can create everything yourself based on this tutorial, or you can choose to import the dialogflow agent and/or our server implementation.

## Putting it all online

As DialogFlow needs to send an HTTP request to your server application, your server application needs to be accessible from the internet, either with a static IP address or a domain name.

* You can deploy through Heroku, which offers a free-tier with unlimited duration. See [our tutorial on Heroku](https://github.com/trafiklab/trafiklab-docs/tree/85417ce9d0f16da3542693f3543876deea25161c/using-trafiklab-data-1/related-tools/heroku.md) to learn how to set it up.
* You can host the application on a server or VPS, for example on DigitalOcean
* You can host the application on a Raspberry Pi in combination with port forwarding on your router. 

After you have deployed your server application, don't forget to update your DialogFlow fulfillment settings!

