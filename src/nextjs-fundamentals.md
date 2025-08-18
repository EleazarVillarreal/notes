<image alt="Docker Logo" height="100px" src="../images/nextjs.png" width="100px" />

# Next.js Fundamentals

## General
* Next.js is a React framework for building scalable hybrid applications, supporting both static sites and fully dynamic web apps.

### Styling
* Next.js supports CSS stylesheets that can be imported in the root layout or individual components (though importing them in components is not recommended).
* For global CSS, it’s recommended to import the stylesheet in the root layout to ensure it’s loaded once and applied consistently.
* Use the built-in [CSS Modules](https://github.com/css-modules/css-modules) when you want scoped styles for specific components to prevent collisions.
* For conditional class names, Vercel recommends using the [clsx](https://www.npmjs.com/package/clsx) package.

### Navigation

### Reserved File Names

## Routing
* A root `layout.{tsx,js}` is required for correct route rendering and can be placed in route groups without affecting the URL structure. Without it, routes in that segment cannot render.
* A root `page.{tsx,js}` is only required if you need to display content at the base route (`/`).
* In Next.js, a folder inside the app directory becomes a public route only if it contains a `page.{tsx,js}`. Without this file, the folder remains inaccessible to the public.
* Create a route group by wrapping a directory name in parentheses `()`, allowing logical organization of routes without affecting the URL structure. (e.g, `(dashboard)`)
  * Avoids adding unnecessary URL segments.
  * Opts into or out of specific layouts.
  * Supports multiple root layouts (e.g., one for marketing pages, another for the dashboard).
* Create dynamic routes by adding brackets to the directory name. (e.g., `[slug]`)
* A catch-all route, `[...slug]`, matches all dynamic routes except the root route.
* Adding an extra pair of brackets to a catch-all route creates an optional catch-all route that includes the root route as well (e.g., `[[...slug]]`).
* Use [`generateStaticParams`](https://nextjs.org/docs/app/api-reference/functions/generate-static-params) with dynamic routes to pre-generate routes at build time, improving performance by avoiding on-demand generation at request time.
* Retrieve the slug(s) in the directory’s `page.{tsx,js}` file via the params prop.
* In Next.js 15, you must await the params prop.

## Rendering

## Server Components
* Run entirely on the server, reducing client-side load by handling data fetching, rendering, and heavy computation on the server.
Improves [First Contentful Paint (FCP)](https://web.dev/articles/fcp) and streams content progressively to the client.* 
* Allows direct database queries, internal API calls, or access to secure server-only code without exposing anything to the client or requiring an extra API layer.
* Supports `async/await` directly in the component body, enabling simpler, co-located data fetching.
* No JavaScript is shipped for these components, so they cannot manage state, handle user interactions, or access browser APIs.
* You can render a Server Component within a Client Component by passing it as children.
```TypeScript
// Server component with async & await
async function getContent() {
  const res = await fetch('https://cms.com/...')
	return await res.json()
}

export async function ServerComponent() {
  const data = await getContent()
	return (
		<div>{data.title}</div>
	)
}
```

## Data Fetching

## API Routes