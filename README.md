# PS5 firmware 14.22 module host

A GitHub Pages-compatible website that checks a list of separately supplied browser exploit modules, skips modules that do not explicitly declare firmware 14.22 support, and attempts eligible scripts in order.

**No verified 14.22 jailbreak or exploit is included.** The manifest is empty until you supply a genuine compatible browser exploit. This is not a firmware bypass and cannot make patched exploits work. Browser pages cannot directly trigger PS2 Classic / Luac0re game entry points.

## Deploy to GitHub Pages

1. Upload `index.html` and `modules.json` to the root of a GitHub repository.
2. In repository **Settings → Pages**, choose **Deploy from a branch** and select the root of your default branch.
3. Open the published site on your console, if accessible.

## Add a compatible browser module

Put a trusted browser-based JavaScript module in `exploits/`, then add it to `modules.json`:

```json
[
  {
    "name": "Example compatible module name",
    "file": "exploits/module.js",
    "browser": true,
    "supportedFirmware": ["14.22"],
    "timeoutMs": 15000
  }
]
```

**This is only a manifest example, not a claim that a compatible module exists.** Do not declare firmware compatibility without evidence. Scripts can use `window.ps5ExploitResult = {success: true}` to *report* success, but this is self-reported and is **not independent proof** of a jailbreak.

## Limitations

- The timeout limits waiting for a script **to load**; it cannot terminate running JavaScript or recover a crashed console.
- Sequential execution is best-effort: an exploit that freezes the browser prevents further attempts.
- A failed exploit may leave console state changed. Reload or restart before further testing if advised by the exploit author.
- A website cannot independently validate kernel or hypervisor access without a trusted verification method supplied by the actual exploit.
