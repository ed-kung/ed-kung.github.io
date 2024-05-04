# Ed's Kung Personal Website

This is the GitHub repository for Edward Kung's personal website, hosted on GitHub Pages and using the Chirpy theme for Jekyll.

## How this site was built

These instructions assume that you already have Ruby and Jekyll installed in your environment.

1. Start a new repo using the [Chirpy Starter Template](https://github.com/cotes2020/chirpy-starter).

2. Clone the repo to your local dev environment.

3. Run `bundle` in the repo's root directory to install the necessary Ruby gems.

4. Copy your favicon files to `/assets/img/favicons/`

5. In addition to obvious changes like site title and social media links, I made the following modifications to `_config.yml`:

    ```YAML
    timezone: America/Los_Angeles
    pwa:
      enabled: false
    url: "https://ed-kung.github.io"
    ```
    
    You need to change the `url` field for deployment on Github Pages to work.

5. Sidebar pages are located in `/_tabs/`.  I deleted `categories.md` and `archives.md` because I didn't need them.  I added `research.md`, `teaching.md`, and `CV.md`.  The sidebar page icons are provided by [Font Awesome](https://fontawesome.com){:target="_blank"}. To select different icons, simply change the icon id in the `icon` field.

6. By default, Chirpy includes Twitter and Github social links. I didn't want Twitter but I wanted to add Linkedin.  To do that, I had to modify `_data/contact.yml`. The social icon for Linked in is `fab fa-linkedin`. The order in which items are listed in `_data/contact.yml` is the order they will show up in the sidebar. I went with email first, then GitHub, then Linkedin.

7. Push the changes to GitHub. Then in Settings>>Pages, choose to deploy from GitHub Actions. 

