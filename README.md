# trellis-sage-9-compiler

[![GitHub tag](https://img.shields.io/github/tag/ItinerisLtd/trellis-sage-9-compiler.svg)](https://github.com/ItinerisLtd/trellis-sage-9-compiler/tags)
[![license](https://img.shields.io/github/license/ItinerisLtd/trellis-sage-9-compiler.svg)](https://github.com/ItinerisLtd/trellis-sage-9-compiler/blob/master/LICENSE)

**This is not production-ready yet! See: [roots/trellis#1030](https://github.com/roots/trellis/pull/1030)**

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [TODOs (Help wanted)](#todos-help-wanted)
- [Requirements](#requirements)
- [Installation](#installation)
- [Role Variables](#role-variables)
  - [`name`](#name)
  - [`cleanup`](#cleanup)
- [Usage](#usage)
- [FAQs](#faqs)
  - [It looks awesome. Where can I find some more goodies like this?](#it-looks-awesome-where-can-i-find-some-more-goodies-like-this)
  - [This package isn't on wp.org. Where can I give a ⭐️⭐️⭐️⭐️⭐️ review?](#this-package-isnt-on-wporg-where-can-i-give-a-%EF%B8%8F%EF%B8%8F%EF%B8%8F%EF%B8%8F%EF%B8%8F-review)
- [Testing](#testing)
  - [Syntax Check](#syntax-check)
- [Author Information](#author-information)
- [Feedback](#feedback)
- [Change log](#change-log)
- [License](#license)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

**This is not production-ready yet! See: [roots/trellis#1030](https://github.com/roots/trellis/pull/1030)**

## TODOs (Help wanted)

- Test on older versions of ansible (only 2.7.4 is tested)
- Test on the offical roots file structure (only the [@tangrufus way](https://github.com/roots/trellis/issues/883#issuecomment-329052189) is tested)
- Allow variables in [defaults](./defaults) be customizable

## Requirements

- Ansible v2.4 or later
- Trellis with [roots/trellis#1030](https://github.com/roots/trellis/pull/1030) patched
- Sage v9

## Installation

Add this role to `requirements.yml`:
```yaml
# requirements.yml
- src: https://github.com/ItinerisLtd/trellis-sage-9-compiler
  version: master # This is not production-ready yet!
```

Hook this role to `deploy_build_before`:
```yaml
# group_vars/all/deploy-hooks.yml
# Learn more on https://roots.io/trellis/docs/deploys/#hooks
deploy_build_before:
  - "{{ playbook_dir }}/vendor/roles/trellis-sage-9-compiler/tasks/main.yml"
```

Run the command:
```sh-session
➜ ansible-galaxy install -r requirements.yml --force
```

## Role Variables

```yaml
# group_vars/<env>/wordpress_sites.yml
wordpress_sites:
  example.com:
    sage_9_compiler:
      - name: my-first-sage-theme-name
      - name: my-second-sage-theme-name
        cleanup: true
      - name: my-second-sage-theme-name
        cleanup: false
```

### `name`

- Required
- Type: string
- Directory name of your sage theme

### `cleanup`

- Optional
- Default: `false`
- Type: boolean
- Whether to [remove theme source files](https://roots.io/guides/remove-theme-source-files-on-deploy/)

More variables in [defaults](./defaults). (*Currently not customizable*)

## Usage

[Deploy](https://roots.io/trellis/docs/deploys/#example) as usual. No special action needed.

## FAQs

### It looks awesome. Where can I find some more goodies like this?

- Articles on [Itineris' blog](https://www.itineris.co.uk/blog/)
- More projects on [Itineris' GitHub profile](https://github.com/itinerisltd)
- Follow [@itineris_ltd](https://twitter.com/itineris_ltd) and [@TangRufus](https://twitter.com/tangrufus) on Twitter
- Hire [Itineris](https://www.itineris.co.uk/services/) to build your next awesome site

### This package isn't on wp.org. Where can I give a ⭐️⭐️⭐️⭐️⭐️ review?

Thanks! Glad you like it. It's important to make my boss know somebody is using this project. Instead of giving reviews on wp.org, consider:

- tweet something good with mentioning [@itineris_ltd](https://twitter.com/itineris_ltd)
- star this [Github repo](https://github.com/ItinerisLtd/trellis-sage-9-compiler)
- watch this [Github repo](https://github.com/ItinerisLtd/trellis-sage-9-compiler)
- write blog posts
- submit pull requests
- [hire Itineris](https://www.itineris.co.uk/services/)

## Testing

### Syntax Check

```bash
➜ ansible-playbook -i 'localhost,' --syntax-check tests/test.yml
```

## Author Information

TODO: Discuss with the roots team!

[trellis-sage-9-compiler](https://github.com/ItinerisLtd/trellis-sage-9-compiler) is a [Itineris Limited](https://www.itineris.co.uk/) project created by [Tang Rufus](https://typist.tech). Fork from [roots/trellis](https://github.com/roots/trellis) because of [roots/trellis#1030](https://github.com/roots/trellis/pull/1030).

Special thanks to [the Roots team](https://roots.io/about/) whose [Trellis](https://github.com/roots/trellis) make this project possible.

Full list of contributors can be found [here](https://github.com/ItinerisLtd/trellis-sage-9-compiler/graphs/contributors).

## Feedback

**Please provide feedback!** We want to make this library useful in as many projects as possible.
Please submit an [issue](https://github.com/ItinerisLtd/trellis-sage-9-compiler/issues/new) and point out what you do and don't like, or fork the project and make suggestions.
**No issue is too small.**

## Change log

Please see [CHANGELOG](./CHANGELOG.md) for more information on what has changed recently.

## License

[trellis-sage-9-compiler](https://github.com/ItinerisLtd/trellis-sage-9-compiler) is released under the [MIT License](https://opensource.org/licenses/MIT).
