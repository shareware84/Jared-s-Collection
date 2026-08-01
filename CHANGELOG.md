# C:\JARED\COLLECTION — Changelog

---

## v2.4

**Content**
- Photographs added for the last nine catalogued items that had no image of their own: the sealed 3DFX Voodoo 3 3000, the iPad 6th generation, the Braava 380, the GTX 1070 Founders Edition, the Emerson 13" TV/DVD combo, the Rift + Touch bundle, the Apple Watch Series 2, the Klydoclock and the i7-7700.
- Photograph coverage now stands at 726 of 815 items.

**Data**
- New chunk appended to `photos.js`, the nineteenth, keyed by item id as before. Everything shot to 320 px on the long edge, JPEG quality 72, transparency flattened to white — 7–14 KB apiece, in line with the existing entries.
- `photo` flag raised from 0 to 1 for the nine ids in both the archive and the admin page. No records added, no markup or script touched.

**Notes**
- Each entry in `photos.js` is a JSON *string* rather than an object, parsed one per tick so a phone never blocks on a single large parse. Adding photographs means appending another string to the array, not merging into an existing one; chunks are best kept under roughly 600 KB.
- The box art now attached to the i7-7700 is the unlocked K-series retail packaging. Either the photograph is of the wrong box or the item is a 7700K and the record needs renaming — flagged rather than guessed at.

---

## v2.3

**DOOM**
- `DOOM.EXE` at the DOS prompt now runs the shareware episode in-page through DOSBox, instead of sending you off to another site.
- Ships as a self-contained `doom.jsdos` bundle (1.96 MB) holding the executable, the WAD and a DOSBox config — SVGA, 16 MB of RAM, and a Sound Blaster 16 at port 220 / IRQ 5 to match the numbers the boot screen prints.
- The emulator opens in a Windows 95–styled window over the DOS terminal, and closing it returns the caret to the prompt rather than dropping you into the archive behind.

**Fixes**
- The DOSBox window was stacked below the DOS screen and rendered behind it. Raised above.
- Running DOOM injected the emulator's stylesheet into the page, which restyled every button and tab on the site. The emulator now runs inside an iframe so its CSS can't reach the page.
- The status bar reported a negative number of items without photographs. It was subtracting both the stored-photo and eBay-link totals from the item count, double-counting everything that had both — by now nearly the whole catalogue.

**Notes**
- DOOM's executable and WAD must come from the same release. A v1.1 engine looks for a split `STABARL`/`STABARR` status bar, which later WADs replaced with a single `STBAR`, and the mismatch stalls startup.

---

## v2.2

**Admin page**
- New `admin.html` for editing the catalogue without a rebuild. Change an item's category, sub-category, name or display order, or hide it entirely, then export an `overrides.js` file to upload alongside `index.html`.
- Search by name, filter by category, or narrow to only-edited, only-hidden, or only-without-photos.
- Thumbnails shown for every item so you can see what you're moving.
- Non-destructive: deleting `overrides.js` reverts everything.

**Browsing**
- New **Original collection** toggle in the toolbar, covering all 183 autographs plus the 15 other pieces marked as such — 198 items in total. Implemented as a separate flag so the *Signed* condition on autographs is preserved rather than overwritten.

**DOS screen**
- Pressing **S** during the boot sequence skips straight to the archive. Undocumented, and limited to the POST phase so it doesn't interfere with typing at the prompt.

**Content**
- Photographs added for the Puppy Bowl X signed football (dated to its 2 February 2014 premiere), the Daily Show notebook, the Mini Nickelodeon pillow and the Sony Pictures 2003 Preview Kit binder.
- Every eBay listing in the catalogue now has a photograph — the last dead links, the King of the Hill press kit and the sealed Flight Simulator 5.1, were both filled.
- Several low-resolution eBay thumbnails replaced with proper shots.

---

## v2.1

**Browsing**
- Shuffle now applies inside every category, not just the combined view, and reseeds each time you switch tabs or sub-filters — a different order every visit.
- Items with photographs always sort ahead of those without, in every category and every sort mode.
- Default page size raised from 48 to 75 items.
- On the **All** tab, recognisable material (autographs, films, games, TV, memorabilia) is weighted toward the top; reference software, utilities and bare hardware sink toward the bottom.

**Categories**
- **Vintage Computing** split into *Software*, *Hardware*, *Microsoft Home*, *Maxis* and *LucasArts*, in that fixed order.
- Microsoft Home widened from titles that literally say it to the whole product line that carried the logo — Exploration series, Encarta, Cinemania, Creative Writer, Scenes, Entertainment Packs, Flight Simulator and the rest. Microsoft's business and OS releases deliberately excluded.
- **Laserdisc** and **VHS** grouped by series where two or more titles exist (X-Files, Beavis & Butt-Head, Doug), everything else under *Films*.

**Detail view**
- Item records are wider with a much larger image pane.
- The ✕ on every window is properly centred — it was drifting off-centre on iOS.
- Removed the *ID confidence* row from autographs.

**DOS screen**
- `DOOM.EXE` and `DOOM1.WAD` added to `DIR`; running DOOM plays a startup sequence and opens the shareware episode at archive.org.
- `AUTOEXEC.BAT` and `CONFIG.SYS` added to `DIR`, both readable with `TYPE` or by name.
- `DEL *.*` runs a fake format of drive C, complete with percentage counter and write-fault error.
- `RESET.EXE` cold-boots the machine.
- Startup chime no longer plays on page load — only when you run a program.

**Fixes**
- Items with a stored photo no longer fall back to expired eBay URLs, which was producing broken-image icons when `photos.js` was slow or missing.
- An open item record now fills in its photograph as the data arrives instead of keeping the placeholder.
- Fixed a shuffle bug where the seed shifted every item's score by the same amount, leaving the order identical on every visit.

**Content**
- Masthead reads *Collection Browser v2.1*.
- 18 photographs added; several duplicate and non-collection entries removed.

---

## v2.0

**Photographs**
- All 479 recoverable eBay listing photos downloaded and embedded permanently, so the archive no longer depends on eBay. Only 6 listings had photos that were genuinely gone.
- 173 autograph binder photographs embedded.
- Photos split into a companion `photos.js` file, cutting the page itself from 8.25 MB to under 450 KB. Images stream in behind the catalogue in chunks so phones stay responsive.
- Item-specific placeholder icons drawn for items with no photograph — televisions, VR headsets, monitors, cartridges, cels and about twenty more, matched from the item name.

**DOS boot screen**
- The archive now opens on a black screen running a BIOS memory check. Type `JARED.EXE` at the prompt to enter.
- Working command line: `DIR`, `HELP`, `TYPE README.TXT`, and a hidden `HAHA.EXE`.
- FM-synthesised startup chime, generated in the browser rather than sampled.
- Minimising the archive returns to the DOS shell with its scrollback intact.

**Interface**
- Rebuilt as a Windows 95 application — desktop teal, beveled silver panels, folder tabs, a status bar, and item records as child windows.
- Bitmap masthead lettering.
- Solitaire-style photo cascade on the window close button.

**Categories**
- All 182 autographs classified by genre: Television, Film, Comedy, Music, Animation, Sports, Politics & News, Space, Notable Figures.

**Privacy**
- Purchase prices removed from the file entirely, not merely hidden. Blurred placeholders remain where a price was recorded.
- Storage locations stripped from the data.

---

## v1.0

- Initial catalogue built from the household inventory spreadsheet — 648 items across Vintage Computing, Vintage Gaming, Autographs, Press Kits, Laserdisc, VHS, DVD, Electronics, Memorabilia and Trading Cards.
- Search, category tabs, sort by date, name and price.
- Item detail view with condition, publisher, location and acquisition date.
- Photographs loaded live from the eBay links recorded in the spreadsheet.
