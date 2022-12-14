<div align="center" >
  <img width=400  alt="Image Credit: Peaceiris" src="https://raw.githubusercontent.com/peaceiris/actions-hugo/main/images/ogp.svg?sanitize=true" />
  <p style="font-size:12px;" >
    Image Credit: <a href="https://github.com/peaceiris">Peaceiris</a>
  </p>
  <h1>
  Build Your Hugo Site in GitHub Actions
  </h1>
  <h3>
    <a href="https://github.com/gohugoio/hugo">
      gohugoio/hugo: The worldâs fastest framework for building websites
    </a>
  </h3>
  <span>
    <h3>
    ð
    <a href="https://github.com/chabad360/hugo-actions/blob/master/LICENSE">
      <img alt="License" src="https://img.shields.io/github/license/chabad360/hugo-actions.svg?style=for-the-badge" />
    </a>
    <a href="https://github.com/marketplace/actions/hugo-site">
      <img alt="Release" src="https://img.shields.io/static/v1?label=&style=for-the-badge&logo=addthis&logoColor=white&message=Get+on+the+GH+Marketplace&color=green" />
    </a>
    <a href="https://github.com/chabad360/hugo-actions/releases/latest">
      <img alt="Release" src="https://img.shields.io/github/release/chabad360/hugo-actions.svg?style=for-the-badge" />
    </a>
    ð
    </h3>
  </span>
</div>
&nbsp;

This action builds your Hugo Site using the latest Hugo Extended.

This action also contains support for several external Hugo Helpers:

| Name | Support |
| ---- | :-----: |
| reStructuredText |ï¸ âï¸ |
| Pandoc | âï¸ |
| Asciidoctor | âï¸ |
| PostCSS | âï¸ |
| Pygments | âï¸ |
| Babel | âï¸ |
| Hugo Modules | âï¸ |

If your site requires the use of another external helper, submit an issue and I'll try to add it.

## â­ Getting started

This is a basic `workflow.yml` to get you started (for more information scroll down to [â­ Inputs](#-inputs)):

```yaml
name: Build Site

on:
  push:
    branches:
      - master

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repo
        uses: actions/checkout@master
        with:
          submodules: true
      - name: Build Site
        uses: chabad360/hugo-actions@master
```

### â­ Inputs

| Key |  Description | Required | Default |
| --- | ------------ | :------: | ------- |
| `buildPath` | The path to build the site into. | â | `public`|
| `hugoVersion` | The version Hugo to use (append `extended_` to the begining to use the extended version). | â | Latest Hugo Extended |
| `args` | Arguments to pass to Hugo | â | `--gc --minify --cleanDestinationDir`|
#### Usage

```yaml
- name: Publish Site
  uses: chabad360/hugo-actions@master
  with:
    buildPath: 'public'
    # Use if you have a need to build the site to another directory
    hugoVersion: 'extended_0.58.3'
    # Use if your site requires a specific version of Hugo
    # Append "extended_" to the begining to use Hugo Extended
    args: --gc --minify --cleanDestinationDir
    # Use if you want to pass some custom arguments to Hugo
```

## â­ Credit

This project is partially based on [mattbailey/actions-hugo](https://github.com/mattbailey/actions-hugo)
