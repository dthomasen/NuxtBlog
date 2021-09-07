---
title: 'Starting Spotify playlist on Sonos via Home Assistant'
image: 'music.jpeg' 
---

There doesn't seem to be an official way to start a Spotify playlist on Sonos via Home Assistant - Everything is using Google Cast or the Spotify Connect protocols.  
But after a lot of trial and error, I now bring you (some) solution.
<!--more-->
## Solution
For this to work you unfortunately have to add the playlist to your "My Sonos" in the Sonos app. Sonos made this a bit harder in one of the latest update, but there's still a way to do it:  

1. Open the Sonos app
2. Tap the search icon
3. Search for the playlist you want to add to Home Assistant
4. Tap it
5. Tap the three dots in the top right corner
6. Select "Add playlist to My Sonos" 

This playlist will now be available to Home Assistant through the select_source service:
```yaml
service: media_player.select_source
  target:
    entity_id: media_player.kokken
  data:
    source: '{{ spotify_playlist_name_ }}'
```

## Lovelace jukebox
To make things easier I've created a grid layout with all the playlists available:
 ![Jukebox grid](/posts/music-grid.jpeg)
Each grid item is a picture card with a tap action that sends a playlist string to a playback script:

```yaml
type: picture
image: >-
  https://i.scdn.co/image/ab67706f00000003d5ffd45a445bb10d75860445
tap_action:
  action: call-service
  service: script.1628579220991
  service_data:
    spotify_playlist: Sunday Funday
  target: {}
hold_action:
  action: none
```

## Playback script
To avoid playing starting with the same song on each playback start, I'm setting the media_player to shuffle before starting the playlist.

```yaml
alias: Afspil spotify playliste på køkken
sequence:
- service: media_player.shuffle_set
  data:
    shuffle: true
  target:
    entity_id: media_player.kokken
- service: media_player.select_source
  target:
    entity_id: media_player.kokken
  data:
    source: '{{ spotify_playlist }}'
  mode: single
```