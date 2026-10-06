# Brix36 for Claude

Films and music videos. You're the star.

![Brix36](plugins/brix36/brix36-icon.png)

Brix36 makes films and music videos starring you or your artist. With this plugin, Claude plans the film or music video with you, shows the storyboard and the exact credit price, and starts production once you say yes. It then hands back the finished video link.

## Install

In Claude Code:

```
/plugin marketplace add https://github.com/socialiserapp-design/brix36-plugin.git
/plugin install brix36@brix36
```

Then sign in to Brix36 when asked (or run `/mcp` and choose Brix36). On claude.ai you can also add the connector directly: Settings → Connectors → Add custom connector → `https://api.brix36.com/mcp`.

You need a Brix36 account. Each person signs in with their own account through Brix36's own sign-in page; Claude never sees your password.

## What you can ask

- Make a 30-second film of me as an action hero.
- Turn my song into a music video.
- Show my recent Brix36 videos.

## Credits and approval

Brix36 uses the credits on your own account. Claude shows the price for the whole job and spends nothing until you say yes. One approval covers that job. If you are short of credits, top up in the Brix36 app or on brix36.com.

## Help

Setup guide: https://brix36.com/connect
Support: https://legal.brix36.com/support
Privacy: https://legal.brix36.com/privacy
Terms: https://legal.brix36.com/terms

The files in this repository (plugin manifest, skill and README) are MIT licensed. The Brix36 service and logo are not covered by that licence.
