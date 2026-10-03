# Dopamigo website

The public homepage, privacy policy and Terms of Service for Dopamigo, ready to deploy as a static website on Vercel. The HTML and CSS work without a build step, dependencies, API keys or environment variables.

## Upload to GitHub

1. Extract `dopamigo-website.zip`.
2. Create your new GitHub repository.
3. Upload the **contents** of the extracted `dopamigo-website` folder into the repository root. Keep the `public` folder and its subfolders intact. Upload the extracted files, not the ZIP itself.
4. Commit the files.

Your repository should look like this:

```text
README.md
vercel.json
.gitignore
public/
  index.html
  style.css
  privacy/
    index.html
  terms/
    index.html
```

## Deploy on Vercel

1. In Vercel, create a new project and import your GitHub repository.
2. Keep **Root Directory** at the repository root (`./`).
3. Use **Framework Preset: Other**. The included `vercel.json` configures an empty build command and `public` as the output directory.
4. No environment variables are needed. Click **Deploy**.
5. Open the production URL and check the homepage, `/privacy/` and `/terms/`. The public production pages must be accessible without signing in, including from a private browser window.

Vercel configuration reference: https://vercel.com/docs/builds/configure-a-build

## Google OAuth branding URLs

Once you have your deployed domain, use:

| Google field | Website URL |
| --- | --- |
| Application home page | `https://YOUR-DOMAIN/` |
| Application privacy policy link | `https://YOUR-DOMAIN/privacy/` |
| Application Terms of Service link | `https://YOUR-DOMAIN/terms/` |

Replace `YOUR-DOMAIN` with the actual hostname. Internal links automatically use whichever domain hosts the site.

Hosting the pages and verifying domain ownership are separate steps. For the current Google OAuth ownership requirement, verify a **Domain property using DNS** in Google Search Console with the Google account that owns the Cloud project. A Google verification TXT record belongs in the domain's DNS settings; uploading a text file to this website does not publish a DNS record. This package does not configure DNS or claim that Google has verified the app.

Google's domain verification instructions: https://support.google.com/cloud/answer/13804266?hl=en

## Edit or preview locally

Edit the files inside `public`. From this folder, start a local preview:

```sh
python3 -m http.server 8080 --bind 127.0.0.1 --directory public
```

Open http://127.0.0.1:8080/. Stop the server with Ctrl+C. Use a local server rather than opening the HTML files directly, because navigation and stylesheet links start at the website root.

The policy pages are copied from the existing Dopamigo website, dated 3 October 2026. Update them when the app's data practices or terms change.
