# Discord Notification Bot 🚀

## Overview 🌟

The Discord Notification Bot is a simple and efficient bot designed to send notifications to a specified Discord channel. It can be used for various purposes, such as alerting users about events, updates, or any important information.

## Features ✨

- 📬 Send messages to a specific channel
- 🛠️ Customizable notification messages
- ⚙️ Easy to set up and configure
- 📊 Supports multiple notification types (text, embeds)

## Prerequisites ✅

- Node.js (version 14 or later)
- A Discord account
- A Discord server where you have permissions to add a bot

## Installation 🛠️

1. **Clone the repository:**

   ```bash
   git clone https://github.com/yourusername/discord-notification-bot.git
   cd discord-notification-bot
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Create a Discord bot:**
   - Go to the [Discord Developer Portal](https://discord.com/developers/applications).
   - Create a new application and add a bot to it.
   - Copy the bot token. 🔑

4. **Configure the bot:**
   - Create a `.env` file in the root directory and add your bot token and channel ID:

     ```plaintext
     DISCORD_TOKEN=your_bot_token
     CHANNEL_ID=your_channel_id
     ```

## Usage 🚀

1. **Start the bot:**

   ```bash
   npm start
   ```

2. **Send a notification:**
   Modify the `notify.js` file to customize the notification message and type.

## Example Notification 💬

```javascript
const { Client, GatewayIntentBits } = require('discord.js');
require('dotenv').config();

const client = new Client({ intents: [GatewayIntentBits.Guilds, GatewayIntentBits.GuildMessages] });

client.once('ready', () => {
    console.log(`Logged in as ${client.user.tag}!`);
});

client.on('messageCreate', message => {
    if (message.content === '!notify') {
        const channel = client.channels.cache.get(process.env.CHANNEL_ID);
        if (channel) {
            channel.send('This is a notification message! 📢');
        }
    }
});

client.login(process.env.DISCORD_TOKEN);
```

## Contributing 🤝

If you would like to contribute to this project, please fork the repository and submit a pull request.
