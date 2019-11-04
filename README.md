[![Build status](https://badge.buildkite.com/8ce0723b03f875a2dd9ba526d3b6fbc8601d1be1f56a02e94e.svg)](https://buildkite.com/benji7425/rss-fetcher)

# Discord RSS fetcher
A Discord bot to post the latest articles from an RSS feed into a channel, optionally mentioning a role when posting.

## Features
- Multiple feeds per server
- Commands to configure feeds in different channels
- Optional role to be mentioned when a feed article is posted
- Detects if a user "beats me to it" by posting the URL before the bot can (useful for slow feeds)
- Specific handling for YouTube links, detects both long and short YouTube URLs

## Use cases
- You want to stay up to date with an RSS feed
- You want your Discord server to be notified of events via an RSS feed

## Getting started
RSS Fetcher needs to be deployed before you can invite it to your Discord server. Please see [my written deployment guide](https://benji7425.io/discord-deployment) or [video tutorial](https://www.youtube.com/watch?v=DjQayKgcjGM) which can guide you through deployment even if you are a beginner.  
Once you have deployed RSS Fetcher then return here to follow the Discord setup instructions below.  

This button can be used for following the Heroku deployment steps.

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/benji7425/discord-rss-fetcher)

## Discord Setup
Follow these instructions once you have deployed the RSS Fetcher and added it to your Discord server.
Use `@RSS Fetcher help` to view available commands.

**Admin only**
These commands require administrator permission in the Discord server.
- `@RSS Fetcher add-feed <url> <#channel> [@role]` to add a new feed
- `@RSS Fetcher view-feeds` to view configured feeds for this server
- `@RSS Fetcher remove-feed <feed-id>` to remove a feed by it's ID (found using the `view-feeds` command)

Example:
`@RSS Fetcher add-feed http://lorem-rss.herokuapp.com/feed?unit=second&interval=30 #rss-posts @subscribers`

## Permissions
The bot requires certain permissions, which you are prompted for on the invite screen.
Each permission has a reason for being required, explained below.

| Permission           | Reason                                                              |
|----------------------|---------------------------------------------------------------------|
| Read messages        | Detect when you use commands                                        |
| Send messages        | Respond when you use commands; post new RSS links                   |
| Read message history | Check if any new RSS links have been posted during downtime         |
| Embed links          | Responses to 'help' requests use message embeds for nice formatting |

## Built With
- [Node.js](https://nodejs.org/en/) - *Runtime*
- [discord.js](https://github.com/discordjs/discord.js) - *Discord library*
- [disharmony](https://github.com/benji7425/disharmony) - *Bot framework*
- [rss-parser](https://github.com/bobby-brennan/rss-parser) - *RSS parsing library*

## Versioning
[SemVer](http://semver.org/) is used for versioning; view available versions on the [tags page](https://github.com/your/project/tags)

## License
This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details
