start server by running ``` npm run dev ```
start convex for backend by running ``` npx convex dev ```
start ngrok by running ``` ngrok http 5173 ```
 - goto something like "https://1026a90ee4b3.ngrok-free.app" from ngrok
 - allow grok to access localhost by adding something like "b3c2a116a620.ngrok-free.app", which is provided from the web interface
 - add that to vite.config.ts under allowedHosts
 ```
 export default defineConfig({
  plugins: [tailwindcss(), reactRouter(), tsconfigPaths()],
  server: {
    allowedHosts: [
      "1026a90ee4b3.ngrok-free.app"
    ]
  }
});
```


when subscription wasn't working because error pops up when I click subscribe before entering credit card number page, I found out that it was because of env variable not set. see: "npx convex env set FRONTEND_URL http://localhost:5174" just do this and it would work