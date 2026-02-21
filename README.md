# Hotel Customer Service - ClawLite Template

ClawLite template for creating a Hotel Customer Service agent.

## Features

- 🏨 Room and hotel facility information
- 💰 Pricing and reservation assistance
- 🛎️ Hotel services information
- 📍 Nearby attractions info
- 🌐 Bilingual support (Indonesian/English)

## Usage

```bash
clawlite instances new aisyahsyihab/hotel-cs my-hotel-agent
```

The wizard will prompt you for:
- Hotel name
- Hotel address
- Contact phone
- Star rating
- Check-in/check-out times

## Configuration

After instance creation, edit:

1. **`.env`** - Add your API keys (copy from `.env.example`)
2. **`workspace/TOOLS.md`** - Update room rates, facilities, policies
3. **`workspace/SOUL.md`** - Customize persona if needed
4. **`workspace/AGENTS.md`** - Adjust response formats if needed

## Start the Agent

```bash
clawlite instances start my-hotel-agent
```

## Template Structure

```
workspace/
├── SOUL.md     # Agent persona and communication style
├── AGENTS.md   # Rules, response formats, escalation matrix
└── TOOLS.md    # Hotel info (rooms, rates, facilities, policies)
```

## Suitable For

- Hotels (1-5 stars)
- Boutique hotels
- Serviced apartments
- Guest houses

## License

MIT
