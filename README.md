# The Paperclip Ledger

A single-file, no-backend weekly habit tracker inspired by *Atomic Habits* — including the "paperclip method" of moving a marker from one jar to another every time you complete a habit.

## How it works

- **Add / remove habits.** Each habit has a name and an optional small reward.
- **Weekly checkboxes.** Every habit gets one checkbox per day, Monday–Sunday.
- **Auto weekly reset.** Every time you open the page, it checks whether the calendar has moved into a new week (i.e. past Sunday night). If so, it archives the just-finished week into history and clears the checkboxes for the new week. If you leave a tab open across the boundary, it also re-checks once a minute.
- **Paperclip jars.** The "To move" jar starts with one clip for every checkbox across all your habits (habits × 7). Every time you check a box, a clip visually moves to the "Moved" jar. Both jars reset with the week.
- **History & trends.** Past weeks are archived with each habit's completion count, plus a small bar chart of your overall weekly completion percentage.
- **Rewards.** If a habit's reward is filled in and you complete all 7 days, a small "you earned it" banner appears on that habit.
- **Backup.** Since everything is stored in your browser's local storage (tied to this device/browser), use **Export backup** occasionally to save a JSON snapshot, and **Import** to restore it (e.g. after clearing browser data, or on a new device).

## Hosting it on GitHub Pages

1. Create a new GitHub repository (public or private — Pages works with both if you have GitHub Pro/Team for private, otherwise use public).
2. Add `index.html` to the repo (drag-and-drop on github.com works fine, or `git add` / `git commit` / `git push` if you're working locally).
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to "Deploy from a branch," pick your default branch (usually `main`) and `/ (root)` as the folder, then save.
5. GitHub will give you a URL like `https://yourusername.github.io/repo-name/`. It can take a minute or two to go live.

That's it — no build step, no dependencies to install. Just this one HTML file.

## A couple of things worth knowing

- Data is stored per browser, per device (localStorage). If you check it from your phone and your laptop, they won't sync with each other — each keeps its own history. If you want a single source of truth, pick one device (or export/import between them manually).
- Clearing your browser's site data/cache for this page will wipe your habits and history — that's what the export/import backup is for.
- Weeks run Monday–Sunday, with the reset effectively landing right after Sunday 11:59pm (technically: the moment your calendar rolls into Monday).
