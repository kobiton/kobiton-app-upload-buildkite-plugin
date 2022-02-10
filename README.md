# Kobiton App Upload Buildkite Plugin

A Plugin that take an apk or ipa file and upload it to Kobiton App.

## Example

Add the following to your `pipeline.yml`:

```yml
steps:
  - label: "Kobiton App Upload"
    plugins:
      - kobiton/kobiton-app-upload#v1.0.0:
          app-name: '<app-name>'
          app-path: '<path-to-your-app>'
          app-type: '<apk or ipa>'
          kobiton-app-id: 'your-kobiton-app-id'
          kobiton-app-access: 'private'
          kobiton-username: '<your-kobiton-username>'
          kobiton-api-key: '<your-kobiton-api-key>'
```

## Configuration

### `app-name` (Required, string)

Title of the app being built, for example `test-app`.

### `app-path` (Required, string)

Path to the app .apk or .ipa file, for example `./test.apk`.

### `app-type` (Required, string)

`ipa` for IOS app or `apk` for Android app.

### `kobiton-app-id` (Required, string)

App ID in Kobiton, use this in case you want to upload new version of an existing app in Kobiton, for example `204234`.

### `kobiton-app-access` (Required, string)

You can either to make this app private with `private` or available for everyone with `public` in the organization.

### `kobiton-username` (Required, string)

Kobiton Username to upload to Kobiton, for example `kobitonadmin`.

### `kobiton-api-key` (Required, string)

API key to access Kobiton API, for example `2c8n41e4-b30d-4f19-ba63-6596016c9e58`.

## Developing

To run the tests:

```shell
docker-compose run --rm tests
```

To validate the `plugin.yml`:
```shell
docker-compose run --rm lint
```

## Contributing

1. Fork the repo
2. Make the changes
3. Run the tests
4. Commit and push your changes
5. Send a pull request
