# discord.js-enhanced

# Setup

```javascript
const { Client, SlashCommand } = require("discord.js-enhanced"); // Require everything we will need.
const client = new Client(); // Create a new client.
const eventHandler = client.event; // Get the event handler for events, such as messageCreate and all other discord events.

client.logEvents(); // If you want to log events (MessageCreate, etc) put this here. If not, remove it.

eventHandler.on("ready", () => {
  const commandHandler = new SlashCommand(client);
  commandHandler.addCommand( // Register the command.
    {
      name: "ping", // Command name
      description: "test", // Command description
      options: [ ], // Options (Optional)
    },
    (callback = (client, interaction, args) => { // Callback (Has to be function)
        interaction.reply("Pong!"); // Reply
    })
  );
    commandHandler.sync("guildid");
}
  
  client.login("token");

```
