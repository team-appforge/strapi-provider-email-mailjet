# strapi-provider-email-mj

## Resources

- [MIT License](LICENSE.md)

## Links

- [Strapi website](http://strapi.io/)
- [Strapi community on Slack](http://slack.strapi.io)
- [Strapi news on Twitter](https://twitter.com/strapijs)

## Prerequisites

You need to have the plugin `strapi-plugin-email` installed in you Strapi project.

## Installation

```bash
# using yarn
yarn add strapi-provider-email-mj

# using npm
npm install strapi-provider-email-mj --save
```

## Configuration

| Variable                | Type                    | Description                                                                                                                        | Required | Default   |
| ----------------------- | ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | -------- | --------- |
| provider                | string                  | The name of the provider you use                                                                                                   | yes      |           |
| providerOptions         | object                  | Will be directly given to the `require('node-mailjet')`. Please refer to [node-mailjet](https://www.npmjs.com/package/node-mailjet) doc. | yes      |           |
| settings                | object                  | Settings                                                                                                                           | no       | {}        |
| settings.defaultFrom    | string                  | Default sender mail address                                                                                                        | no       | undefined |
| settings.defaultReplyTo | string \| array<string> | Default address or addresses the receiver is asked to reply to                                                                     | no       | undefined |

### Example

**Path -** `config/plugins.js`

```js
module.exports = ({ env }) => ({
  // ...
  email: {
    provider: 'mailjet-mj',
    providerOptions: {
      apiKey: env('MAILJET_API_KEY'),
      secretKey: env('MAILJET_SECRET_KEY'),
    },
    settings: {
      defaultFrom: 'myemail@prodiver.com',
      defaultReplyTo: 'myemail@provider.com',
    },
  },
  // ...
});
```
