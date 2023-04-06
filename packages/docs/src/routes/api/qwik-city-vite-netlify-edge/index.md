---
title: \@builder.io/qwik-city/vite/netlify-edge API Reference
---

# **API** @builder.io/qwik-city/vite/netlify-edge

<h2 id="netlifyedgeadapter" data-kind="function" data-kind-label="F"><a aria-hidden="true" tabindex="-1" href="#netlifyedgeadapter"><span class="icon icon-link"></span></a>netlifyEdgeAdapter </h2>

```typescript
export declare function netlifyEdgeAdapter(
  opts?: NetlifyEdgeAdapterOptions
): any;
```

| Parameter | Type                                                    | Description  |
| --------- | ------------------------------------------------------- | ------------ |
| opts      | [NetlifyEdgeAdapterOptions](#netlifyedgeadapteroptions) | _(Optional)_ |

**Returns:**

any

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik-city/adapters/netlify-edge/vite/index.ts" target="_blanks">Edit this section</a></p>

<h2 id="netlifyedgeadapteroptions" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#netlifyedgeadapteroptions"><span class="icon icon-link"></span></a>NetlifyEdgeAdapterOptions </h2>

```typescript
export interface NetlifyEdgeAdapterOptions extends ServerAdapterOptions
```

**Extends:** ServerAdapterOptions

| Property             | Modifiers | Type       | Description                                                                                                                                                                                                                          |
| -------------------- | --------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [functionRoutes?](#) |           | boolean    | <p>_(Optional)_ Determines if the build should generate the edge functions declarations <code>manifest.json</code> file.</p><p>https://docs.netlify.com/edge-functions/declarations/</p><p>Defaults to <code>true</code>.</p>        |
| [staticPaths?](#)    |           | string\[\] | _(Optional)_ Manually add pathnames that should be treated as static paths and not SSR. For example, when these pathnames are requested, their response should come from a static file, rather than a server-side rendered response. |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik-city/adapters/netlify-edge/vite/index.ts" target="_blanks">Edit this section</a></p>