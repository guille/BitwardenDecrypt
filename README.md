# BitwardenDecrypt

Fork of https://github.com/GurpreetKang/BitwardenDecrypt with personal patches. For all credit, see the original repo. My changes are commented in the main Python file and are also GPLv3.

## Web UI

The [docs directory](/docs) includes a web version, which is also [deployed on Github Pages](https://guille.github.io/BitwardenDecrypt/). Upon uploading an encrypted JSON and entering the password, it will decrypt the JSON and allow you to view/download it.

It works entirely client-side, and it bundles argon2 (`argon2-bundled`, version `1.18.0`) so it should work without connection once the page has loaded.

That being said, you (probably!) don't know me and uploading your encrypted vault _and_ the password to unlock it to an untrusted website is very likely a bad idea. **I take no responsibility** for any issues or leaks that may happen and actively recommend you do not use the web version.

For the record, this is the external code:

```sh
curl -L "https://unpkg.com/argon2-browser/dist/argon2-bundled.min.js" > argon2-bundled.min.js
```

You should evaluate:
- How likely am I to be misleading you.
- How likely is it that the unpkg.com source was compromised when I ran the command.
- How likely is it that the my computer or this repo is compromised.

Personally, I hope to never need this tool, but after a very untimely and mishandled [Bitwarden incident](https://status.bitwarden.com/issues/684ef49610bdfb6d843aa854) locked me out of my vault when I needed it I figured I needed an emergency access hatch that I knew was safe-ish.

The whole HTML file is AI generated with only minor tweaks. Pretty much slop, but it works for my exports.
