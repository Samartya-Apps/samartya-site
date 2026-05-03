# Astro Starter Kit: Basics

```sh
npm create astro@latest -- --template basics
```

> 🧑‍🚀 **Seasoned astronaut?** Delete this file. Have fun!

## 🚀 Project Structure

Inside of your Astro project, you'll see the following folders and files:

```text
/
├── public/
│   └── favicon.svg
├── src
│   ├── assets
│   │   └── astro.svg
│   ├── components
│   │   └── Welcome.astro
│   ├── layouts
│   │   └── Layout.astro
│   └── pages
│       └── index.astro
└── package.json
```

To learn more about the folder structure of an Astro project, refer to [our guide on project structure](https://docs.astro.build/en/basics/project-structure/).

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

## 📬 Forms (Contact & Schools Trial)

The `/contact` and `/for-schools/request-trial` forms submit directly to
[Web3Forms](https://web3forms.com), which emails the submission to the
inbox associated with the access key (currently `sales@samartya.com`).

The access key is hardcoded in each form's hidden `access_key` input. This
is by design — Web3Forms keys are public; spam protection is handled
server-side via the honeypot (`botcheck` field), per-key rate limits, and
optional hCaptcha (toggle in the Web3Forms dashboard if needed).

To rotate the key or change the destination inbox, update the
`<input name="access_key">` value in:

- `src/pages/contact.astro`
- `src/pages/for-schools/request-trial.astro`

Reference: [Web3Forms Astro guide](https://docs.web3forms.com/how-to-guides/static-site-generators/astro).

## 👀 Want to learn more?

Feel free to check [our documentation](https://docs.astro.build) or jump into our [Discord server](https://astro.build/chat).
