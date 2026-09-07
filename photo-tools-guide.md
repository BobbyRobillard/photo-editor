# Photo tools: how to use it

This is the browser tool that resizes, trims, and converts client photos. It runs on your computer. Nothing uploads anywhere, so client photos never leave your laptop.

---

## Open it

Double-click `photo-tools.html`. It opens in Chrome and it is ready to use.

Keep it somewhere you can find it, like your desktop or a Tech & Mech folder. It is one file, nothing to install.

## Where this fits in the batch workflow

Order matters. Run the steps in this order or you will lose the slugs ChatGPT gives you.

1. **Convert first.** If the client sent iPhone photos, convert HEIC to JPG in this tool before anything else. ChatGPT cannot read HEIC.
2. **Then run Phase 1 and 2 in ChatGPT.** Audit, then the manifest with slugs and alt text. Rename the files on disk to match the approved manifest.
3. **Then resize here.** The tool keeps your filenames and adds only a size tag, so `tree-removal-wide-titusville-01.jpg` becomes `tree-removal-wide-titusville-01-1600x900.jpg`.

If you resize before naming, every output is named after the camera file and the manifest is useless.

**One thing this tool does not do:** it strips all EXIF, including GPS, which is what we want. But it cannot write IPTC title or description. If a client needs those fields, that is a separate step and Chad will tell you.

---

## The five-minute version

1. Drag photos into the left panel.
2. Click **Auto-sort by shape**.
3. Click a group, set its recipe on the right.
4. Check a few photos in the filmstrip, fix any bad crops by dragging.
5. Pick **Save to**, then **Run all groups**.

---

## The parts, and when you need each

### Photos (left)

Drop the whole client folder in at once. 500 photos is fine. Thumbnails load as you scroll, so give it a moment on a big batch.

### Groups (left)

A group is a set of photos that all get the same treatment. Every photo starts in one group called "All photos."

**Auto-sort by shape** splits them into Portrait, Landscape, and Square, and gives each sensible starting sizes.

*Why you need this:* a 9:16 phone video still and a 16:9 drone shot should not get the same output size. Cropping a tall portrait into a wide banner throws away most of the photo. Sorting by shape means each shape gets sizes it actually fits.

To move photos between groups: click a thumbnail to select it, Ctrl-click to add more, Shift-click for a range, then use **Move selected to** above the filmstrip. The colored bar on each thumbnail tells you which group it is in.

Make your own groups when shape is not the real difference. Example: a PK job where before-and-after pairs need one treatment and standalone shots need another.

### Recipe (right)

Each group has its own recipe with three steps that run in this order: **Trim → Resize → Output**.

**Trim** removes white and transparent borders from the outside edges.

*When you need it:* logos, product cutouts, screenshots with white margins, anything a client exported with padding around it. **Leave it off for normal photos.** A photo with a bright overcast sky along the top edge can lose the sky, because the tool cannot tell "white background" from "white sky." If that happens, drop the tolerance to 4.

**Resize** has two modes.

*Crop and fit to exact sizes* gives you exact pixel dimensions, cropping to fit. Use this for anything going on a website, a GBP post, or social. Check as many sizes as you need; each one gets its own subfolder.

*Scale by percent* just shrinks the whole photo, no cropping. Use this when a client sends 12MP originals and you need them smaller for email or a proof sheet without changing the framing.

*Keep this part of the photo* is set to Smart, which finds the busiest area of the frame. It is right most of the time and wrong on maybe one in ten. That is what the crop window below is for.

*Never enlarge small photos* stays checked. Blowing up a small Facebook download makes it look worse, not better.

**Output** is always on.

*Format:* JPG for photos, PNG when you need transparency, WebP if the site wants it. **Same as input** keeps whatever came in.

*File names:* leave on **Keep original names** in almost every case, since that is what protects the slugs from the manifest. Use *Rename in order* only when there is no manifest and you just need `photo-001`, `photo-002`.

**Presets** save a whole recipe under a name so you can reuse it on the next client. Save one per client once you have their sizes dialed in. They are stored in this browser on this laptop, so they will not follow you to another machine.

### Preview and the crop window (center)

The left image is the original with a bright window over it. That window is what gets kept. The right image is the result.

**Drag the window** to pick a better part of the photo. Arrow keys nudge it, Shift plus arrow moves it further. A gold dot appears on that thumbnail so you can see which photos you have adjusted. **Back to automatic** undoes it.

*When you need this:* the smart crop centers on detail, not on meaning. On a tree removal shot it might center the crane and cut off the house. On a harvest photo it might cut the tag. Click through the filmstrip, fix the handful that look wrong, leave the rest.

If a group has several sizes, use the **Size** dropdown to check each one, because each has a different shape and its own crop position.

*These positions are only in memory.* Refresh the page and they are gone. Do a batch in one sitting.

### Save to (bottom right)

**A folder you pick** writes each photo as it finishes. Best for big batches. You get a folder per group, with size subfolders inside.

**One zip file** builds everything and hands you one download. Use it if you are sending the whole set to someone.

### Run all groups (top right)

Processes every group with its own recipe. The log shows every file written, and flags anything skipped. Read those flags. "Could not open" usually means a corrupt download worth chasing.

---

## Quick answers

**A photo came out sideways.** Tell Chad. It is a bug in how the tool reads rotation, not something you can fix in settings.

**Some files were skipped.** The log says why. Usually a broken download.

**The whole thing feels slow.** HEIC is slow to decode, a couple of seconds per photo. Convert HEIC in its own pass, then work from the JPGs.

**Nothing happens when I click Run.** Chrome is waiting on you to choose where to save. Look for the folder or save window, it sometimes opens behind the browser.

**My preset disappeared.** Presets live in this browser on this laptop. A cleared browser or a different computer will not have them.

**I need one photo cropped differently from the rest of its group.** Drag its crop window. That is exactly what it is for.
