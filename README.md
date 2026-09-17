# Matine & Co Accountants – website

A one-page static website for Mhamed Matine, certified accountant and tax adviser at 9 Bell Street,
just off Edgware Road, London NW1. No build step, no frameworks: plain HTML and CSS, so it can be
hosted anywhere for free. It is set up to be published from the `Mco-aco` GitHub account at
https://mco-aco.github.io/.

## Files

| File | What it is |
|------|------------|
| `index.html` | The page. All the wording and contact details live here. |
| `styles.css` | Colours, fonts and layout. |
| `logo.png` | The logo with its background removed. |
| `favicon.png`, `apple-touch-icon.png` | Browser tab and phone home-screen icons. |
| `matine.vcf` | The "Save contact to your phone" card. Keep it in step with the details in `index.html`. |
| `.nojekyll` | Tells GitHub Pages to serve the files exactly as they are. |

## Editing the details

Open `index.html` in any text editor. The phone number appears in the header, the hero button, the
services note and the contact section, so search for `020 8087 4606` and change every copy.
The email address and the office address work the same way (search for `Bell Street`).
The structured-data block near the top of the file (the `application/ld+json` script) should match too;
it helps Google show the business correctly.

## Previewing on your computer

Double-click `index.html`, or run this in the folder and open http://localhost:8000:

```
python3 -m http.server
```

## Publishing on GitHub Pages (free hosting)

The site lives in the `Mco-aco` GitHub account. Naming the repository `Mco-aco.github.io` gives the
site the short address https://mco-aco.github.io/, which the page's link-preview tags and the vCard
already use.

1. Sign in to github.com as `Mco-aco` and create a new **public** repository called
   `Mco-aco.github.io`. Leave it empty (no README, no .gitignore, no licence).
2. If somebody else will push from their own computer, add them under
   **Settings → Collaborators → Add people**. They accept the emailed invitation and can then push
   with their own GitHub login. The alternative is to push with a personal access token created in
   the `Mco-aco` account (**Settings → Developer settings → Personal access tokens**), entered as the
   password when git asks.
3. In this folder, run:

   ```
   git push -u origin main
   ```

   The remote `origin` already points at `https://github.com/Mco-aco/Mco-aco.github.io.git`.
4. On GitHub open the repository, then **Settings → Pages**. Under *Build and deployment* choose
   **Deploy from a branch**, branch **main**, folder **/ (root)**, and save.
5. After a minute or two the site is live at https://mco-aco.github.io/.

If the repository is given a different name, the address becomes `https://mco-aco.github.io/REPO-NAME/`.
Update the `canonical`, `og:url` and `og:image` tags and the JSON-LD `url` and `image` in `index.html`,
and the `URL:` line in `matine.vcf`, to match.

Every later change is published by committing and pushing again:

```
git add -A
git commit -m "Update contact details"
git push
```

### Custom domain (optional)

If a domain such as `matineandco.co.uk` is bought later, add it under **Settings → Pages → Custom domain**
and point the domain's DNS at GitHub Pages as GitHub's instructions describe. Then change the site
address in the files listed above to the new domain.
