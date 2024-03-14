This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

## Running the first time afer clonning?

Install dependencies with `npm install`

## Experimenting issues after changing dependencies?

Try to delete these foldes: `node_modules` and `.next`


## Extra configurations

Let's avoid linters maring @layer and @taiwind with the following error messages
- Unknown at rule @tailwindcss(unknownAtRules)
- '@layer' is not supported by Chrome, Chrome Android, Edge, Opera, Samsung Internet.

### Instructions

1. Create the folder `.vscode`
2. Create this file `settings.json` inside `.vscode`
3. Add the following configuration inside `settings.json`

```
{
  "css.customData": [".vscode/css_custom_data.json"],
  "files.associations": {
    "*.css": "tailwindcss"
  }
}
```

4. Create file  `.hintrc` on root folder
5. Add the following configuration

```