# WhatsApp Echo Bot v2.4

A Node.js bot powered by [whatsapp-web.js](https://github.com/pedroslopez/whatsapp-web.js) that automatically echoes incoming text messages back to the sender, with configurable options and admin controls.

## ⚙️ Features

- **Echo Mode**: Reply or send messages back with quotes.
- **Admin Whitelist**: Only numbers in the `ADMINS` array can toggle echo on/off in chat.
- **Terminal Controls**: Fully control bot behavior via terminal commands.
- **Case Conversion**: Option to convert messages to lowercase before echoing.
- **One-Time Echo**: Automatically disable after one reply.
- **Adjustable Delay**: Set response delay in milliseconds at runtime.
- **Reply Modes**: Choose between `msg.reply()` (quoted) or `client.sendMessage()` (new message).
- **Graceful Shutdown**: Cleans up session and exits on Ctrl+C.

## 🚀 Installation

1. **Clone repository**
   ```bash
   git clone https://github.com/yourusername/whatsapp-echo-bot.git
   cd whatsapp-echo-bot
   ```
2. **Install dependencies**
   ```bash
   npm install whatsapp-web.js qrcode-terminal
   ```
3. **Configure admins**
   - Open `bot.js` and update the `ADMINS` array with your WhatsApp number(s) in `<number>@c.us` format.

4. **Run the bot**
   ```bash
   node bot.js
   ```
5. **Scan QR**
   - A QR code appears in the console. Scan it with WhatsApp > Linked Devices.

## 💻 Usage

### Terminal Commands

| Command   | Description                                  |
|-----------|----------------------------------------------|
| `on`      | Enable echo mode                             |
| `off`     | Disable echo mode                            |
| `l`       | Enable lowercase conversion                  |
| `ll`      | Disable lowercase conversion                 |
| `d`       | Enable response delay                        |
| `dd`      | Disable response delay                       |
| `t`       | Enable one-time echo                         |
| `tt`      | Disable one-time echo                        |
| `r`       | Use `msg.reply()` (quoted reply)             |
| `rr`      | Use `client.sendMessage()` (new message)     |
| `sd <ms>` | Set response delay to `<ms>` milliseconds     |
| `info`    | Show current configuration                   |

### Chat Commands (Admin Only)

Send the following commands in any chat from an admin number:

- `!on`  — Enable echo mode
- `!off` — Disable echo mode

## ⚙️ Configuration Options

In `bot.js`, adjust default values:

```js
const ADMINS       = ['12345678901@c.us'];
let   responseDelay = 100;
let   echoEnabled   = false;
let   toLowerCase   = true;
let   oneTime       = true;
let   useDelay      = false;
let   useReply      = false;
```

- **`ADMINS`**: Array of WhatsApp IDs allowed to control the bot.
- **`responseDelay`**: Delay before responding (ms).
- **`echoEnabled`**: Default echo state.
- **`toLowerCase`**: Convert messages to lowercase.
- **`oneTime`**: Disable echo after one response.
- **`useDelay`**: Apply delay before replies.
- **`useReply`**: Choose reply method.

## 📄 License

MIT License

---
*Happy coding!*

