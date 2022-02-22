
[![CircleCI Build Status](https://circleci.com/gh/BrassTack/circleci-poc-orb-file-copy.svg?style=shield "CircleCI Build Status")](https://circleci.com/gh/BrassTack/circleci-poc-orb-file-copy) [![CircleCI Orb Version](https://badges.circleci.com/orbs/brasstack/circleci-poc-orb-file-copy.svg)](https://circleci.com/orbs/registry/orb/brasstack/circleci-poc-orb-file-copy) [![GitHub License](https://img.shields.io/badge/license-MIT-lightgrey.svg)](https://raw.githubusercontent.com/BrassTack/circleci-poc-orb-file-copy/master/LICENSE) [![CircleCI Community](https://img.shields.io/badge/community-CircleCI%20Discuss-343434.svg)](https://discuss.circleci.com/c/ecosystem/orbs)


# Example orb file copy

Example implementation - it copies a "file" from inside the orb to the filesystem of the running job.  This example cannot be reusably consumed.

See https://www.brasstack.net/blog/circleci-orb-file-copy/ for a more complete explanation.

Example usage: https://github.com/BrassTack/circleci-poc-orb-file-copy-consumer/tree/main/.circleci

```yaml
version: 2.1

orbs:
  circleci-poc-orb-file-copy: brasstack/circleci-poc-orb-file-copy@0

workflows:
  file-copy-test:
    jobs:
      - circleci-poc-orb-file-copy/copy-file-from-orb
```

Example step: https://github.com/BrassTack/circleci-poc-orb-file-copy/blob/main/src/jobs/copy-file-from-orb.yml#L8

```yaml
  - run:
      name: "copy sample.yml from orb to the filesystem"
      environment:
          TEMPLATE_CONTENT: <<include(templates/sample.yml)>>
      command: /bin/echo "$TEMPLATE_CONTENT" > /tmp/sample.yml
```

![example screenshot](/circleci-orb-file-copy-example.png)

