# step-slack

A slack notifier written in `bash` and `curl`. Make sure you create a Slack
webhook first (see the Slack integrations page to set one up).

[![wercker status](https://app.wercker.com/status/94f767fe85199d1f7f2dd064f36802bb/s "wercker status")](https://app.wercker.com/project/bykey/94f767fe85199d1f7f2dd064f36802bb)

# Options

- `url` The Slack webhook url
- `channel` The Slack channel
- `username` Username of the notification message
- `icon_url` (optional) A url that specifies an image to use as the avatar icon in Slack
- `notify_on` (optional) If set to `failed`, it will only notify on failed
builds or deploys.

# Example

```yaml
build:
    after-steps:
        - slack-notifier:
            url: $SLACK_URL
            channel: notifications
            username: myamazingbotname
```

The `url` parameter is the [slack webhook](https://api.slack.com/incoming-webhooks) that wercker should post to.
You can create an *incoming webhook* on your slack integration page.
This url is then exposed as an environment variable (in this case
`$SLACK_URL`) that you create through the wercker web interface as *deploy pipeline variable*.



# License

The MIT License (MIT)

# Changelog

## 1.0.0

- Initial release
