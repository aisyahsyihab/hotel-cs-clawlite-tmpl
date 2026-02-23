# TOOLS.md - Hotel Configuration

## Required Skills

- `hotel_invoice` — Invoice & customer management (configure skill name as needed)

## Hotel Details

**Name:** [Hotel Name]
**Address:** [Address]
**Phone:** [Phone]
**Email:** [Email]

## Room Types

| Type | Size | Bed | Rate/night |
|------|------|-----|------------|
| [Room Type 1] | - m² | - | NOT SET |
| [Room Type 2] | - m² | - | NOT SET |
| [Room Type 3] | - m² | - | NOT SET |

*Configure actual room types and prices*

## Policies

- **Check-in:** 14:00
- **Check-out:** 12:00
- **Early check-in:** Subject to availability
- **Late check-out:** Subject to availability

## Additional Services

| Service | Rate |
|---------|------|
| Breakfast | NOT SET |
| Extra bed | NOT SET |
| Airport Transfer | NOT SET |

*Update prices when provided by owner*

## Pricing Rules

- **Weekday:** Base price
- **Weekend:** Base price + X%
- **Peak Season:** Base price + Y%

*Configure percentages as needed*

## Quick Reference

### Check Price
```
hotel_invoice(tool="get_prices", room="room_code")
```

### Create Invoice
```
hotel_invoice(
  tool="create_invoice",
  customer_name="Guest Name",
  phone="08xxx",
  room="room_code",
  check_in="YYYY-MM-DD",
  check_out="YYYY-MM-DD"
)
```

### Submit & Send PDF
```
hotel_invoice(tool="submit_invoice", invoice_id="INV-xxx")
hotel_invoice(tool="get_pdf", invoice_id="INV-xxx")
```

## Notes

- All invoices created as DRAFT first
- MUST confirm with guest before submit
- PDF sent as file attachment, not link
- Never quote prices not in this file
