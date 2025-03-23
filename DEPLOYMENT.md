# Deployment Guide for Pharmacy App

This guide provides step-by-step instructions for deploying the Pharmacy App to Netlify.

## Prerequisites

1. A [Netlify](https://www.netlify.com/) account (you can sign up for free)
2. Node.js and npm installed on your machine

## Option 1: Deploy via Netlify UI (Recommended for Beginners)

1. First, build your project:
   ```
   npm install
   npm run build
   ```

2. Log in to your Netlify account.

3. On your Netlify dashboard, click on "Add new site" > "Import an existing project".

4. Select "Deploy manually" (since we've already built the project).

5. Drag and drop the `dist` folder that was created after running `npm run build` into the designated area.

6. Wait for the deployment to complete. Netlify will provide you with a URL for your deployed site.

7. Your Pharmacy App is now live!

## Option 2: Deploy via Netlify CLI

1. Install the Netlify CLI:
   ```
   npm install -g netlify-cli
   ```

2. Log in to your Netlify account through the CLI:
   ```
   netlify login
   ```

3. Initialize a new Netlify site in your project directory:
   ```
   netlify init
   ```

4. Choose "Create & configure a new site" when prompted.

5. Follow the prompts to select your team and provide a site name.

6. When asked about the build command, enter: `npm run build`

7. When asked about the publish directory, enter: `dist`

8. Deploy your site:
   ```
   netlify deploy --prod
   ```

9. Your Pharmacy App is now deployed to Netlify!

## Option 3: Continuous Deployment with GitHub

1. Push your project to a GitHub repository.

2. Log in to your Netlify account.

3. Click on "Add new site" > "Import an existing project".

4. Select GitHub as your Git provider and authorize Netlify.

5. Select your repository from the list.

6. Configure the following build settings:
   - Build command: `npm run build`
   - Publish directory: `dist`

7. Click on "Deploy site".

8. Netlify will now build and deploy your site. It will also automatically redeploy whenever you push changes to your GitHub repository.

## Troubleshooting

### Issue: Page Not Found on Refresh

If you encounter a "Page not found" error when refreshing a page, this is because Netlify doesn't know how to handle client-side routing.

**Solution**: Create or update the `netlify.toml` file in your project root:

```toml
[build]
  command = "npm run build"
  publish = "dist"

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

This configuration tells Netlify to redirect all requests to `index.html`, allowing React Router to handle the routing.

### Issue: Environment Variables

If your app requires environment variables:

1. Add a `.env` file to your project with your variables (prefixed with `VITE_` for Vite to expose them).
2. In Netlify, go to Site Settings > Build & Deploy > Environment > Environment variables.
3. Add the same variables there.

## Support

If you encounter any issues with deployment, please refer to the [Netlify documentation](https://docs.netlify.com/) or contact support.

Happy deploying! 