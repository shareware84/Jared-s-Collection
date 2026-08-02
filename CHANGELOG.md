# C:\JARED\COLLECTION — Changelog

---

## v2.5

**Content**
- Photographs added for the last nine catalogued items that had no image of their own: the sealed 3DFX Voodoo 3 3000, the iPad 6th generation, the Braava 380, the GTX 1070 Founders Edition, the Emerson 13" TV/DVD combo, the Rift + Touch bundle, the Apple Watch Series 2, the Klydoclock and the i7-7700.
- Photographs added for the two advance screening passes: I-Spy (2002) and Fred Claus (2007).
- Photographs added for the Panasonic KXL-D720 CD-ROM drive; replacements for the two Sony Magic Link entries (the loose unit and the sealed headset bundle) and the Quest 2 silicone cover.
- Photograph added for the Bob Camp signed Ren & Stimpy pencil drawing, dated 2021 in the artist's own hand.
- Photograph coverage now stands at 730 items.
- Jim Davis Garfield letter dated 7 November 1996, read off the letter itself — the first album piece to carry a date at all; the other 168 have none.
- Fred Claus pass dated 4 November 2007 from the invitation itself, replacing the purchase date on the record. Notes reduced to *advance screening pass, admits two*.
- Masthead and DOS boot banner read *Collection Browser v2.5*.
- The archive is now called `index.html`, and `jareds-archive.html` is gone. The admin page, the changelog and every relative path have always assumed `index.html` at the far end, so the old name only survived as a rename done from memory at deploy time &mdash; and as a second copy that could quietly fall out of step with the first.

**Data**
- Four chunks appended to `photos.js`, the nineteenth through twenty-second, keyed by item id as before. Everything shot to 320 px on the long edge, JPEG quality 72, transparency flattened to white — 7–14 KB apiece, in line with the existing entries.
- `photo` flag raised from 0 to 1 for the eleven ids in both the archive and the admin page. No records added, no markup or script touched.

**Dates**
- Dates now display as *November 7, 1996* rather than the raw `1996-11-07`, in the item record and in the admin table alike. Storage stays ISO so sorting is unaffected; partial dates degrade gracefully — a bare year shows as the year, a year and month as *May 2019*.

**Fixes**
- Restored roughly 180 lines removed in error while the high-resolution tier was being rewired &mdash; `PAGE_SIZE`, the placeholder icon set and its matching rules, the eBay candidate chain, the status-line counter and the image retry wiring all went with the block that was replaced. The catalogue failed to build at all: *PAGE_SIZE is not defined*. Restored verbatim from v2.3 and verified by booting the whole script against a stub DOM, which now renders the grid rather than throwing.
- `photos.js` is now requested as `photos.js?v=2.5` from both pages. The filename never changes between releases, so browsers were serving the cached copy against a freshly uploaded catalogue — any photograph that moved to a different item id sat on *LOADING PHOTO* indefinitely while everything else appeared normal. Bump the query string on each release.

**Corrections**
- `auto171` "Bryan Williams" was the Bryant Gumbel signed Seinfeld 8x10 already catalogued as `inv9` — the binder note read *two men shaking hands, signature not legible*, which is Gumbel and Seinfeld. The album entry has been folded into the inventory record: photograph rekeyed to `inv9`, duplicate removed, and the unidentified-signature note dropped now that the piece has a name.
- `auto11` "Fred Haise" is Ray Charles — the album photograph is the signed portrait at the piano, captioned RAY CHARLES. Renamed and moved from *Space* to *Music*; the printed-name note, which read FRED W. HAISE, JR., went with it. The two genuine Haise signatures in the collection are unaffected, though only one now remains under that name.
- `auto12` "Ray Charles" is Jerry Lee Lewis and Dennis Quaid — two men at a piano, from the *Great Balls of Fire!* period, both signatures on the print. Renamed, kept under *Music*, printed-name note cleared. The binder pass had mislabelled this pair and `auto11` in tandem; the collection now holds one Ray Charles rather than two.
- Catalogue count 815 → 814. Autographs 183 → 182; original collection 198 → 197, then 195 with the two removals below. Photograph coverage holds at 730, now of 814.

**Admin page** (kept local, not uploaded)
- **Add a new item.** Name, category, sub-category, condition, brand, date, price and an original-collection flag, plus a photograph picked from disk &mdash; resized to 320px and JPEG'd in the browser, exactly as the catalogue photos were. New items land in the same table as everything else, so they can be renamed, recategorised, boosted or hidden immediately. They are written to `overrides.js` as `__NEW_ITEMS`; the archive maps them onto its own field names on load.
- **Export photos.js.** The page already holds every photograph in memory, so it can now write the whole file back out with any new ones folded in, chunked at roughly 600 KB. Adding an item therefore means exporting both files and bumping the `?v=` on the photos.js tag.
- **Site metrics.** A static file cannot count its own visitors &mdash; something has to receive the hit, so the archive now carries a GoatCounter tag. It counts a pageview on load and fires an event whenever an item record is opened, under `/item/<id>` with the item's name as the title. No cookies and no personal data: a path, a title, a referrer. The admin page opens the dashboard in a new tab rather than framing it: it is kept off the server, and GoatCounter only permits framing from a whitelisted domain. Every call is wrapped, so a blocked or missing counter is a no-op rather than an error.

**Photographs at two sizes**
- Large versions now live as ordinary files in a `hi/` folder, named by item id &mdash; `hi/auto120.jpg`. 187 of them, 32.5 MB in total, at 1600px on the long edge.
- No manifest and no sidecar to rebuild. The record view probes `hi/<id>.jpg` when it opens; if the file is there the pane swaps up to it once decoded, and if it isn't, the 320px version simply stays. Adding a high-resolution photograph is now nothing more than dropping a correctly named JPEG in the folder &mdash; no export step, no code change.
- Records open on the small version immediately, so there is no empty pane and no flash while the large file loads. A missing file is a silent 404. Each image is cached separately by the browser, and only the opened item's file is ever fetched.
- This replaces `photos-hi.js`, which is deleted. Base64 inside JavaScript added a third to every file, made all of them download together, and would have rewritten a multi-megabyte blob in git history on every edit &mdash; workable for fourteen items, not for a binder of autographs.
- The rest of the catalogue cannot be upgraded this way. The other ~700 photographs exist only at the size they were embedded at in v2.0; the eBay originals are gone and the binder scans were downsampled on the way in. Enlarging those would invent detail rather than restore it.

**Autographs**
- The whole binder is in: 173 scans, 187 files in `hi/`, 32.5 MB, all at 1600px. Every autograph record in the catalogue now has a full-size version behind its thumbnail.
- The leading number in each scan's filename is its catalogue id, which made the matching exact rather than a judgement by eye &mdash; 1 to 173, no gaps and no duplicates.
- Four scans had no `auto` record: 27, 98, 171 and 172. All four turned out to be pieces catalogued on the inventory side instead, and each was identified by matching the scan against the stored thumbnail rather than by guesswork &mdash; 27 is the Mitch Hedberg ticket (`inv13`), 98 is Mark Hamill (`inv12`), 171 the Gumbel/Seinfeld 8x10 (`inv9`), 172 the Daniel Stern (`inv10`). Three of the four correlate perfectly with the thumbnail already on file, so the identification is not a judgement call. 171 is the piece merged earlier this version, which the album numbering independently confirms.

**Browsing**
- The original collection now leads the **All** tab on first load. Any deliberate action &mdash; a category, a sort, a search, a toggle &mdash; drops the pinning for the rest of the session, so it never fights what was actually asked for.
- Johnny Knoxville / Steve-O skateboard and the Taking on Tyson gloves removed from the original collection. It now stands at 195 items.

**Genres**
- *Notable Figures* renamed **Misc**.
- *Politics & News* renamed **Politics**.
- Geraldo Rivera moved from Politics to Misc.
- Autographs now read: Television 62, Film 52, Comedy 19, Music 15, Animation 12, Sports 7, Politics 5, Misc 5, Space 5.

**Notes**
- Each entry in `photos.js` is a JSON *string* rather than an object, parsed one per tick so a phone never blocks on a single large parse. Adding photographs means appending another string to the array, not merging into an existing one; chunks are best kept under roughly 600 KB.
- The I-Spy pass is recorded as *Famke Janssen – Eddie Murphy*, but the artwork bills Eddie Murphy and Owen Wilson. Left as found.
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
