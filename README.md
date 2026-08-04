<p align="center">
    <a href="https://www.getzola.org/">
        <img src="https://img.shields.io/badge/powered_by-Zola-brightgreen?style=flat-square&labelColor=202b2d&color=087e96" alt="Built with Zola"></a>
    <a href="https://github.com/welpo/tabi">
        <img src="https://img.shields.io/badge/theme-tabi-0?style=flat-square&labelColor=202b2d&color=087e96" alt="tabi theme"></a>
    <a href="https://welpo.github.io/tabi/blog/mastering-tabi-settings/">
        <img src="https://img.shields.io/badge/docs-here-0?style=flat-square&labelColor=202b2d&color=087e96" alt="Documentation"></a>
</p>

# tabi start

Start blogging in minutes with [Zola](https://www.getzola.org/) and [tabi](https://github.com/welpo/tabi).

![Screenshot of tabi theme](https://cdn.jsdelivr.net/gh/welpo/tabi@main/light_dark_screenshot.png)

## Quick start

1. On the top right of this page, click "Use this template" → "Create a new repository"
2. Replace placeholders in `content/_index.md` and in the first four lines of `config.toml`
3. Save your profile photo to `static/img/profile.webp` (or change the path to your image in `content/_index.md`)
4. Start writing in `content/blog/`. See `content/blog/hello.md` for an example

**Note**: an error like `Tried to build search index for language ko which is not supported`, means Zola does not support search for that language. To disable search, set `build_search_index = false` in `config.toml`

> [!TIP]
> Take a look through `config.toml` to customise further (set up [social links](https://welpo.github.io/tabi/blog/mastering-tabi-settings/#social-media-icons), your [email](https://welpo.github.io/tabi/blog/mastering-tabi-settings/#encoded-email)…). The [Mastering tabi Settings](https://welpo.github.io/tabi/blog/mastering-tabi-settings/) guide has more details.

> [!WARNING]
> Syntax highlighting works on Zola `0.22.0` and newer. For older versions, set in `config.toml`:

    [markdown]
    highlight_code = true
    bottom_footnotes = true
    # To use a Zola built-in theme, CSP needs to allow unsafe-inline for style-src.
    highlight_theme = "css"
    smart_punctuation = true

## File structure

```tree
├── config.toml              # Site configuration
├── content/
│   ├── _index.md            # Home page
│   ├── archive/             # Archive page
│   │   └── _index.md        # Archive page section
│   ├── blog/                # Blog posts
│   │   ├── hello.md         # Sample post
│   │   └── _index.md        # Blog section configuration
│   └── projects/            # Projects page
│       ├── cool_project.md  # Sample project
│       └── _index.md        # Projects section configuration
│── static/
│   └── img/
│       └── profile.webp     # Profile photo for home page
└── themes/
    └── tabi/                # tabi theme
```

## Local development

1. [Install Zola](https://www.getzola.org/documentation/getting-started/installation/)
2. Clone your repository
3. Run `git submodule update --init --recursive`
4. Run `zola serve`
5. Visit http://127.0.0.1:1111. You should see [this](https://tabi-start.pages.dev/).

## Deployment

Refer to the [Zola documentation](https://www.getzola.org/documentation/deployment/overview/):

- [AWS S3 Bucket](https://www.getzola.org/documentation/deployment/aws-s3/)
- [Cloudflare Pages](https://www.getzola.org/documentation/deployment/cloudflare-pages/)
- [Codeberg Pages](https://www.getzola.org/documentation/deployment/codeberg-pages/)
- [Docker image](https://www.getzola.org/documentation/deployment/docker-image/)
- [Edgio](https://www.getzola.org/documentation/deployment/edgio/)
- [Fly.io](https://www.getzola.org/documentation/deployment/flyio/)
- [GitHub Pages](https://www.getzola.org/documentation/deployment/github-pages/)
- [GitLab Pages](https://www.getzola.org/documentation/deployment/gitlab-pages/)
- [Netlify](https://www.getzola.org/documentation/deployment/netlify/)
- [Sourcehut Pages](https://www.getzola.org/documentation/deployment/sourcehut/)
- [Vercel](https://www.getzola.org/documentation/deployment/vercel/)
- [Zeabur](https://www.getzola.org/documentation/deployment/zeabur/)

## Updating tabi

### Automated updates

This template includes a [GitHub Action workflow](https://github.com/welpo/tabi-start/blob/main/.github/workflows/update-tabi.yml) that checks for tabi theme updates weekly and pushes them directly to `main` when a build check passes.

#### Setting up permissions

The automated updates require proper GitHub Actions permissions:

1. Go to your repository's Settings → Actions → General
2. Scroll down to "Workflow permissions"
3. Enable "Read and write permissions"
4. Save changes

<details>
<summary>How automated updates work (click to read)</summary>

- Every Monday at midnight (UTC), the workflow checks for new tabi versions
- If an update is found, it builds the site with the new theme version
- If the build succeeds, it commits and pushes the update directly to `main`, with a commit message containing:
  - Detailed changelog
  - Links to relevant commits and PRs
- If the build fails, the workflow fails and you'll receive an email notification. It's likely tabi added a breaking change that needs your manual review.

</details>

### Manual updates

```bash
git submodule update --remote themes/tabi
```

## Support

- [tabi documentation](https://welpo.github.io/tabi/)
- [Zola documentation](https://www.getzola.org/documentation/getting-started/overview/)

> [!TIP]
> How was your experience with this template?
>
> Share your thoughts in this [tabi discussion](https://github.com/welpo/tabi/discussions/440) or [report any issues](https://github.com/welpo/tabi/issues/new?&labels=bug&template=2_bug_report.yml) you find! Thank you 🙇🏼‍♂️
