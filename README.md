# Pipeline Components: Pylint

[![][gitlab-repo-shield]][repository]
![Project Stage][project-stage-shield]
![Project Maintenance][maintenance-shield]
[![License][license-shield]](LICENSE)
[![GitLab CI][gitlabci-shield]][gitlabci]

## Docker status

[![Image Size][size-shield]][dockerhub]
[![Docker Pulls][pulls-shield]][dockerhub]

## Usage

The image is for running pylint, pylint is installed in /app/ in case you need to customize the install before usage.
The plugin [pylint-gitlab] is installed for easy gitlab reporting features

## Examples

```yaml
pylint:
  stage: linting
  image: registry.gitlab.com/pipeline-components/pylint:latest
  script:
    - pylint **/*.py
```

Example with pylint-gitlab
```yaml
pylint:
  stage: linting
  image: registry.gitlab.com/pipeline-components/pylint:latest
  script:
    - pylint --exit-zero --load-plugins=pylint_gitlab --output-format=gitlab-codeclimate:codeclimate.json **/*.py
  artifacts:
    reports:
      codequality: codeclimate.json
    when: always
```

## Versioning

This project uses [Semantic Versioning][semver] for its version numbering.

## Support

Got questions?

You have several options to get them answered:
Check the [discord channel][discord]
You could also [open an issue here][issue]

## Contributing

This is an active open-source project. We are always open to people who want to
use the code or contribute to it.

We've set up a separate document for our [contribution guidelines][contributing-link].

Thank you for being involved! 😍

## Authors & contributors

The original setup of this repository is by [Robbert Müller][mjrider].

The Build pipeline is large based on [Community Hass.io Add-ons
][hassio-addons] by [Franck Nijhof][frenck].

For a full list of all authors and contributors,
check [the contributor's page][contributors].

## License

This project is licensed under the [MIT License](./LICENSE) by [Robbert Müller][mjrider].

[contributing-link]: https://pipeline-components.dev/contributing/
[contributors]: https://gitlab.com/pipeline-components/pylint/-/graphs/main
[discord]: https://discord.gg/vhxWFfP
[dockerhub]: https://hub.docker.com/r/pipelinecomponents/pylint
[frenck]: https://github.com/frenck
[gitlab-repo-shield]: https://img.shields.io/badge/Source-Gitlab-orange.svg?logo=gitlab
[gitlabci-shield]: https://img.shields.io/gitlab/pipeline/pipeline-components/pylint.svg
[gitlabci]: https://gitlab.com/pipeline-components/pylint/-/commits/main
[hassio-addons]: https://github.com/hassio-addons
[issue]: https://gitlab.com/pipeline-components/pylint/issues
[license-shield]: https://img.shields.io/badge/License-MIT-green.svg
[maintenance-shield]: https://img.shields.io/maintenance/yes/2025.svg
[mjrider]: https://gitlab.com/mjrider
[project-stage-shield]: https://img.shields.io/badge/project%20stage-production%20ready-brightgreen.svg
[pulls-shield]: https://img.shields.io/docker/pulls/pipelinecomponents/pylint.svg?logo=docker
[repository]: https://gitlab.com/pipeline-components/pylint
[semver]: http://semver.org/spec/v2.0.0.html
[size-shield]: https://img.shields.io/docker/image-size/pipelinecomponents/pylint.svg?logo=docker

[pylint-gitlab]: https://gitlab.com/smueller18/pylint-gitlab
