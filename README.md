# Wercker Node Firefox Headless

Run headless firefox using xvfb on wercker.com.


Example `wercker.yml`.

```yaml
box: dignifiedquire/node-firefox-headless

steps:
  - wercker/grunt@0.0.9

build:
  # The steps that will be executed on build
  steps:
    - npm-install
    - script:
        name: setup headless firefox
        code: |
          export DISPLAY=:99.0
          sh -e /etc/init.d/xvfb start
    - grunt:
        tasks: default
```
