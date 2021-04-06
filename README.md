![Alt Text](https://cdn.discordapp.com/attachments/796178474762502168/828869926089392189/simplescreenrecorder-2021-04-06.gif)


# Get started

Kalo pen ngerun programnya, tinggal kek gini aja:

```bash
cd svelte-dragulajs
npm install
```

...then start [Rollup](https://rollupjs.org):

```bash
npm run dev
```

trus cekidot ke [localhost:5000](http://localhost:5000), kamu bakalan bisa melihat aplikasimu telah berjalan. kalo pengen ngedit source codenya, ada di folder `src`, lalu save aja, nanti bisa dilihat perbedaannya.


Kalo kamu pake VSCode, aku rekomendasikan untuk menginstall extensionnya terlebih dahulu, biar mantab..
[Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode). 
<br/>
<br/>
<br/>

# Petunjuk bawaan dari SvelteJS
## Building and running in production mode

To create an optimised version of the app:

```bash
npm run build
```

You can run the newly built app with `npm run start`. This uses [sirv](https://github.com/lukeed/sirv), which is included in your package.json's `dependencies` so that the app will work when you deploy to platforms like [Heroku](https://heroku.com).


## Single-page app mode

By default, sirv will only respond to requests that match files in `public`. This is to maximise compatibility with static fileservers, allowing you to deploy your app anywhere.

If you're building a single-page app (SPA) with multiple routes, sirv needs to be able to respond to requests for *any* path. You can make it so by editing the `"start"` command in package.json:

```js
"start": "sirv public --single"
```

## Using TypeScript
This template already with Typescript


## Deploying to the web

### With [Vercel](https://vercel.com)

Install `vercel` if you haven't already:

```bash
npm install -g vercel
```

Then, from within your project folder:

```bash
cd public
vercel deploy --name my-project
```