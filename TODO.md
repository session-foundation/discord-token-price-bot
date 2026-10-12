# TODO

## Move the Discord app to a company team

The bot's Discord application is owned by a former contributor's personal account, not a team, so nobody here can manage it: token, intents, install settings.

1. Create a developer Team (https://discord.com/developers/teams), ideally owned by a shared company account, and add the maintainers as Admins.
2. Ask the current owner to transfer the app to that team. They need to be a team member while transferring, and 2FA on their account; remove them afterwards.
3. If the transfer can't happen: create a new app under the team, put its `BOT_TOKEN` and `BOT_APP_ID` in the server's `.env.local`, restart, invite the new bot to each server and kick the old one.

## Once the app is under the team

- **Reset the bot token** (Bot tab), update `BOT_TOKEN` in the server's `.env.local`, restart. The previous owner may still hold the current token.
- **Turn off every Privileged Gateway Intent** (Bot tab), Message Content included. The code requests only `Guilds`.
- **Trim the bot's role permissions** in each server (Server Settings > Roles > the bot's role). Slash commands need none; the announcement channel needs View Channel, Send Messages and Embed Links only.
- **Trim the default install permissions** (Installation > Default Install Settings) to the same.
