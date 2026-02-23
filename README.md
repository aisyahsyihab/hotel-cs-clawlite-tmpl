# Hotel CS ClawLite Template

ClawLite template for hotel/villa customer service with capabilities:
- Reservations & bookings
- Invoice creation & PDF delivery
- Room pricing information

## Requirements

- Invoice skill (e.g., `krasan_invoice` or custom)
- Backend system (e.g., Frappe/ERPNext)

## Quick Start

```bash
# Create new instance from template
./clawlite instances new my-hotel --template aisyahsyihab/hotel-cs-clawlite-tmpl
```

The wizard will prompt you for:
- Hotel name
- Hotel address
- Contact phone
- Star rating
- Check-in/check-out times

## First User = Owner

The first person to chat with the agent becomes the **owner**. The agent will ask for hotel configuration info and save it to the workspace files.

## Configuration

Edit files after creating instance:

1. **workspace/SOUL.md** - Hotel name and personality
2. **workspace/TOOLS.md** - Room types, prices, policies
3. **workspace/AGENTS.md** - Specific rules if needed

## Important: Set Timezone

Add to container environment to fix time-based greetings:

```
TZ=Asia/Jakarta
```

Without this, greetings will use UTC and be wrong for local time.

## Recommended Model

- **Production:** Qwen3-8B (reliable, efficient)
- **Budget:** Qwen3-4B (lighter, still capable)
- **Premium:** Qwen3-14B (best accuracy)

## Files

```
hotel-cs-clawlite-tmpl/
├── workspace/
│   ├── SOUL.md      # Agent persona
│   ├── AGENTS.md    # Rules & workflow
│   └── TOOLS.md     # Hotel config & prices
├── config-example.yaml
├── .env.example
├── template.yaml
└── README.md
```

## Key Rules

1. **Never make up prices** - Only quote what's in TOOLS.md
2. **Update files when owner provides info** - Save immediately
3. **PDF sending** - Use get_pdf tool, it sends automatically
4. **Draft first** - Always create invoice as draft, confirm, then submit

## Workflow

```
Guest → Ask room/price → get_prices()
      → Want to book → collect info → create_invoice()
      → Confirm → approve → submit_invoice() → get_pdf()
```

## Customization

1. Edit `workspace/SOUL.md` for personality/greeting
2. Edit `workspace/TOOLS.md` for room types, prices, services
3. Edit `workspace/AGENTS.md` for workflow rules
4. Replace placeholder `[Hotel Name]` etc. with actual values
5. Replace `NOT SET` prices with actual prices
