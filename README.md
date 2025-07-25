# draw2app

![screenshot](https://github.com/niklauslee/draw2app/blob/main/images/screenshot.png?raw=true)

**draw2app** is a simple open-source tool to generate web app from drawing in web browser. You can draw a low-fidelity sketch for a web app and then generate real web app executable in web browser.

This is developed using:

- [DGM.js](https://dgmjs.dev) (diagram library)
- [Astro](https://astro.build) (meta-framework)
- [shadcn/ui](https://ui.shadcn.com/) (React UI components)
- React + TypeScript
- Tailwind CSS (styling)
- OpenAI GPT-4o

## Deployment

This application can be deployed to both **Cloudflare Pages** and **Cloudflare Workers**.

### Cloudflare Pages Deployment

1. Build the application:
   ```bash
   npm run build
   ```

2. Deploy the `dist` directory to Cloudflare Pages

### Cloudflare Workers Deployment

#### Prerequisites
- Install [Wrangler CLI](https://developers.cloudflare.com/workers/wrangler/install-and-update/) or use the included dev dependency
- Configure Wrangler with your Cloudflare account: `npx wrangler login`

#### Configuration
The application includes a `wrangler.toml` configuration file for Workers deployment. You may need to update:

1. **name**: Change the worker name if desired
2. **routes**: Configure your custom domain routes
3. **vars**: Add any required environment variables

#### Deploy to Workers

1. **Option 1: Using the deployment script**
   ```bash
   npm run deploy:workers
   ```

2. **Option 2: Manual deployment**
   ```bash
   npm run build:workers
   npx wrangler deploy
   ```

#### Local Development with Workers Runtime

```bash
# Run with local Workers runtime
npm run preview:workers

# Or with remote Cloudflare services
npm run dev:workers
```

#### Key Differences

- **Pages**: Optimized for static sites with serverless functions
- **Workers**: Pure serverless environment, handles all routing programmatically
- **Build**: Workers deployment uses a memory-optimized build command to handle large bundle sizes

The application works identically on both platforms, with the same features and performance characteristics.
