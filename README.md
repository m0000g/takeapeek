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

# Fast Refresh (hot reload) issue?
- Documentation: <https://nextjs.org/docs/architecture/fast-refresh>
- Problem: Changing page.tsx doesn't trigger fast reload.
- Can't see "[Fast Refresh] rebuilding" on console (Maybe is not available in this version?)

`package.json`

```
    "next": "14.1.0",
    "react": "^18",
```

Similar complains:
- <https://github.com/vercel/next.js/issues/51162>
- According to this link Downgrading to Next v 13.2 solves the issue.: <https://github.com/vercel/next.js/issues/57046#issue-1951896689>

What I hava done
- Fixed node version to '20.11.1'
- Remove `.next` and `node_modules` folders, nothing happends.
- Downgrade to 13.2, no dice.
- Using `// @refresh reset` inside page.tsx, nada.
- Try to emulate exactly the files from the instalation, since I changed the font and location of the globals.css while coding <https://ui.shadcn.com/docs/installation/next>