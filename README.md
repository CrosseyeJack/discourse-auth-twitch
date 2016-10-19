discourse-auth-twitch
=====================

Twitch API OAuth for Discourse

Installation Instructions (for Docker installations):
This plugin relies on some changes patched into Discourse - https://github.com/CrosseyeJack/discourse-twitch-oauth-patch

These changes just mean we are relying on Twitch to validate our user names for us instead of discourse.

* Open your container app.yml
* Register a new Twitch API application at http://www.twitch.tv/kraken/oauth2/clients/new if you haven't already.
  * For the Redirect API: http(s)://example.com/auth/twitch/callback
* Under section ```env:``` your Twitch API credentials must be added:
```
  TWITCH_CLIENT_ID: CLIENT_ID
  TWITCH_CLIENT_SECRET: CLIENT_SECRET
```
* Under section ```hooks:``` append the following
```
          - git clone {Path to git}.git
```
* Rebuild the docker container
```
./launcher rebuild my_image
```
