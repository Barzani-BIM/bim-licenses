# BIM Field Tools — licenses

`licenses.json` decides which Windows PCs can run BIM Field Tools. The app reads it at start and every 30 minutes.

## Give a PC access
1. The person opens the app. The lock screen shows **This PC's code**, e.g. `3F9A-21C7-88D0`. They send it to you.
2. Here on GitHub open `licenses.json` → ✏️ pencil → add a line under `"devices"`:
   ```json
   "3F9A-21C7-88D0": {"name": "Duhok PC 2", "active": true},
   ```
   Every line except the last one in the list ends with a comma.
3. **Commit changes**. On their PC: **Check again** (GitHub can take up to 5 minutes to show the change).

## Options per PC
- `"active": false` — turn that PC off (the app locks within 30 minutes, or at next start).
- `"until": "2027-06-30"` — access ends after that date.
- `"message": "..."` — text shown on that PC's lock screen.

## Switch everyone off
Set `"enabled": false` at the top (and optionally a `"message"`). Set it back to `true` to switch on again.

## Offline
A PC that checked OK keeps working for 3 days without internet, then asks to connect once.

This repo must stay **public** so the app can read the file. Anyone can see it, so for `"name"` use a short label like `"Duhok PC 2"`, not personal details.
