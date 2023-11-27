# On-Demand Incremental Static Regeneration

Demo of On-demand ISR in [Next.js](https://nextjs.org/docs/app/building-your-application/data-fetching/fetching-caching-and-revalidating#revalidating-data) using GitHub Issues. When a new issue is created, a webhook from a GitHub App _pushes_ new changes to the deployed application to regenerate the static page.

## Setup

1. Create a new [GitHub App](https://github.com/settings/apps/new)
   1. Provide the URL of your deployed application for Homepage URL
   1. Ensure Webhook "Active" is checked
   1. Add `<your-site>/api/webhook` as the Webhook URL
   1. Create a Webhook secret and add it to `.env.local` as `GITHUB_WEBHOOK_SECRET`
   1. Give "Read Only" access to Issues
   1. Subscribe to "Issues" events
1. Add the App ID to `.env.local` as `GITHUB_APP_ID`
1. Generate a private key and add it to `.env.local` as `GITHUB_APP_PK_PEM`
1. Install the newly created GitHub App for your repo
1. `https://github.com/settings/apps/<your-app-name>/installations`

## Running Locally

```zsh
$ yarn dev
```

## Learn More

- [Read the documentation](https://nextjs.org/docs/app/building-your-application/data-fetching/fetching-caching-and-revalidating#revalidating-data)
