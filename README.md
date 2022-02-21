
[![CircleCI Build Status](https://circleci.com/gh/BrassTack/circleci-poc-orb-file-copy.svg?style=shield "CircleCI Build Status")](https://circleci.com/gh/BrassTack/circleci-poc-orb-file-copy) [![CircleCI Orb Version](https://badges.circleci.com/orbs/brasstack/circleci-poc-orb-file-copy.svg)](https://circleci.com/orbs/registry/orb/brasstack/circleci-poc-orb-file-copy) [![GitHub License](https://img.shields.io/badge/license-MIT-lightgrey.svg)](https://raw.githubusercontent.com/BrassTack/circleci-poc-orb-file-copy/master/LICENSE) [![CircleCI Community](https://img.shields.io/badge/community-CircleCI%20Discuss-343434.svg)](https://discuss.circleci.com/c/ecosystem/orbs)


# Example orb file copy

Copies a "file" from inside the orb to the filesystem of the running job.

See --brasstack link to article--

Example usage: https://github.com/BrassTack/circleci-poc-orb-file-copy-consumer/tree/main/.circleci

```
version: 2.1

orbs:
  circleci-poc-orb-file-copy: brasstack/circleci-poc-orb-file-copy@0

workflows:
  file-copy-test:
    jobs:
      - circleci-poc-orb-file-copy/copy-file-from-orb
```

Example job: https://github.com/BrassTack/circleci-poc-orb-file-copy/blob/main/src/jobs/copy-file-from-orb.yml

![example screenshot](/circleci-orb-file-copy-example.png)

