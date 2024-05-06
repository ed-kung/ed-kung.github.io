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


## Note on using project sites

The above instructions should work if the repo name is `github-username.github.io`. That's the required repo name for your "main" Github Pages site. The website will be served at: `https://github-username.github.io`.

If you instead named your repo something else, like `my-project`, then it is considered a "project site" and will be served at `https://github-username.github.io/my-project`.

If you are using a project site, the previous instructions will lead to deployment errors, due to the way Chirpy handles relative links.

If you are making a project site from the Chirpy template, you will need to modify the following line in `_config.yml`:

```YAML
baseurl: my-project
```

In addition, any relative links you use in your markdows need to be preceded by `my-project`. 

For example, if you want to link to a pdf file hosted in `assets/pdf/my-pdf.pdf`, the markdown link should look like:

```markdown
[Link to pdf](/my-project/assets/pdf/my-pdf.pdf)
```

Not including `my-project` in the link will cause deployment errors.


## Using a custom domain name

- First, follow [these instructions](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages) to verify the custom domain. I wanted to verify `ekung.io`.

    - If you're using Namecheap, as I am, the TXT record host should simply be `_github-pages-challenge-ed-kung` (without the `.ekung.io` at the end)
    
- Then, follow [these instructions](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site) for setting up the custom domain.

    - To set up both the apex domain and the www subdomain variant, the following records were added on Namecheap:
    
    | Type           | Host | Value                        |
    | -------------- | ---- | ---------------------------- |
    | ALIAS          |    @ | ed-kung.github.io            |
    | CNAME          |  www | ed-kung.github.io            |
    
    - Then, a CNAME record needs to be added to the Github repo. This is a file named `CNAME` and it contains one line:
    
    ```
    www.ekung.io
    ```
    
    - Then, the custom domain for Github Pages is configured to `www.ekung.io`.
    
- Now, all requests to `www.ekung.io` or `ekung.io` are directed to the Github Pages site. Project sites automatically redirect as well, without having to specify a custom domain on the project sites.










