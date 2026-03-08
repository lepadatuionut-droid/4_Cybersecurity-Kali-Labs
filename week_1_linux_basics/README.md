# Week 1 – Linux CLI Essentials (Kali / Apporto)

**Focus:** Practical Linux terminal fundamentals used in cybersecurity workflows:
- Directory & file operations (`mkdir`, `touch`, `cp`, `mv`, `rm`, `rm -r`, `rmdir`)
- Handling absolute paths in Kali (using `/home/kali/...` when `~` is not available)
- Quoting/escaping names with spaces
- Exporting terminal history (`history > my_history.txt`)
- Packaging outputs as a ZIP for export

## What’s inside this week
- `command_line/` – working directory used during the lab
- `docs/Week_1_LAB_work_report.docx` – full lab write‑up
- `screenshots/` – selected terminal/desktop screenshots
- `archives/` – exported artifact (zip) for download

## Notes & lessons learned
- The VM file manager and the Apporto Files panel can show different mounts; the terminal is the source of truth for real paths.
- A trailing slash on `mv` makes your intent clear when moving **into** a directory (`mv homeworkfile linux.lunches/`).
- Use `rm -ri` when learning—interactive confirmations help avoid mistakes.
