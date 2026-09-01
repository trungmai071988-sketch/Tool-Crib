# Tool Finder

Search the tool crib by brand, type, diameter, LOC, coolant-thru, or EDP#.

## Files in this repo

| File | What it is | How often it changes |
|---|---|---|
| `index.html` | The app: layout, search, buttons. **No tool data.** | Only when you change how the app looks or works |
| `tools.json` | The catalog. One tool per line. | Every time you add or fix tools |
| `sct-reference.png` | SCT thread mill reference image | Rarely |

The tool data used to live inside `index.html`. It doesn't anymore. That is the whole point: replacing
`index.html` can no longer wipe out the catalog, because the catalog isn't in that file.

## Adding tools

1. Open the site, go to **Add tool** or **Import**, and add what you need.
   Anything you add is saved on your device only.
2. Go to **Import → Download tools.json**.
3. On GitHub, open the old `tools.json` → pencil icon isn't practical for a file this size, so use
   **Add file → Upload files**, drop in the new `tools.json`, and commit. It replaces the old one.
4. Refresh the site. Everyone now sees the new tools.
5. Back in the app, **Clear local changes** so your device isn't holding a second copy.

## Changing the app

Edit `index.html` freely. Do not paste tool data into it. `tools.json` is untouched by that edit,
so nothing can go missing.

## Record format

```json
{"id":"seed_0","brand":"MA Ford","type":"Series CXDSS Drill","diameter":".1200","edp":"06616","price":"","loc":"0.787","neckdia":"","coolant":"No","specs":"","notes":"CXDSS1200AP, OAL 2.44\""}
```

Every record needs a unique `id`. `brand`, `type`, `diameter`, and `edp` should always be filled in;
the rest can be empty strings.

## Note

`tools.json` is loaded over the network, so opening `index.html` by double-clicking it on your PC
will show a load error. Use the GitHub Pages address.
