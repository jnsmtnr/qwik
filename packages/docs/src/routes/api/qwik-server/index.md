---
title: \@builder.io/qwik/server API Reference
---

# **API** @builder.io/qwik/server

<h2 id="getqwikloaderscript" data-kind="function" data-kind-label="F"><a aria-hidden="true" tabindex="-1" href="#getqwikloaderscript"><span class="icon icon-link"></span></a>getQwikLoaderScript </h2>

Provides the qwikloader.js file as a string. Useful for tooling to inline the qwikloader script into HTML.

```typescript
export declare function getQwikLoaderScript(opts?: {
  events?: string[];
  debug?: boolean;
}): string;
```

| Parameter | Type                                      | Description  |
| --------- | ----------------------------------------- | ------------ |
| opts      | { events?: string\[\]; debug?: boolean; } | _(Optional)_ |

**Returns:**

string

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/scripts.ts" target="_blanks">Edit this section</a></p>

<h2 id="inorderauto" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#inorderauto"><span class="icon icon-link"></span></a>InOrderAuto </h2>

```typescript
export interface InOrderAuto
```

| Property                  | Modifiers | Type   | Description  |
| ------------------------- | --------- | ------ | ------------ |
| [maximunChunk?](#)        |           | number | _(Optional)_ |
| [maximunInitialChunk?](#) |           | number | _(Optional)_ |
| [strategy](#)             |           | 'auto' |              |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="inorderdisabled" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#inorderdisabled"><span class="icon icon-link"></span></a>InOrderDisabled </h2>

```typescript
export interface InOrderDisabled
```

| Property      | Modifiers | Type       | Description |
| ------------- | --------- | ---------- | ----------- |
| [strategy](#) |           | 'disabled' |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="inorderstreaming" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#inorderstreaming"><span class="icon icon-link"></span></a>InOrderStreaming </h2>

```typescript
export type InOrderStreaming = InOrderAuto | InOrderDisabled | InOrderDirect;
```

**References:** [InOrderAuto](#inorderauto), [InOrderDisabled](#inorderdisabled)

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="prefetchimplementation" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#prefetchimplementation"><span class="icon icon-link"></span></a>PrefetchImplementation </h2>

```typescript
export interface PrefetchImplementation
```

| Property            | Modifiers | Type                                               | Description                                                                                                                                                                                                                                                                                                                              |
| ------------------- | --------- | -------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [linkInsert?](#)    |           | 'js-append' \| 'html-append' \| null               | <p>_(Optional)_ <code>js-append</code>: Use JS runtime to create each <code>&lt;link&gt;</code> and append to the body.</p><p><code>html-append</code>: Render each <code>&lt;link&gt;</code> within html, appended at the end of the body.</p>                                                                                          |
| [linkRel?](#)       |           | 'prefetch' \| 'preload' \| 'modulepreload' \| null | _(Optional)_ Value of the <code>&lt;link rel=&quot;...&quot;&gt;</code> attribute when link is used. Defaults to <code>prefetch</code> if links are inserted.                                                                                                                                                                            |
| [prefetchEvent?](#) |           | 'always' \| null                                   | <p>_(Optional)_ Dispatch a <code>qprefetch</code> event with detail data containing the bundles that should be prefetched. The event dispatch script will be inlined into the document's HTML so any listeners of this event should already be ready to handle the event.</p><p>This implementation will inject a script similar to:</p> |

```
<script type="module">
  document.dispatchEvent(new CustomEvent("qprefetch", { detail:{ "bundles": [...] } }))
</script>
```

<p>By default, the <code>prefetchEvent</code> implementation will be set to <code>always</code>.</p> |
|  [workerFetchInsert?](#) |  | 'always' \| 'no-link-support' \| null | <p>_(Optional)_ <code>always</code>: Always include the worker fetch JS runtime.</p><p><code>no-link-support</code>: Only include the worker fetch JS runtime when the browser doesn't support <code>&lt;link&gt;</code> prefetch/preload/modulepreload.</p> |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="prefetchresource" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#prefetchresource"><span class="icon icon-link"></span></a>PrefetchResource </h2>

```typescript
export interface PrefetchResource
```

| Property     | Modifiers | Type                                      | Description |
| ------------ | --------- | ----------------------------------------- | ----------- |
| [imports](#) |           | [PrefetchResource](#prefetchresource)\[\] |             |
| [url](#)     |           | string                                    |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="prefetchstrategy" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#prefetchstrategy"><span class="icon icon-link"></span></a>PrefetchStrategy </h2>

```typescript
export interface PrefetchStrategy
```

| Property                | Modifiers | Type                                              | Description  |
| ----------------------- | --------- | ------------------------------------------------- | ------------ |
| [implementation?](#)    |           | [PrefetchImplementation](#prefetchimplementation) | _(Optional)_ |
| [symbolsToPrefetch?](#) |           | [SymbolsToPrefetch](#symbolstoprefetch)           | _(Optional)_ |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="qwikloaderoptions" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#qwikloaderoptions"><span class="icon icon-link"></span></a>QwikLoaderOptions </h2>

```typescript
export interface QwikLoaderOptions
```

| Property       | Modifiers | Type                          | Description  |
| -------------- | --------- | ----------------------------- | ------------ |
| [events?](#)   |           | string\[\]                    | _(Optional)_ |
| [include?](#)  |           | 'always' \| 'never' \| 'auto' | _(Optional)_ |
| [position?](#) |           | 'top' \| 'bottom'             | _(Optional)_ |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="render" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#render"><span class="icon icon-link"></span></a>Render </h2>

```typescript
export type Render = RenderToString | RenderToStream;
```

**References:** [RenderToString](#rendertostring), [RenderToStream](#rendertostream)

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="renderoptions" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#renderoptions"><span class="icon icon-link"></span></a>RenderOptions </h2>

```typescript
export interface RenderOptions extends SerializeDocumentOptions
```

**Extends:** [SerializeDocumentOptions](#serializedocumentoptions)

| Property                  | Modifiers | Type                                                                | Description                                                                                                                                                                              |
| ------------------------- | --------- | ------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [base?](#)                |           | string \| ((options: [RenderOptions](#renderoptions)) =&gt; string) | _(Optional)_ Specifies the root of the JS files of the client build. Setting a base, will cause the render of the <code>q:base</code> attribute in the <code>q:container</code> element. |
| [containerAttributes?](#) |           | Record&lt;string, string&gt;                                        | _(Optional)_                                                                                                                                                                             |
| [containerTagName?](#)    |           | string                                                              | _(Optional)_ When set, the app is serialized into a fragment. And the returned html is not a complete document. Defaults to <code>html</code>                                            |
| [locale?](#)              |           | string \| ((options: [RenderOptions](#renderoptions)) =&gt; string) | _(Optional)_ Language to use when rendering the document.                                                                                                                                |
| [prefetchStrategy?](#)    |           | [PrefetchStrategy](#prefetchstrategy) \| null                       | _(Optional)_                                                                                                                                                                             |
| [qwikLoader?](#)          |           | [QwikLoaderOptions](#qwikloaderoptions)                             | _(Optional)_ Specifies if the Qwik Loader script is added to the document or not. Defaults to <code>{ include: true }</code>.                                                            |
| [serverData?](#)          |           | Record&lt;string, any&gt;                                           | _(Optional)_                                                                                                                                                                             |
| [snapshot?](#)            |           | boolean                                                             | _(Optional)_ Defaults to <code>true</code>                                                                                                                                               |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="renderresult" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#renderresult"><span class="icon icon-link"></span></a>RenderResult </h2>

```typescript
export interface RenderResult
```

| Property               | Modifiers | Type                                      | Description  |
| ---------------------- | --------- | ----------------------------------------- | ------------ |
| [isStatic](#)          |           | boolean                                   |              |
| [manifest?](#)         |           | QwikManifest                              | _(Optional)_ |
| [prefetchResources](#) |           | [PrefetchResource](#prefetchresource)\[\] |              |
| [snapshotResult](#)    |           | SnapshotResult \| undefined               |              |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="rendertostream" data-kind="function" data-kind-label="F"><a aria-hidden="true" tabindex="-1" href="#rendertostream"><span class="icon icon-link"></span></a>renderToStream </h2>

```typescript
export type RenderToStream = (
  opts: RenderToStreamOptions
) => Promise<RenderToStreamResult>;
```

**References:** [RenderToStreamOptions](#rendertostreamoptions), [RenderToStreamResult](#rendertostreamresult)

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/render.ts" target="_blanks">Edit this section</a></p>

<h2 id="rendertostream" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#rendertostream"><span class="icon icon-link"></span></a>RenderToStream </h2>

```typescript
export type RenderToStream = (
  opts: RenderToStreamOptions
) => Promise<RenderToStreamResult>;
```

**References:** [RenderToStreamOptions](#rendertostreamoptions), [RenderToStreamResult](#rendertostreamresult)

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="rendertostreamoptions" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#rendertostreamoptions"><span class="icon icon-link"></span></a>RenderToStreamOptions </h2>

```typescript
export interface RenderToStreamOptions extends RenderOptions
```

**Extends:** [RenderOptions](#renderoptions)

| Property        | Modifiers | Type                                  | Description  |
| --------------- | --------- | ------------------------------------- | ------------ |
| [stream](#)     |           | StreamWriter                          |              |
| [streaming?](#) |           | [StreamingOptions](#streamingoptions) | _(Optional)_ |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="rendertostreamresult" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#rendertostreamresult"><span class="icon icon-link"></span></a>RenderToStreamResult </h2>

```typescript
export interface RenderToStreamResult extends RenderResult
```

**Extends:** [RenderResult](#renderresult)

| Property     | Modifiers | Type                                                      | Description |
| ------------ | --------- | --------------------------------------------------------- | ----------- |
| [flushes](#) |           | number                                                    |             |
| [size](#)    |           | number                                                    |             |
| [timing](#)  |           | { firstFlush: number; render: number; snapshot: number; } |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="rendertostring" data-kind="function" data-kind-label="F"><a aria-hidden="true" tabindex="-1" href="#rendertostring"><span class="icon icon-link"></span></a>renderToString </h2>

```typescript
export type RenderToString = (
  opts: RenderToStringOptions
) => Promise<RenderToStringResult>;
```

**References:** [RenderToStringOptions](#rendertostringoptions), [RenderToStringResult](#rendertostringresult)

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/render.ts" target="_blanks">Edit this section</a></p>

<h2 id="rendertostring" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#rendertostring"><span class="icon icon-link"></span></a>RenderToString </h2>

```typescript
export type RenderToString = (
  opts: RenderToStringOptions
) => Promise<RenderToStringResult>;
```

**References:** [RenderToStringOptions](#rendertostringoptions), [RenderToStringResult](#rendertostringresult)

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="rendertostringoptions" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#rendertostringoptions"><span class="icon icon-link"></span></a>RenderToStringOptions </h2>

```typescript
export interface RenderToStringOptions extends RenderOptions
```

**Extends:** [RenderOptions](#renderoptions)

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="rendertostringresult" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#rendertostringresult"><span class="icon icon-link"></span></a>RenderToStringResult </h2>

```typescript
export interface RenderToStringResult extends RenderResult
```

**Extends:** [RenderResult](#renderresult)

| Property    | Modifiers | Type                                  | Description |
| ----------- | --------- | ------------------------------------- | ----------- |
| [html](#)   |           | string                                |             |
| [timing](#) |           | { render: number; snapshot: number; } |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="resolvemanifest" data-kind="function" data-kind-label="F"><a aria-hidden="true" tabindex="-1" href="#resolvemanifest"><span class="icon icon-link"></span></a>resolveManifest </h2>

```typescript
export declare function resolveManifest(
  manifest: QwikManifest | ResolvedManifest | undefined
): ResolvedManifest | undefined;
```

| Parameter | Type                                          | Description |
| --------- | --------------------------------------------- | ----------- |
| manifest  | QwikManifest \| ResolvedManifest \| undefined |             |

**Returns:**

ResolvedManifest \| undefined

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/render.ts" target="_blanks">Edit this section</a></p>

<h2 id="serializedocumentoptions" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#serializedocumentoptions"><span class="icon icon-link"></span></a>SerializeDocumentOptions </h2>

```typescript
export interface SerializeDocumentOptions
```

| Property           | Modifiers | Type                             | Description  |
| ------------------ | --------- | -------------------------------- | ------------ |
| [debug?](#)        |           | boolean                          | _(Optional)_ |
| [manifest?](#)     |           | QwikManifest \| ResolvedManifest | _(Optional)_ |
| [symbolMapper?](#) |           | SymbolMapperFn                   | _(Optional)_ |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="setserverplatform" data-kind="function" data-kind-label="F"><a aria-hidden="true" tabindex="-1" href="#setserverplatform"><span class="icon icon-link"></span></a>setServerPlatform </h2>

```typescript
export declare function setServerPlatform(
  manifest: QwikManifest | ResolvedManifest | undefined
): Promise<void>;
```

| Parameter | Type                                          | Description |
| --------- | --------------------------------------------- | ----------- |
| manifest  | QwikManifest \| ResolvedManifest \| undefined |             |

**Returns:**

Promise&lt;void&gt;

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/index.ts" target="_blanks">Edit this section</a></p>

<h2 id="streamingoptions" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#streamingoptions"><span class="icon icon-link"></span></a>StreamingOptions </h2>

```typescript
export interface StreamingOptions
```

| Property      | Modifiers | Type                                  | Description  |
| ------------- | --------- | ------------------------------------- | ------------ |
| [inOrder?](#) |           | [InOrderStreaming](#inorderstreaming) | _(Optional)_ |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="symbolstoprefetch" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#symbolstoprefetch"><span class="icon icon-link"></span></a>SymbolsToPrefetch </h2>

auto: Prefetch all possible QRLs used by the document. Default

```typescript
export type SymbolsToPrefetch =
  | "auto"
  | ((opts: { manifest: QwikManifest }) => PrefetchResource[]);
```

**References:** [PrefetchResource](#prefetchresource)

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="versions" data-kind="variable" data-kind-label="V"><a aria-hidden="true" tabindex="-1" href="#versions"><span class="icon icon-link"></span></a>versions </h2>

```typescript
versions: {
    readonly qwik: string;
    readonly qwikDom: string;
}
```

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/server/utils.ts" target="_blanks">Edit this section</a></p>