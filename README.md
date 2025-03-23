# Pharmacy App

A modern pharmacy e-commerce application built with React, TypeScript, and Vite.

## Features

- Browse pharmacy products
- Add items to cart
- Checkout process
- User authentication
- Responsive design

## Tech Stack

- React
- TypeScript
- Vite
- React Router
- Tailwind CSS
- Axios

## Development

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Deployment

### Netlify Deployment

The easiest way to deploy this application is using Netlify:

1. Create a Netlify account at [netlify.com](https://www.netlify.com/)
2. Install the Netlify CLI:
   ```
   npm install -g netlify-cli
   ```
3. Log in to your Netlify account:
   ```
   netlify login
   ```
4. Deploy the site:
   ```
   netlify deploy --prod
   ```

Alternatively, you can connect your GitHub repository to Netlify for continuous deployment.

### Manual Deployment

1. Build the project:
   ```
   npm run build
   ```
2. The build output will be in the `dist` directory
3. Upload the contents of the `dist` directory to your web server

## License

MIT 