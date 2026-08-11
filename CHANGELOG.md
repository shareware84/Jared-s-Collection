# C:\JARED\COLLECTION — Changelog

---

## v3.1

**Autographs**
- Chevy Chase (`auto186`, Comedy) — color portrait in a Bushwood Country Club cap, the club from Caddyshack, signed in blue marker across the sweater. **Received TTM on August 11, 2026.** The first record in the catalog to note a through-the-mail return.
- **Provenance.** The record pairs the print with a post from Chase's verified Facebook page, May 16, 2024: he is sitting at a table covered in copies of this exact portrait, holding one up mid-signing, with a stack of blanks beside him. Same print, same blue marker, same placement across the sweater. It establishes that he signs this photograph himself and in quantity, which is what a TTM return depends on. It is a post about the practice rather than about this copy, and the two are two years apart — which is as far as any TTM provenance can reasonably go.
- The caption thanks everyone who signed his name for him that day. That is a joke at the expense of ghost-signing accusations, made in a photograph of him doing the signing, and is recorded as such so nobody reads it later as a disclaimer.
- Confidence raised to **High** on the strength of the post. The authentication flag is still empty: no certificate, no witness, and the piece was never submitted anywhere — high confidence and third-party authentication are different claims, and the catalog keeps them apart.
- Original collection, since it was obtained rather than bought in.
- Genre **Comedy** rather than Film. The photograph is Caddyshack-themed, which argues the other way; the filing follows the person over the prop, as Conan O'Brien and Don Rickles already do.
- Photographed on a countertop rather than scanned. The print was deskewed to its own edges and the surface cropped out, so the record shows the object and not the kitchen.
- The full-size image is a two-panel composite — the print beside the post — since the catalog shows one photograph per record, the same approach the Blockbuster card's front and back already use. The card thumbnail stays the print alone. At 2283px it exceeds the 1600px object ceiling for the reason the article scans do: the caption and the date have to be readable or the panel proves nothing.
- **Direct link.** The record links out to the post itself, opening in a new tab under the same `noreferrer` policy the page already sets, so Facebook is told nothing about where the click came from. The `?mibextid=` parameter was dropped from the URL — it is share-tracking that encodes who passed the link along, and it is not part of the address.
- The link is a second copy of the evidence, not the evidence. Posts get deleted and accounts get renumbered; the composite in `hi/` is what survives that.
- Item records gained an optional `link` field, rendered beside the existing eBay-image link rather than replacing it. `auto186` is the only record using it so far.
- **Screenshot trimmed before it went in.** The status bar, the comment thread and the reply box are cropped away — the box carried the account holder's full name and the thread carried a commenter's, and neither belongs in a public file.
- Autographs 196, catalog 861 records (859 live), photograph coverage 777.

---

## v3.0.1

A correction release. v3.0 was assembled but never deployed cleanly; everything below is a fix to that build rather than new work, and the v3.0 notes have been corrected in place where they described something the files did not actually do.

**Packaging**
- `admin.html` and `rotate-review.html` ship inside the archive, but they are local tools and must not be uploaded. `admin.html` carries the purchase price of every item — the figures the public file deliberately withholds, keeping only the `priced` flag that drives the blurred placeholder. `index.html` is clean; the archive is not. Uploading the folder wholesale therefore publishes every price paid, which is the one way this release can go wrong. The upload set is `index.html`, `photos.js`, `overrides.js`, `doom-v12.jsdos` and `hi/`.
- `rotate-review.html` now requests `photos.js?v=3.1` as well, so the rotation tool and the catalog can never disagree about which photographs they are looking at.

**Fixes**
- `inv3` "Mike Tyson Boxing Gloves from Taking on Tyson" had kept its original-collection flag. v3.0 recorded the gloves as removed from the original collection, but the change landed on `inv131` "Taking on Tyson Boxing Gloves" only, and the two records look like the same object. Flag cleared on `inv3`; whether the pair should be merged the way `auto171`/`inv9` were is left open rather than decided here.
- Three `photos.js` chunks exceeded the ~600 KB guideline the file's own note sets — one at 1,065 KB across 46 items, which is the case the guideline exists to prevent, since a chunk is parsed whole in a single tick. Split at export into 27 chunks, none above 600 KB. Byte-for-byte identical content: same 776 keys, same values, same order.
- US spelling sweep completed. v3.0 claimed it and left `Synthesised`, `Centre` and `off-centre` in the `index.html` comments, `colours` in one item note, and `recategorised`, `minimising`, `FM-synthesised` and `off-centre` in this file. Fixed. Article transcripts are excluded from the sweep along with item names — they are records of what was printed, not prose written here, so `amongst`, `towards` and `theatre` stay as the papers set them.
- `photos.js?v=3.1` on both pages; masthead and DOS boot banner read *Collection Browser v3.0.1*.

**Counts**
- The v3.0 notes were written as work went along and their totals stopped matching the data partway down: a catalog count of 814 above entries that end at 860, and photograph coverage given as 730 when the flag is set on 776. Every figure in the v3.0 section below has been recomputed from the shipped files rather than carried forward.
- **860 records, 858 live.** `overrides.js` hides `inv309` and `inv255`, so the browsable catalog is two smaller than the data file. Worth stating outright, because a hidden item is invisible to the page but present in every count taken off the JSON.
- **Original collection is 238 records, 237 live** — not 195. The filter is a plain truthy check on `orig`, and all 28 Published Work pieces carry the flag, which is defensible on its own terms but was never recorded. Excluding those, 209.

**Still open**
- Search covers name, brand, raw category and transcript, but not `note`. Part numbers, inscriptions and caveats like *Disc 2 of 2* are therefore unreachable — the same argument that put transcripts in the index.
- The year-month display branch (*May 2019*) has no data exercising it: every stored date is a full ISO date or a bare year.
- Misc holds four records, three of which `overrides.js` moves elsewhere. Misc and Audio/Media are each one item in the live catalog.

---

## v3.0

**Content**
- Photographs added for the last nine cataloged items that had no image of their own: the sealed 3DFX Voodoo 3 3000, the iPad 6th generation, the Braava 380, the GTX 1070 Founders Edition, the Emerson 13" TV/DVD combo, the Rift + Touch bundle, the Apple Watch Series 2, the Klydoclock and the i7-7700.
- Photographs added for the two advance screening passes: I-Spy (2002) and Fred Claus (2007).
- Photographs added for the Panasonic KXL-D720 CD-ROM drive; replacements for the two Sony Magic Link entries (the loose unit and the sealed headset bundle) and the Quest 2 silicone cover.
- Full-size photograph added for the Sony Pictures 2003 Preview Kit binder (`inv181`) — the binder open, showing the Geoffrey Ammer letter and the CD-ROM in its sleeve. The card keeps the closed-binder shot, so the record now opens onto a different and more informative view of the same object.
- Photograph added for the Bob Camp signed Ren & Stimpy pencil drawing, dated 2021 in the artist's own hand.
- Photograph coverage stands at **776 of 860 records**.
- Jim Davis Garfield letter dated November 7, 1996, read off the letter itself — the first album piece to carry a date at all; the other 168 have none.
- Fred Claus pass dated November 4, 2007 from the invitation itself, replacing the purchase date on the record. Notes reduced to *advance screening pass, admits two*.
- The archive is now called `index.html`, and `jareds-archive.html` is gone. The admin page, the changelog and every relative path have always assumed `index.html` at the far end, so the old name only survived as a rename done from memory at deploy time &mdash; and as a second copy that could quietly fall out of step with the first.

**New category: Published Work**
- A thirteenth category for Jared's own printed journalism, filed under the code BYLINE and sub-divided by title with the chip row reading *Published in:* &mdash; the same mechanism Autographs uses for genre and Vintage Computing for software versus hardware. **28 pieces: 17 from Outloud Magazine, 10 from the Purchase College Dispatch, and one that names no publication.**
- Outloud: reviews of Big Fish, Shrek, Traffic, The Mummy Returns, Garden State and the Vanilla Sky soundtrack; the Sizzling Summer Movies preview and a second summer preview built around cartoon adaptations; a Mitch Hedberg feature written around a Miami Improv set; the Broadway musical *Movin' Out*; VH1's *I Love the 90's*; a full-page Avenue Q spread; The Beatles Anthology; a Kill Bill Vol. 2 review; an Austin Powers: Goldmember preview written while the film was still in pre-production; and interviews with Jane McGregor for *Slap Her... She's French* and with Eric Jungmann and Chyler Leigh for Not Another Teen Movie. The McGregor piece carries a photograph of the writer with her, captioned in the paper itself.
- The Dispatch: the Beatles Anthology review (Volume 7, Number 5, February 16, 2005), Avenue Q (Volume 6, Number 6, February 18, 2004), the Netflix and Blockbuster Online report (Volume 7, Number 9, May 4, 2005), Kill Bill Vol. 2, the fifth season of *Curb Your Enthusiasm*, *Maria Full of Grace*, the 20th-anniversary Game Boy Micro, the Pete & Pete DVD, and two pieces on jazz vocalist Joanne Lawry — one written as a profile, one as news.
- Unattributed: a second Kill Bill Vol. 2 review (`inv669`). The clipping names no publication, so it is left unattributed rather than assumed.
- Three subjects exist in two versions each &mdash; Avenue Q, the Beatles Anthology and Kill Bill Vol. 2 were written up separately for Outloud and for The Dispatch. They are filed as distinct pieces rather than duplicate scans, because they are.
- The Vanilla Sky entry reviews the soundtrack rather than the film, which makes it the only record of its kind in the collection.
- `inv663` began as a fragment &mdash; an orphaned photograph and caption with no body text and nothing on the scan naming the publication. The article turned up, so it is now the full Curb review with both photographs that ran alongside it (Larry David, and Purchase alum Susie Essman in character), attributed to The Dispatch and titled with its actual headline.
- Big Fish (`inv654`) gained its second column, which carries the closing paragraphs and the Buscemi still.
- Clippings scanned in parts &mdash; the McGregor interview, the summer preview, Kill Bill &mdash; are stacked into one image per piece, matched in width, since an article cut across two scans is still one article.
- Dates are exact where the masthead carries one and year-only where it doesn't; those years are inferred from the films' release dates rather than read off the page, which is worth knowing before treating them as citations.

**Published Work: legibility**
- The article scans are not squeezed to the 1600px ceiling the rest of the catalog uses. Text is not a product photograph &mdash; a review you can't read is not a record of anything &mdash; so these are stored at their native resolution up to 3000px. The Dispatch pages are 2400&times;3000, the Outloud spreads around 2100. The Mitch Hedberg PDF was re-rasterized at 450 dpi rather than 200, taking it from 1126px to 2530.
- **Transcripts.** Each article carries its text, read off the scan by OCR and shown under the item's fields in a scrolling panel. Column wraps and hyphen breaks are rejoined so it reads as prose rather than as a column dump.
- Search reaches the transcripts. A phrase from the body of a review will find the piece &mdash; previously only titles, publications and categories were searchable, which made the most searchable material in the catalog invisible to it.
- The heading says *read by OCR, may contain errors* rather than implying otherwise. Faded newsprint transcribes imperfectly and some words come through wrong; the scan above remains the record of what was actually printed.
- **27 of the 28 pieces carry a transcript.** The magazine Kill Bill review (`inv677`) does not: it is set as reversed-out white type on a dark ground across two columns, and every OCR pass returned text so interleaved and noise-ridden that publishing it would have been worse than publishing nothing. Recorded as having no transcript rather than a bad one.

**Privacy**
- Surname removed from the two item notes that still carried it, so it now appears nowhere in any file &mdash; not the records, not the transcripts, not this changelog. The notes describe the bylines without naming them.
- Surname blurred out of every byline in the Published Work scans. The word was located by OCR in each source and blurred at a radius scaled to the text height, then the scans were re-read to confirm it no longer resolves. First name left intact, so the pieces still read as bylined. Not every scan carried it; the Kill Bill still and the Curb photograph have no byline on them.
- The redaction is applied to the images themselves, not overlaid at display time, so it survives download, right-click and view-source.

**Autographs**
- Hugh M. Hefner & Christie Hefner (`auto185`, Misc) — a framed Playboy Enterprises one-year service anniversary certificate. Filed under Autographs as requested but at low confidence and with the authentication flag left empty: both signatures sit in the printed layout in a way that reads as part of the certificate artwork rather than ink applied afterwards. Worth checking against the glass before it counts as a signed piece.
- Don Rickles (`auto184`, Comedy), original collection — a 1995 Barnett Bank arts-sponsorship magazine advertisement, inscribed to Jared and signed across the page. An odd substrate for an autograph, and the second Rickles in the collection after the group page at `auto173`.
- Tara Strong & Meghan McCarthy (`auto183`, Animation) — a My Little Pony: Friendship is Magic promotional print from Discovery Family and Hasbro Studios, two signatures in red marker across the banner. Filed at medium confidence: the attribution is plausible on every count but neither signature is legible enough to confirm from the piece itself.
- Conan O'Brien (`auto182`, Comedy) — a childhood school portrait signed across the face in blue marker, sold with a GM Authentic Autos certificate of authenticity. **The signature is not genuine.** Recorded at low confidence with the authentication flag cleared, and kept in the catalog rather than removed: a collection that records what a piece actually is stays more useful than one that quietly drops its mistakes, and the certificate is itself part of the story.
- Two sports pieces: Pete Rose & Wade Boggs (`auto180`), a spring training photo signed by both, and Andre Dawson (`auto181`), a Florida Marlins photo inscribed with his nickname.
- Four more added from the binder: Alex Trebek (`auto176`, Television), Sal Governale & Richard Christy (`auto177`, Comedy), Drew Carey (`auto178`, Television) and Miles, the Denver Broncos mascot (`auto179`, Sports). The Trebek is inscribed "thanks for adding me to your collection"; the Stern pair is a SiriusXM still signed by both; Carey's is a Price Is Right photo signed in white marker; the Broncos piece is a Children's Hospital Colorado poster signed across the artwork.
- Two new entries, both original collection: Mason Gamble (`auto174`) and Mason Gamble & Walter Matthau (`auto175`). Warner Bros. publicity stills DM-613 and DM-10 from Dennis the Menace (1993), photographed by Theo Westenberger, each inscribed to Jared and signed by Gamble. Filed as two records rather than one because they are two distinct pieces, and the Matthau still would otherwise have been visible nowhere.
- Road to Perdition signed Tom Hanks press kit (`inv202`) moved from Press Kits to Autographs, genre Film, condition raised to Signed. The authentication flag was left empty rather than set. Its original category was already recorded as Press Kits/Autographs, so the move brings the browsing category in line with what the piece is.
- **Autographs stands at 195 records.** Press Kits 72.

**Other additions**
- VPR Matrix Device Drivers & Restore CD set (`inv653`, Vintage Computing / Software), August 7, 2026. Part numbers, versions and covered models recorded in the note. The restore disc is marked Disc 2 of 2, so the set is incomplete as an install path — worth knowing before anyone tries to rebuild the tower with it.
- VPR Matrix 1620 Pentium 4 desktop (`inv652`, Vintage Computing / Hardware), August 7, 2026. Goodwill tested stock — posts to BIOS, VGA video, 0.125 GB RAM, no hard drive, cosmetic damage. The specifications come off the refurbisher's label rather than a listing, so they are recorded in the note.
- Canon PIXMA TS6520 wireless inkjet printer (`inv651`, Electronics), bought August 5, 2026, with a product photograph at both sizes. The price lives in `admin.html` only; the public file carries the priced flag, which renders as the blurred placeholder. The source is only 1170px, so the full-size file is stored at its native resolution rather than upscaled to the usual 1600.
- Dr. Hibbert framed 3D wall art (`inv650`, Memorabilia) — a sculpted Simpsons relief in a gold shadow box, hands and forearm breaking out over the frame's inner edge.
- Nickelodeon The N promotional notebook (`inv649`, Memorabilia) — silver foil hand logo, the-n.com beneath, branded green pen still clipped into the spiral. Joins the The N blanket already at `inv129`.
- Blockbuster Video membership card (`inv648`, Memorabilia), original collection, dated to its issue on October 12, 2002. Front and back are composed into a single image, since the catalog shows one photo per record and a membership card without its back is half an object.
- Electronics 36, Memorabilia 30.

**Photographs at two sizes**
- Large versions now live as ordinary files in a `hi/` folder, named by item id &mdash; `hi/auto120.jpg`. 234 of them, 61 MB in total, at up to 1600px on the long edge for objects and up to 3000px for the article scans.
- No manifest and no sidecar to rebuild. The record view probes `hi/<id>.jpg` when it opens; if the file is there the pane swaps up to it once decoded, and if it isn't, the 320px version simply stays. Adding a high-resolution photograph is now nothing more than dropping a correctly named JPEG in the folder &mdash; no export step, no code change.
- Records open on the small version immediately, so there is no empty pane and no flash while the large file loads. A missing file is a silent 404. Each image is cached separately by the browser, and only the opened item's file is ever fetched.
- This replaces `photos-hi.js`, which is deleted. Base64 inside JavaScript added a third to every file, made all of them download together, and would have rewritten a multi-megabyte blob in git history on every edit &mdash; workable for fourteen items, not for a binder of autographs.
- The rest of the catalog cannot be upgraded this way. The other photographs exist only at the size they were embedded at in v2.0; the eBay originals are gone and the binder scans were downsampled on the way in. Enlarging those would invent detail rather than restore it.

**The autograph binder**
- The whole binder is in: 173 scans, all at 1600px. Every autograph record in the catalog now has a full-size version behind its thumbnail.
- The leading number in each scan's filename is its catalog id, which made the matching exact rather than a judgment by eye &mdash; 1 to 173, no gaps and no duplicates.
- Four scans had no `auto` record: 27, 98, 171 and 172. All four turned out to be pieces cataloged on the inventory side instead, and each was identified by matching the scan against the stored thumbnail rather than by guesswork &mdash; 27 is the Mitch Hedberg ticket (`inv13`), 98 is Mark Hamill (`inv12`), 171 the Gumbel/Seinfeld 8x10 (`inv9`), 172 the Daniel Stern (`inv10`). Three of the four correlate perfectly with the thumbnail already on file, so the identification is not a judgment call. 171 is the piece merged below, which the album numbering independently confirms.

**Corrections**
- `auto171` "Bryan Williams" was the Bryant Gumbel signed Seinfeld 8x10 already cataloged as `inv9` — the binder note read *two men shaking hands, signature not legible*, which is Gumbel and Seinfeld. The album entry has been folded into the inventory record: photograph rekeyed to `inv9`, duplicate removed, and the unidentified-signature note dropped now that the piece has a name.
- `auto11` "Fred Haise" is Ray Charles — the album photograph is the signed portrait at the piano, captioned RAY CHARLES. Renamed and moved from *Space* to *Music*; the printed-name note, which read FRED W. HAISE, JR., went with it. The two genuine Haise signatures in the collection are unaffected, though only one now remains under that name.
- `auto12` "Ray Charles" is Jerry Lee Lewis and Dennis Quaid — two men at a piano, from the *Great Balls of Fire!* period, both signatures on the print. Renamed, kept under *Music*, printed-name note cleared. The binder pass had mislabeled this pair and `auto11` in tandem; the collection now holds one Ray Charles rather than two.

**Genres**
- *Notable Figures* renamed **Misc**.
- *Politics & News* renamed **Politics**.
- Geraldo Rivera moved from Politics to Misc.
- Autographs now read: Television 64, Film 55, Comedy 22, Music 15, Animation 13, Sports 10, Misc 6, Politics 5, Space 5.

**Browsing**
- The original collection leads the **All** tab on first load. Any deliberate action &mdash; a category, a sort, a search, a toggle &mdash; drops the pinning for the rest of the session, so it never fights what was actually asked for.
- Johnny Knoxville / Steve-O skateboard and the Taking on Tyson gloves removed from the original collection.

**Dates**
- Dates display as *November 7, 1996* rather than the raw `1996-11-07`, in the item record and in the admin table alike. Storage stays ISO so sorting is unaffected, and the value is parsed as a string rather than through `new Date()`, so a date never slides a day backwards in a western timezone. Partial dates degrade gracefully — a bare year shows as the year, a year and month as *May 2019*.

**Data**
- Four chunks appended to `photos.js`, keyed by item id as before. Everything shot to 320 px on the long edge, JPEG quality 72, transparency flattened to white — 7–14 KB apiece, in line with the existing entries.
- `photo` flag raised from 0 to 1 for the eleven ids in both the archive and the admin page. No records added, no markup or script touched.

**Fixes**
- Three photographs were lying on their side and are now upright: the Empty Nest cast photo (`auto17`), the Sony Pictures 2003 Preview Kit binder (`inv181`) and the boxed HP C1405B keyboard (`inv287`). The last two were stored portrait when the objects are wider than they are tall. `auto17` was rebuilt from the original scan at both sizes; the other two exist only as 320px thumbnails, so those were turned in place.
- Orientation had to be judged by eye rather than read from the files: the scans came through Imgur, which strips EXIF, so every one of the 173 arrived with no orientation tag for the pipeline to act on. Photographs taken straight off a phone keep theirs and rotate automatically.
- Spelling standardized to US English across the changelog, the page copy and the code comments &mdash; catalog rather than catalogue, recognizable, centered, labeled, behavior. Item names and article transcripts are untouched, since those are records rather than prose, and `aria-labelledby` keeps its spec spelling. *(Completed in v3.0.1 — see above.)*
- Restored roughly 180 lines removed in error while the high-resolution tier was being rewired &mdash; `PAGE_SIZE`, the placeholder icon set and its matching rules, the eBay candidate chain, the status-line counter and the image retry wiring all went with the block that was replaced. The catalog failed to build at all: *PAGE_SIZE is not defined*. Restored verbatim from v2.3 and verified by booting the whole script against a stub DOM, which now renders the grid rather than throwing.
- `photos.js` is now requested with a version query string from both pages. The filename never changes between releases, so browsers were serving the cached copy against a freshly uploaded catalog — any photograph that moved to a different item id sat on *LOADING PHOTO* indefinitely while everything else appeared normal. Bump the query string on each release.

**Admin page** (kept local, not uploaded)
- **Add a new item.** Name, category, sub-category, condition, brand, date, price and an original-collection flag, plus a photograph picked from disk &mdash; resized to 320px and JPEG'd in the browser, exactly as the catalog photos were. New items land in the same table as everything else, so they can be renamed, recategorized, boosted or hidden immediately. They are written to `overrides.js` as `__NEW_ITEMS`; the archive maps them onto its own field names on load.
- **Add a high-resolution photo.** Pick an item, pick a full-size image, and the page hands back exactly the file that belongs in `hi/` — named `<id>.jpg`, resized to 1600px at quality 82, the same treatment the binder scans had. A browser can't write into a folder on the server, so moving the file is the one manual step; there is nothing to export and no code to change. Optionally the 320px card thumbnail is regenerated from the same source at the same time, so the card and the record never disagree.
- **Export photos.js.** The page already holds every photograph in memory, so it can now write the whole file back out with any new ones folded in, chunked at roughly 600 KB. Adding an item therefore means exporting both files and bumping the `?v=` on the photos.js tag.
- **Site metrics.** A static file cannot count its own visitors &mdash; something has to receive the hit, so the archive now carries a GoatCounter tag. It counts a pageview on load and fires an event whenever an item record is opened, under `/item/<id>` with the item's name as the title. No cookies and no personal data: a path, a title, a referrer. The admin page opens the dashboard in a new tab rather than framing it: it is kept off the server, and GoatCounter only permits framing from a whitelisted domain. Every call is wrapped, so a blocked or missing counter is a no-op rather than an error.

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
- The status bar reported a negative number of items without photographs. It was subtracting both the stored-photo and eBay-link totals from the item count, double-counting everything that had both — by now nearly the whole catalog.

**Notes**
- DOOM's executable and WAD must come from the same release. A v1.1 engine looks for a split `STABARL`/`STABARR` status bar, which later WADs replaced with a single `STBAR`, and the mismatch stalls startup.

---

## v2.2

**Admin page**
- New `admin.html` for editing the catalog without a rebuild. Change an item's category, sub-category, name or display order, or hide it entirely, then export an `overrides.js` file to upload alongside `index.html`.
- Search by name, filter by category, or narrow to only-edited, only-hidden, or only-without-photos.
- Thumbnails shown for every item so you can see what you're moving.
- Non-destructive: deleting `overrides.js` reverts everything.

**Browsing**
- New **Original collection** toggle in the toolbar, covering all 183 autographs plus the 15 other pieces marked as such — 198 items in total. Implemented as a separate flag so the *Signed* condition on autographs is preserved rather than overwritten.

**DOS screen**
- Pressing **S** during the boot sequence skips straight to the archive. Undocumented, and limited to the POST phase so it doesn't interfere with typing at the prompt.

**Content**
- Photographs added for the Puppy Bowl X signed football (dated to its February 2, 2014 premiere), the Daily Show notebook, the Mini Nickelodeon pillow and the Sony Pictures 2003 Preview Kit binder.
- Every eBay listing in the catalog now has a photograph — the last dead links, the King of the Hill press kit and the sealed Flight Simulator 5.1, were both filled.
- Several low-resolution eBay thumbnails replaced with proper shots.

---

## v2.1

**Browsing**
- Shuffle now applies inside every category, not just the combined view, and reseeds each time you switch tabs or sub-filters — a different order every visit.
- Items with photographs always sort ahead of those without, in every category and every sort mode.
- Default page size raised from 48 to 75 items.
- On the **All** tab, recognizable material (autographs, films, games, TV, memorabilia) is weighted toward the top; reference software, utilities and bare hardware sink toward the bottom.

**Categories**
- **Vintage Computing** split into *Software*, *Hardware*, *Microsoft Home*, *Maxis* and *LucasArts*, in that fixed order.
- Microsoft Home widened from titles that literally say it to the whole product line that carried the logo — Exploration series, Encarta, Cinemania, Creative Writer, Scenes, Entertainment Packs, Flight Simulator and the rest. Microsoft's business and OS releases deliberately excluded.
- **Laserdisc** and **VHS** grouped by series where two or more titles exist (X-Files, Beavis & Butt-Head, Doug), everything else under *Films*.

**Detail view**
- Item records are wider with a much larger image pane.
- The ✕ on every window is properly centered — it was drifting off-center on iOS.
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
- Photos split into a companion `photos.js` file, cutting the page itself from 8.25 MB to under 450 KB. Images stream in behind the catalog in chunks so phones stay responsive.
- Item-specific placeholder icons drawn for items with no photograph — televisions, VR headsets, monitors, cartridges, cels and about twenty more, matched from the item name.

**DOS boot screen**
- The archive now opens on a black screen running a BIOS memory check. Type `JARED.EXE` at the prompt to enter.
- Working command line: `DIR`, `HELP`, `TYPE README.TXT`, and a hidden `HAHA.EXE`.
- FM-synthesized startup chime, generated in the browser rather than sampled.
- Minimizing the archive returns to the DOS shell with its scrollback intact.

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

- Initial catalog built from the household inventory spreadsheet — 648 items across Vintage Computing, Vintage Gaming, Autographs, Press Kits, Laserdisc, VHS, DVD, Electronics, Memorabilia and Trading Cards.
- Search, category tabs, sort by date, name and price.
- Item detail view with condition, publisher, location and acquisition date.
- Photographs loaded live from the eBay links recorded in the spreadsheet.
