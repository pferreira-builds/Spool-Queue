# Spool Queue

A single-file 3D print job organiser. One HTML file, no install, no server, no account.
Open it in a browser and it works, including offline.

It gives you a 15-day plan, a first-come-first-served queue per printer, a price for every
job built from your own rates, and a printable client quote.

---

## Getting started

1. Save `spool-queue.html` anywhere on your computer.
2. Double-click it. It opens in your default browser.
3. Bookmark the tab, that is your app from now on.

That's the whole install. There is nothing to sign up for and nothing leaves your machine.

**Optional, and worth it:** drag the file into your Applications folder, Documents, or a
Dropbox/Drive folder so you always open the same copy. Your data is tied to the browser,
not to the file, but keeping one copy avoids confusion later.

---

## First five minutes

Open **Settings** and fill in four things. Every price in the app is calculated from them,
so it is worth being honest here.

| Setting | What it means | A reasonable starting point |
|---|---|---|
| Labour rate | What an hour of your own time is worth | Whatever you would charge for an hour of work |
| Waste / failure % | Purge, brims, skirts, the occasional failed print | 5% if you are reliable, 10-15% if you print tricky things |
| Margin % | Profit on top of your real cost | 20-30% for hobby work, more for one-off commissions |
| Currency | Just the symbol shown on screen | € / $ / £ |

Then the **Printers** tab, one row per machine:

- **Rate /h** is what an hour of printing costs you in power, wear and consumables.
  If you have no idea, `0.85` per hour is a sane placeholder for a mid-size FDM printer.
- **Unattended** is the important one. Leave it ticked if you are happy to let that
  machine run overnight, and the plan gives it 24 hours a day. Untick it and the plan
  only books work between the **Start** and **End** hours you set, so a job needing more
  hours than your working day gets flagged instead of quietly "finishing" at 3 a.m.
- **Colour** is how that printer shows up on the calendar.

Then the **Filament** tab, one row per spool type, with the price per kilogram you
actually paid.

---

## Adding a job

**+ New job**, and fill in:

- **Product** and **Quantity**
- **Client / order** — optional, but this is what powers the client filter and quotes
- **Printer** and **Filament**
- **Material (g)** and **Print time (h)** — per unit, straight from your slicer's estimate
- **Hands-on (min)** — supports removal, sanding, assembly, packing; per unit
- **Deadline** — when it has to be in the customer's hands

The price appears live as you type, broken into filament, machine, labour, and margin,
with a per-unit figure when quantity is more than one.

The **Notes** field is free text: layer height, infill, which nozzle, colour swaps,
packaging, anything future-you will want.

---

## How the schedule works

Jobs run **first come, first served** on each printer. The job at the top of a printer's
lane starts now, the next one starts when it finishes, and so on across the 15-day plan.

- **Reorder** with the ▲▼ buttons, or type a position number in the box and press Enter.
  Everything reschedules instantly.
- **Pin to day** (in the job detail) forces a job onto a specific date. Pinned jobs claim
  their slot first and the rest of the queue flows around them.
- Each day card shows a **capacity bar per printer** and the jobs running that day, with
  their clock times. A `↳` chip is a job continuing from the previous day.

### The warnings

The banner at the top of the page tells you the truth about your queue:

- **Day over the ceiling** — a day has more work booked than the printer's hours allow.
  This only happens when a pin overbooks a day. That day turns red.
- **Longer than the working day** — a single print needs more hours than that printer's
  window. It only works if the machine may run unattended overnight.
- **Finishes after the deadline** — the job will be late. It names the finish date and
  the deadline so you can see the size of the problem.
- **Outside the 15-day window** — your queue is simply longer than the plan.

---

## Quotes

Pick a client in the header dropdown. The queue, the totals, and the **Quote** button all
narrow to that client's jobs.

**Quote** opens a one-page quote: line items with quantity, filament used, print time,
unit price and amount; the total; filament and machine-time totals; a ready-by date taken
from the actual schedule. The terms line is editable in place for one-off wording, or
permanently in Settings → Rates. **Print / PDF** prints the quote alone, without the rest
of the app.

Set **Shop name** in Settings → Rates so your name is at the top of it.

---

## Your data

Everything lives in your browser's local storage, on that one machine, in that one
browser. It survives closing the tab, restarting, and being offline.

It does **not** sync between machines, and clearing your browser's site data clears the
queue.

So: press **Backup** now and then. It downloads a JSON file with all your settings and
jobs. **Restore** loads one back, on any machine. That file is also how you move to a new
computer, and how you keep a copy before doing anything drastic.

**Or let it keep a file for you.** In Chrome, Edge, Brave or Opera there is a **Keep a
file** button in the top bar. Pick a JSON file once and every change is written to it as
you go, on top of the browser copy. When you open the page, the newer of the two wins.
Put that file in a Dropbox, Drive or OneDrive folder and the same queue opens on any
machine that points at it, with the folder's own backup and version history, and still
no server and no account. The browser asks you to allow the file again each session
(one click on **Reconnect file**). Firefox and Safari do not have this feature yet, so
there the button does not appear and nothing changes.

Finished jobs stay in the list forever. Tick **show finished** under the queue to see
them, along with what you charged.

---

## Keyboard

- `N` — new job
- `Esc` — close the open panel

## Notes

- Works in any current browser. Chrome, Firefox, Safari, Edge. Keeping a file is Chromium only for now.
- The interface follows your system light/dark setting; the ◐ button overrides it.
- Fonts load from Google Fonts when you are online, and fall back to your system fonts
  when you are not. Nothing else is fetched, and nothing is sent anywhere.

