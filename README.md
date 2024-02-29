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

## Notes from the developer.

### Solving issues with my local dev environment

1. I got a warning message "unknown at rule @tailwind css"
   I solved the issue by following the instructions I found here: <https://byby.dev/at-rule-tailwind>

a. Add custom data for the CSS language service in VSCode `css_custom_data.json` inside `.vscode folder`

```
{
  "version": 1.1,
  "atDirectives": [
    {
      "name": "@tailwind",
      "description": "Use the @tailwind directive to insert Tailwind's `base`, `components`, `utilities`, and `screens` styles into your CSS."
    }
  ]
}
```

b. Reference that on the `settings.json` file like so

```
{
  "css.customData": [".vscode/css_custom_data.json"]
}
```

c. Install Tailwind CSS IntelliSense extensions for VSCode, adding that to the `settings.json` file as well

```
{
  "files.associations": {
    "*.css": "tailwindcss"
  }
}
```

2. I got an error trying to disable marking '@layer' as not supported. Try to change some rules on the website. I was unable to add this to the `.hintrc` file

```
{
  "extends": ["development"],
  "hints": {
    "compat-api/css": ["error", {"ignore": ["@layer"]}]
  }
}

```

## Additional tips

### ESLINT

If you want to disable `eslint` for just one line you can use the following

Disables for the next line:

```
/* eslint-disable-next-line */
@tailwind base;

/* eslint-disable-next-line */
@tailwind components;

/* eslint-disable-next-line */
@tailwind utilities;

```

Disables from the entire file

```
/* eslint-disable */

```

### Grammarly

You can disable Grammarly for certain parts of your text within a file by using special comments. Here's how you can do it:
To disable Grammarly for a particular section, you can wrap it with comments like this:

```
<!-- grammarly-disable -->

Text you don't want Grammarly to check.

<!-- grammarly-enable -->

```