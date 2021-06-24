# React + Contentful + Github Pages Boilerplate

Easily build static pages using this boilerplate - which can be easily deployed in Github Pages!

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app). Refer to their documentation for further information.

## Setup

1. In `package.json`, update the `homepage` and `name` fields with your github username.

```json
{
  "homepage": "https://<YOUR_GITHUB_ID>.github.io",
  "name": "<YOUR_GITHUB_ID>.github.io"
}
```

2. Update the `.env` file with the necessary keys, IDs from your Contentful account.

```env
REACT_APP_CONTENTFUL_BASE_URL=https://cdn.contentful.com
REACT_APP_CONTENTFUL_SPACE_ID=YOUR_CONTENTFUL_SPACE_ID
REACT_APP_CONTENTFUL_ENVIRONMENT_ID=YOUR_CONTENTFUL_ENVIRONMENT_ID
REACT_APP_CONTENTFUL_DELIVERY_TOKEN=-Id6Isa-ZEZm-YOUR_CONTENTFUL_DELIVERY_TOKEN
```

## Contentful

This uses [contentful.js](https://www.npmjs.com/package/contentful) to access data stored in Contentful via the Content Delivery API.

To retrieve data, you can directly import `src/adapters/contentful/client` and do requests with the resulting object, eg:

```typescript
import client from "../client"; // directory depends where you are executing requests from
const result = await client.getEntries({
  content_type: "users",
});
```

## Deployment

Once any changes have been merged to the `master` branch, those changes need to be deployed. To do that, simply execute:

```bash
npm run deploy
```

This builds your app using [gh-pages](https://www.npmjs.com/package/gh-pages). To check the supported options and other information, check their documentation.

By default, all of the built files will be under the `gh-pages` branch. This will be the branch to be used as a source when configuring your repository to use Github Pages.

To do that, go to your repository and select _Settings > Pages_. Publish your page using Github pages and select `gh-pages` as the source branch. Leave the directory as `root`.
