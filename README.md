# Technologocal watch

**Based on [Marp] via [Marp CLI].**

- Write your slide deck by [Marp] Markdown.
- Manage the content of slides via Git. (Using [GitPitch](https://gitpitch.com/) style `PITCHME.md`)
- Host your deck at GitHub, and publish as webpage with [GitHub Pages], [Netlify], and [ZEIT Now][now]!

[marp]: https://marp.app/
[marp cli]: https://github.com/marp-team/marp-cli
[github pages]: https://pages.github.com/
[netlify]: https://www.netlify.com/
[now]: https://zeit.co/now

<p align="center">
  <a href="https://yhatt.github.io/marp-cli-example"><img src="https://yhatt.github.io/marp-cli-example/og-image.jpg" width="500" /></a>
</p>

## See published slide deck

- <img src="https://icongr.am/octicons/mark-github.svg" width="24" height="24" valign="bottom" /> **[GitHub Pages]**: https://yhatt.github.io/marp-cli-example
- <img src="https://www.netlify.com/img/press/logos/logomark.svg" width="24" height="24" valign="bottom" /> **[Netlify]**: https://yhatt-marp-cli-example.netlify.com/
- <img src="https://assets.zeit.co/image/upload/front/assets/design/now-black.svg" width="24" height="24" valign="bottom" /> **[ZEIT Now][now]**: https://marp-cli-example.yhatt.now.sh/

## Usage

It's surprisingly easy to start publishing your slide deck!

### <img src="https://icongr.am/octicons/mark-github.svg" width="24" height="24" valign="bottom" /> [GitHub Pages]

[Fork this repository](https://help.github.com/en/github/getting-started-with-github/fork-a-repo) from **"Fork"** button in right-top corner to start!

#### Setup GitHub Actions

We have [GitHub Actions workflow](.github/workflows/github-pages.yml) to build and deploy from `master` to `gh-pages` automatically.

In the moment, deploying from public repository to GitHub Pages requires setting up your access token as secret. ([Track discussion in forum...](https://github.community/t5/GitHub-Actions/Github-action-not-triggering-gh-pages-upon-push/m-p/26869/highlight/true))

1. Go to **["Personal Access Tokens"](https://github.com/settings/tokens)** setting page and click **"Generate New Token"**.
2. Create new token with **"repo"** scope, and _copy generated token_.
3. Go to **"Settings"** tab in forked repository, and select **"Secrets"** from sidebar.
4. Add a new secret **"ACCESS_TOKEN"** with the value of generated token.
5. Turn on GitHub Actions in forked repository from **"Actions"** tab.

## How to write

For Marp slide deck features, please see the documentation of [Marpit Markdown](https://marpit.marp.app/markdown), [the features of Marp Core](https://github.com/marp-team/marp-core#features), and the default example in [`PITCHME.md`](https://raw.githubusercontent.com/yhatt/marp-cli-example/master/PITCHME.md) for .

You have to install [Node.js](https://nodejs.org/) and run `npm i` at first if you want to write slide deck with [Marp CLI].

### Edit deck

Just edit **[`PITCHME.md`](./PITCHME.md)**!

#### Preview deck

[**Marp for VS Code**](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) extension is the best partner for writing Marp slide deck with live preview.

<p align="center">
  <a href="https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode">
    <img src="https://raw.githubusercontent.com/marp-team/marp-vscode/master/docs/screenshot.png" width="500" />
  </a>
</p>

#### Preview via CLI

```bash
npm run start
```

It will be opened preview window via installed Google Chrome, and track change of `PITCHME.md`.

### Assets and themes

- `assets` directory can put your assets for using in the deck. (e.g. Image resources)
- `themes` directory can put [custom theme CSS](https://marpit.marp.app/theme-css). To use in the deck, please change `theme` global directive.

### Build deck via CLI

```bash
npm run build
```

The built assets will output to `dist` folder.

#### Build per assets

```bash
npm run deck      # Output static HTML to dist/index.html
npm run og-image  # Output image for Open Graph to dist/og-image.jpg
```

## LICENSE

[WTFPL](/LICENSE)
