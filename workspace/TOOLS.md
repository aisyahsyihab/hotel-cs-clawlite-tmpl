# TOOLS.md - Tool Usage Guide

<cron-reminders>
## Membuat Reminder

Gunakan `add_cron` dengan `clawlite-send` untuk kirim reminder ke user.

<example>
<tool_call>
{"tool": "add_cron", "args": {
  "schedule": "30 14 * * *",
  "command": "clawlite-send {user_id} \"Reminder: Waktunya minum vitamin!\"",
  "comment": "Reminder vitamin harian"
}}
</tool_call>
</example>

<schedule-format>
┌───────────── menit (0-59)
│ ┌───────────── jam (0-23)
│ │ ┌───────────── hari dalam bulan (1-31)
│ │ │ ┌───────────── bulan (1-12)
│ │ │ │ ┌───────────── hari dalam minggu (0-6, 0=Minggu)
│ │ │ │ │
* * * * *
</schedule-format>

<schedule-examples>
- `*/5 * * * *` — setiap 5 menit
- `0 9 * * *` — jam 9 pagi setiap hari
- `30 14 * * 1-5` — jam 14:30 Senin-Jumat
- `0 8 1 * *` — jam 8 pagi tanggal 1 setiap bulan
</schedule-examples>

<rules>
- WAJIB gunakan `clawlite-send {user_id} "pesan"` untuk kirim reminder
- Ganti `{user_id}` dengan ID user yang request (e.g., `tg_123456`, `wa_628xxx`)
- JANGAN PERNAH pakai `echo` — pesan tidak akan terkirim ke user!
</rules>
</cron-reminders>

<send-file>
## Kirim File

Untuk kirim file (invoice PDF, dll) ke user:

<example>
<tool_call>
{"tool": "send_file", "args": {"path": "/workspace/users/{user_id}/invoice.pdf"}}
</tool_call>
</example>
</send-file>

<calendar>
## Google Calendar (Reservasi)

Gunakan `krasan-admin calendar` untuk cek dan tambah reservasi.

### Cek Reservasi Tanggal Tertentu

```bash
krasan-admin calendar get --date 2026-03-15
```

### Scan Reservasi Range Tanggal

```bash
krasan-admin calendar scan --start 2026-03-01 --end 2026-03-31
```

### Tambah Reservasi Baru

```bash
krasan-admin calendar add \
  --guest "Nama Tamu" \
  --phone "08123456789" \
  --check-in 2026-03-15 \
  --check-out 2026-03-17 \
  --room 1 \
  --booking-info "Extra bed 1, dekorasi"
```

<parameters>
- `--guest` — Nama tamu (wajib)
- `--phone` — Nomor telepon (wajib)
- `--check-in` — Tanggal check-in YYYY-MM-DD (wajib)
- `--check-out` — Tanggal check-out YYYY-MM-DD (wajib)
- `--room` — Room ID, bisa multiple: `--room 1 2` (opsional)
- `--booking-info` — Info tambahan: extra bed, dekorasi, dll (opsional)
- `--json` — Output dalam format JSON
</parameters>

<room-ids>
- 1 = SINDORO (VVIP)
- 2 = BISMO (VIP)
- 3 = PAKUWOJO (VIP)
- 4 = SEMERU (VVIP)
</room-ids>

<example>
<tool_call>
{"tool": "shell", "args": {"command": "krasan-admin calendar get --date 2026-03-15 --json"}}
</tool_call>
</example>
</calendar>
