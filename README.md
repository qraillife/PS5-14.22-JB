# PS5 14.22 Exploit Host — module scaffold

This package provides a website launcher, not a jailbreak.

## GitHub Pages
Upload index.html, modules.json and the exploits folder to the root of your GitHub repository. Enable Pages from the main branch, root directory.

## Adding a verified module
Only add modules independently verified for your target firmware and browser entry point. The manifest is deliberately empty because no verified module is bundled.

Example manifest entry format (illustrative only, do not use without a real compatible module):

```json
[{"name":"Verified module name","file":"exploits/verified.js","browser":true,"supportedFirmware":["14.22"],"timeoutMs":15000}]
```

A module's success flag is a claim, not independent proof of a kernel jailbreak. Browser JavaScript cannot automatically invoke Luac0re's PS2 Classic entry point.
