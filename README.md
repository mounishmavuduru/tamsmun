# TAMS Model United Nations

Website for TAMSMUN, a one-day high school Model UN conference hosted by the Texas Academy of Mathematics and Science at the University of North Texas in Denton, Texas. Saturday, October 10, 2026, 8:00 AM to 6:00 PM.

## Files

- `index.html` is the whole site: styles, markup, and script in one file. No build step.
- `hero-campus.jpg` is the hero background photo (UNT campus, looking toward the Hurley clock tower). If you swap it, give the new file a new name, because browsers cache the photo for a year.
- `favicon.svg` is the browser tab icon.
- `vercel.json` sets long-lived caching for the photo.

## Editing

Open `index.html` and change the text directly. Near the bottom of the file there is a `CONFIG` block:

```js
var CONFIG = {
  heroImage: "",           // leave empty to use hero-campus.jpg
  contactEmail: "",        // the Secretariat's email address
  instagram: "",           // Instagram handle without the @
  secretaryGeneral: "",    // name that signs the letter
  registrationUrl: "",     // delegate registration form link, once live
  chairUrl: ""             // chair application form link, once live
};
```

Fill in a value and the page updates itself: the Register buttons appear, "Opens soon" flips to "Open now", the footer shows the email, and so on. Empty strings keep the "opens soon" copy.

The schedule and the committee cards are plain HTML in the `schedule` and `committees` sections.

## Deploying

The site is deployed on Vercel. Every push to `main` deploys automatically once the GitHub repo is connected to the Vercel project.

To preview locally, open `index.html` in a browser, or run any static server in this folder:

```bash
npx serve .
```

## Domain

After buying `tamsmun.org`:

1. In Vercel, open the project, go to Settings, then Domains, and add `tamsmun.org` and `www.tamsmun.org`.
2. Vercel shows the DNS records to add at the registrar: an `A` record for `@` pointing to `76.76.21.21` and a `CNAME` record for `www` pointing to `cname.vercel-dns.com`. Alternatively, switch the domain's nameservers to `ns1.vercel-dns.com` and `ns2.vercel-dns.com` and Vercel manages DNS itself.
3. Wait for the records to propagate (minutes to a few hours). Vercel issues the HTTPS certificate automatically.
4. Set one of the two domains as the primary in Vercel so the other redirects to it.
