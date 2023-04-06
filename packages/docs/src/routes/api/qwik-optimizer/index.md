---
title: \@builder.io/qwik/optimizer API Reference
---

# **API** @builder.io/qwik/optimizer

<h2 id="path-basename" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#path-basename"><span class="icon icon-link"></span></a>basename </h2>

```typescript
basename(path: string, ext?: string): string;
```

| Parameter | Type   | Description  |
| --------- | ------ | ------------ |
| path      | string |              |
| ext       | string | _(Optional)_ |

**Returns:**

string

<h2 id="componententrystrategy" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#componententrystrategy"><span class="icon icon-link"></span></a>ComponentEntryStrategy </h2>

```typescript
export interface ComponentEntryStrategy
```

| Property     | Modifiers | Type                         | Description  |
| ------------ | --------- | ---------------------------- | ------------ |
| [manual?](#) |           | Record&lt;string, string&gt; | _(Optional)_ |
| [type](#)    |           | 'component'                  |              |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="createoptimizer" data-kind="variable" data-kind-label="V"><a aria-hidden="true" tabindex="-1" href="#createoptimizer"><span class="icon icon-link"></span></a>createOptimizer </h2>

```typescript
createOptimizer: (optimizerOptions?: OptimizerOptions) => Promise<Optimizer>;
```

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/optimizer.ts" target="_blanks">Edit this section</a></p>

<h2 id="diagnostic" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#diagnostic"><span class="icon icon-link"></span></a>Diagnostic </h2>

```typescript
export interface Diagnostic
```

| Property         | Modifiers | Type                                      | Description |
| ---------------- | --------- | ----------------------------------------- | ----------- |
| [category](#)    |           | [DiagnosticCategory](#diagnosticcategory) |             |
| [code](#)        |           | string \| null                            |             |
| [file](#)        |           | string                                    |             |
| [highlights](#)  |           | [SourceLocation](#sourcelocation)\[\]     |             |
| [message](#)     |           | string                                    |             |
| [scope](#)       |           | string                                    |             |
| [suggestions](#) |           | string\[\] \| null                        |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="diagnosticcategory" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#diagnosticcategory"><span class="icon icon-link"></span></a>DiagnosticCategory </h2>

```typescript
export type DiagnosticCategory = "error" | "warning" | "sourceError";
```

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="path-dirname" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#path-dirname"><span class="icon icon-link"></span></a>dirname </h2>

```typescript
dirname(path: string): string;
```

| Parameter | Type   | Description |
| --------- | ------ | ----------- |
| path      | string |             |

**Returns:**

string

<h2 id="entrystrategy" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#entrystrategy"><span class="icon icon-link"></span></a>EntryStrategy </h2>

```typescript
export type EntryStrategy =
  | InlineEntryStrategy
  | HoistEntryStrategy
  | SingleEntryStrategy
  | HookEntryStrategy
  | ComponentEntryStrategy
  | SmartEntryStrategy;
```

**References:** [InlineEntryStrategy](#inlineentrystrategy), [SingleEntryStrategy](#singleentrystrategy), [HookEntryStrategy](#hookentrystrategy), [ComponentEntryStrategy](#componententrystrategy), [SmartEntryStrategy](#smartentrystrategy)

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="path-extname" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#path-extname"><span class="icon icon-link"></span></a>extname </h2>

```typescript
extname(path: string): string;
```

| Parameter | Type   | Description |
| --------- | ------ | ----------- |
| path      | string |             |

**Returns:**

string

<h2 id="path-format" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#path-format"><span class="icon icon-link"></span></a>format </h2>

```typescript
format(pathObject: {
        root: string;
        dir: string;
        base: string;
        ext: string;
        name: string;
    }): string;
```

| Parameter  | Type                                                                    | Description |
| ---------- | ----------------------------------------------------------------------- | ----------- |
| pathObject | { root: string; dir: string; base: string; ext: string; name: string; } |             |

**Returns:**

string

<h2 id="globalinjections" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#globalinjections"><span class="icon icon-link"></span></a>GlobalInjections </h2>

```typescript
export interface GlobalInjections
```

| Property         | Modifiers | Type                         | Description  |
| ---------------- | --------- | ---------------------------- | ------------ |
| [attributes?](#) |           | { \[key: string\]: string; } | _(Optional)_ |
| [location](#)    |           | 'head' \| 'body'             |              |
| [tag](#)         |           | string                       |              |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="hookanalysis" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#hookanalysis"><span class="icon icon-link"></span></a>HookAnalysis </h2>

```typescript
export interface HookAnalysis
```

| Property               | Modifiers | Type                  | Description |
| ---------------------- | --------- | --------------------- | ----------- |
| [canonicalFilename](#) |           | string                |             |
| [captures](#)          |           | boolean               |             |
| [ctxKind](#)           |           | 'event' \| 'function' |             |
| [ctxName](#)           |           | string                |             |
| [displayName](#)       |           | string                |             |
| [entry](#)             |           | string \| null        |             |
| [extension](#)         |           | string                |             |
| [hash](#)              |           | string                |             |
| [name](#)              |           | string                |             |
| [origin](#)            |           | string                |             |
| [parent](#)            |           | string \| null        |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="hookentrystrategy" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#hookentrystrategy"><span class="icon icon-link"></span></a>HookEntryStrategy </h2>

```typescript
export interface HookEntryStrategy
```

| Property  | Modifiers | Type   | Description |
| --------- | --------- | ------ | ----------- |
| [type](#) |           | 'hook' |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="inlineentrystrategy" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#inlineentrystrategy"><span class="icon icon-link"></span></a>InlineEntryStrategy </h2>

```typescript
export interface InlineEntryStrategy
```

| Property  | Modifiers | Type     | Description |
| --------- | --------- | -------- | ----------- |
| [type](#) |           | 'inline' |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="path-isabsolute" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#path-isabsolute"><span class="icon icon-link"></span></a>isAbsolute </h2>

```typescript
isAbsolute(path: string): boolean;
```

| Parameter | Type   | Description |
| --------- | ------ | ----------- |
| path      | string |             |

**Returns:**

boolean

<h2 id="path-join" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#path-join"><span class="icon icon-link"></span></a>join </h2>

```typescript
join(...paths: string[]): string;
```

| Parameter | Type       | Description |
| --------- | ---------- | ----------- |
| paths     | string\[\] |             |

**Returns:**

string

<h2 id="minifymode" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#minifymode"><span class="icon icon-link"></span></a>MinifyMode </h2>

```typescript
export type MinifyMode = "simplify" | "none";
```

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="path-normalize" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#path-normalize"><span class="icon icon-link"></span></a>normalize </h2>

```typescript
normalize(path: string): string;
```

| Parameter | Type   | Description |
| --------- | ------ | ----------- |
| path      | string |             |

**Returns:**

string

<h2 id="optimizer" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#optimizer"><span class="icon icon-link"></span></a>Optimizer </h2>

```typescript
export interface Optimizer
```

| Property | Modifiers | Type                                | Description                                                          |
| -------- | --------- | ----------------------------------- | -------------------------------------------------------------------- |
| [sys](#) |           | [OptimizerSystem](#optimizersystem) | Optimizer system use. This can be updated with a custom file system. |

| Method                                                        | Description                                                        |
| ------------------------------------------------------------- | ------------------------------------------------------------------ |
| [transformFs(opts)](#optimizer-transformfs)                   | Transforms the directory from the file system.                     |
| [transformFsSync(opts)](#optimizer-transformfssync)           | Transforms the directory from the file system.                     |
| [transformModules(opts)](#optimizer-transformmodules)         | Transforms the input code string, does not access the file system. |
| [transformModulesSync(opts)](#optimizer-transformmodulessync) | Transforms the input code string, does not access the file system. |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="optimizeroptions" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#optimizeroptions"><span class="icon icon-link"></span></a>OptimizerOptions </h2>

```typescript
export interface OptimizerOptions
```

| Property      | Modifiers | Type                                | Description  |
| ------------- | --------- | ----------------------------------- | ------------ |
| [binding?](#) |           | any                                 | _(Optional)_ |
| [sys?](#)     |           | [OptimizerSystem](#optimizersystem) | _(Optional)_ |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="optimizersystem" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#optimizersystem"><span class="icon icon-link"></span></a>OptimizerSystem </h2>

```typescript
export interface OptimizerSystem
```

| Property                 | Modifiers | Type                                                                                     | Description  |
| ------------------------ | --------- | ---------------------------------------------------------------------------------------- | ------------ |
| [cwd](#)                 |           | () =&gt; string                                                                          |              |
| [dynamicImport](#)       |           | (path: string) =&gt; Promise&lt;any&gt;                                                  |              |
| [env](#)                 |           | [SystemEnvironment](#systemenvironment)                                                  |              |
| [getInputFiles?](#)      |           | (rootDir: string) =&gt; Promise&lt;[TransformModuleInput](#transformmoduleinput)\[\]&gt; | _(Optional)_ |
| [os](#)                  |           | string                                                                                   |              |
| [path](#)                |           | [Path](#path)                                                                            |              |
| [strictDynamicImport](#) |           | (path: string) =&gt; Promise&lt;any&gt;                                                  |              |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="path-parse" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#path-parse"><span class="icon icon-link"></span></a>parse </h2>

```typescript
parse(path: string): {
        root: string;
        dir: string;
        base: string;
        ext: string;
        name: string;
    };
```

| Parameter | Type   | Description |
| --------- | ------ | ----------- |
| path      | string |             |

**Returns:**

{ root: string; dir: string; base: string; ext: string; name: string; }

<h2 id="path" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#path"><span class="icon icon-link"></span></a>Path </h2>

```typescript
export interface Path
```

| Property       | Modifiers             | Type          | Description |
| -------------- | --------------------- | ------------- | ----------- |
| [delimiter](#) | <code>readonly</code> | string        |             |
| [posix](#)     | <code>readonly</code> | [Path](#path) |             |
| [sep](#)       | <code>readonly</code> | string        |             |
| [win32](#)     | <code>readonly</code> | null          |             |

| Method                                | Description |
| ------------------------------------- | ----------- |
| [basename(path, ext)](#path-basename) |             |
| [dirname(path)](#path-dirname)        |             |
| [extname(path)](#path-extname)        |             |
| [format(pathObject)](#path-format)    |             |
| [isAbsolute(path)](#path-isabsolute)  |             |
| [join(paths)](#path-join)             |             |
| [normalize(path)](#path-normalize)    |             |
| [parse(path)](#path-parse)            |             |
| [relative(from, to)](#path-relative)  |             |
| [resolve(paths)](#path-resolve)       |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="qwikbuildmode" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#qwikbuildmode"><span class="icon icon-link"></span></a>QwikBuildMode </h2>

```typescript
export type QwikBuildMode = "production" | "development";
```

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/plugins/plugin.ts" target="_blanks">Edit this section</a></p>

<h2 id="qwikbuildtarget" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#qwikbuildtarget"><span class="icon icon-link"></span></a>QwikBuildTarget </h2>

```typescript
export type QwikBuildTarget = "client" | "ssr" | "lib" | "test";
```

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/plugins/plugin.ts" target="_blanks">Edit this section</a></p>

<h2 id="qwikbundle" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#qwikbundle"><span class="icon icon-link"></span></a>QwikBundle </h2>

```typescript
export interface QwikBundle
```

| Property             | Modifiers | Type       | Description  |
| -------------------- | --------- | ---------- | ------------ |
| [dynamicImports?](#) |           | string\[\] | _(Optional)_ |
| [imports?](#)        |           | string\[\] | _(Optional)_ |
| [origins?](#)        |           | string\[\] | _(Optional)_ |
| [size](#)            |           | number     |              |
| [symbols?](#)        |           | string\[\] | _(Optional)_ |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="qwikmanifest" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#qwikmanifest"><span class="icon icon-link"></span></a>QwikManifest </h2>

```typescript
export interface QwikManifest
```

| Property         | Modifiers | Type                                                                                                          | Description  |
| ---------------- | --------- | ------------------------------------------------------------------------------------------------------------- | ------------ |
| [bundles](#)     |           | { \[fileName: string\]: [QwikBundle](#qwikbundle); }                                                          |              |
| [injections?](#) |           | [GlobalInjections](#globalinjections)\[\]                                                                     | _(Optional)_ |
| [mapping](#)     |           | { \[symbolName: string\]: string; }                                                                           |              |
| [options?](#)    |           | { target?: string; buildMode?: string; forceFullBuild?: boolean; entryStrategy?: { \[key: string\]: any; }; } | _(Optional)_ |
| [platform?](#)   |           | { \[name: string\]: string; }                                                                                 | _(Optional)_ |
| [symbols](#)     |           | { \[symbolName: string\]: [QwikSymbol](#qwiksymbol); }                                                        |              |
| [version](#)     |           | string                                                                                                        |              |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="qwikrollup" data-kind="function" data-kind-label="F"><a aria-hidden="true" tabindex="-1" href="#qwikrollup"><span class="icon icon-link"></span></a>qwikRollup </h2>

```typescript
export declare function qwikRollup(
  qwikRollupOpts?: QwikRollupPluginOptions
): any;
```

| Parameter      | Type                                                | Description  |
| -------------- | --------------------------------------------------- | ------------ |
| qwikRollupOpts | [QwikRollupPluginOptions](#qwikrolluppluginoptions) | _(Optional)_ |

**Returns:**

any

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/plugins/rollup.ts" target="_blanks">Edit this section</a></p>

<h2 id="qwikrolluppluginoptions" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#qwikrolluppluginoptions"><span class="icon icon-link"></span></a>QwikRollupPluginOptions </h2>

```typescript
export interface QwikRollupPluginOptions
```

| Property                      | Modifiers | Type                                                                                                      | Description                                                                                                                                                                                                                          |
| ----------------------------- | --------- | --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [buildMode?](#)               |           | [QwikBuildMode](#qwikbuildmode)                                                                           | _(Optional)_ Build <code>production</code> or <code>development</code>. Default <code>development</code>                                                                                                                             |
| [debug?](#)                   |           | boolean                                                                                                   | _(Optional)_ Prints verbose Qwik plugin debug logs. Default <code>false</code>                                                                                                                                                       |
| [entryStrategy?](#)           |           | [EntryStrategy](#entrystrategy)                                                                           | _(Optional)_ The Qwik entry strategy to use while building for production. During development the type is always <code>hook</code>. Default <code>{ type: &quot;smart&quot; }</code>)                                                |
| [forceFullBuild?](#)          |           | boolean                                                                                                   | _(Optional)_                                                                                                                                                                                                                         |
| [manifestInput?](#)           |           | [QwikManifest](#qwikmanifest)                                                                             | _(Optional)_ The SSR build requires the manifest generated during the client build. The <code>manifestInput</code> option can be used to manually provide a manifest. Default <code>undefined</code>                                 |
| [manifestOutput?](#)          |           | (manifest: [QwikManifest](#qwikmanifest)) =&gt; Promise&lt;void&gt; \| void                               | _(Optional)_ The client build will create a manifest and this hook is called with the generated build data. Default <code>undefined</code>                                                                                           |
| [optimizerOptions?](#)        |           | [OptimizerOptions](#optimizeroptions)                                                                     | _(Optional)_                                                                                                                                                                                                                         |
| [rootDir?](#)                 |           | string                                                                                                    | _(Optional)_ The root of the application, which is commonly the same directory as <code>package.json</code> and <code>rollup.config.js</code>. Default <code>process.cwd()</code>                                                    |
| [srcDir?](#)                  |           | string                                                                                                    | _(Optional)_ The source directory to find all the Qwik components. Since Qwik does not have a single input, the <code>srcDir</code> is used to recursively find Qwik files. Default <code>src</code>                                 |
| [srcInputs?](#)               |           | [TransformModuleInput](#transformmoduleinput)\[\] \| null                                                 | _(Optional)_ Alternative to <code>srcDir</code>, where <code>srcInputs</code> is able to provide the files manually. This option is useful for an environment without a file system, such as a webworker. Default: <code>null</code> |
| [target?](#)                  |           | [QwikBuildTarget](#qwikbuildtarget)                                                                       | _(Optional)_ Target <code>client</code> or <code>ssr</code>. Default <code>client</code>                                                                                                                                             |
| [transformedModuleOutput?](#) |           | ((transformedModules: [TransformModule](#transformmodule)\[\]) =&gt; Promise&lt;void&gt; \| void) \| null | _(Optional)_ Hook that's called after the build and provides all of the transformed modules that were used before bundling.                                                                                                          |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/plugins/rollup.ts" target="_blanks">Edit this section</a></p>

<h2 id="qwiksymbol" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#qwiksymbol"><span class="icon icon-link"></span></a>QwikSymbol </h2>

```typescript
export interface QwikSymbol
```

| Property               | Modifiers | Type                  | Description |
| ---------------------- | --------- | --------------------- | ----------- |
| [canonicalFilename](#) |           | string                |             |
| [captures](#)          |           | boolean               |             |
| [ctxKind](#)           |           | 'function' \| 'event' |             |
| [ctxName](#)           |           | string                |             |
| [displayName](#)       |           | string                |             |
| [hash](#)              |           | string                |             |
| [origin](#)            |           | string                |             |
| [parent](#)            |           | string \| null        |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="qwikvite" data-kind="function" data-kind-label="F"><a aria-hidden="true" tabindex="-1" href="#qwikvite"><span class="icon icon-link"></span></a>qwikVite </h2>

```typescript
export declare function qwikVite(qwikViteOpts?: QwikVitePluginOptions): any;
```

| Parameter    | Type                                            | Description  |
| ------------ | ----------------------------------------------- | ------------ |
| qwikViteOpts | [QwikVitePluginOptions](#qwikvitepluginoptions) | _(Optional)_ |

**Returns:**

any

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/plugins/vite.ts" target="_blanks">Edit this section</a></p>

<h2 id="qwikvitedevresponse" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#qwikvitedevresponse"><span class="icon icon-link"></span></a>QwikViteDevResponse </h2>

```typescript
export interface QwikViteDevResponse
```

| Property                  | Modifiers | Type                      | Description  |
| ------------------------- | --------- | ------------------------- | ------------ |
| [\_qwikEnvData?](#)       |           | Record&lt;string, any&gt; | _(Optional)_ |
| [\_qwikRenderResolve?](#) |           | () =&gt; void             | _(Optional)_ |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/plugins/vite.ts" target="_blanks">Edit this section</a></p>

<h2 id="qwikviteplugin" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#qwikviteplugin"><span class="icon icon-link"></span></a>QwikVitePlugin </h2>

```typescript
export interface QwikVitePlugin
```

| Property  | Modifiers | Type                                    | Description |
| --------- | --------- | --------------------------------------- | ----------- |
| [api](#)  |           | [QwikVitePluginApi](#qwikvitepluginapi) |             |
| [name](#) |           | 'vite-plugin-qwik'                      |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/plugins/vite.ts" target="_blanks">Edit this section</a></p>

<h2 id="qwikvitepluginapi" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#qwikvitepluginapi"><span class="icon icon-link"></span></a>QwikVitePluginApi </h2>

```typescript
export interface QwikVitePluginApi
```

| Property             | Modifiers | Type                                           | Description |
| -------------------- | --------- | ---------------------------------------------- | ----------- |
| [getClientOutDir](#) |           | () =&gt; string \| null                        |             |
| [getManifest](#)     |           | () =&gt; [QwikManifest](#qwikmanifest) \| null |             |
| [getOptimizer](#)    |           | () =&gt; [Optimizer](#optimizer) \| null       |             |
| [getOptions](#)      |           | () =&gt; NormalizedQwikPluginOptions           |             |
| [getRootDir](#)      |           | () =&gt; string \| null                        |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/plugins/vite.ts" target="_blanks">Edit this section</a></p>

<h2 id="qwikvitepluginoptions" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#qwikvitepluginoptions"><span class="icon icon-link"></span></a>QwikVitePluginOptions </h2>

```typescript
export interface QwikVitePluginOptions
```

| Property                      | Modifiers | Type                                                                                                                                                                | Description                                                                                                                                                                                          |
| ----------------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [client?](#)                  |           | { input?: string\[\] \| string; devInput?: string; outDir?: string; manifestOutput?: (manifest: [QwikManifest](#qwikmanifest)) =&gt; Promise&lt;void&gt; \| void; } | _(Optional)_                                                                                                                                                                                         |
| [debug?](#)                   |           | boolean                                                                                                                                                             | _(Optional)_ Prints verbose Qwik plugin debug logs. Default <code>false</code>                                                                                                                       |
| [devTools?](#)                |           | { clickToSource: string\[\] \| false; }                                                                                                                             | _(Optional)_                                                                                                                                                                                         |
| [entryStrategy?](#)           |           | [EntryStrategy](#entrystrategy)                                                                                                                                     | _(Optional)_ The Qwik entry strategy to use while building for production. During development the type is always <code>hook</code>. Default <code>{ type: &quot;smart&quot; }</code>)                |
| [optimizerOptions?](#)        |           | [OptimizerOptions](#optimizeroptions)                                                                                                                               | _(Optional)_ Options for the Qwik optimizer. Default <code>undefined</code>                                                                                                                          |
| [srcDir?](#)                  |           | string                                                                                                                                                              | _(Optional)_ The source directory to find all the Qwik components. Since Qwik does not have a single input, the <code>srcDir</code> is used to recursively find Qwik files. Default <code>src</code> |
| [ssr?](#)                     |           | { input?: string; outDir?: string; manifestInput?: [QwikManifest](#qwikmanifest); }                                                                                 | _(Optional)_                                                                                                                                                                                         |
| [transformedModuleOutput?](#) |           | ((transformedModules: [TransformModule](#transformmodule)\[\]) =&gt; Promise&lt;void&gt; \| void) \| null                                                           | _(Optional)_ Hook that's called after the build and provides all of the transformed modules that were used before bundling.                                                                          |
| [vendorRoots?](#)             |           | string\[\]                                                                                                                                                          | _(Optional)_ List of directories to recursively search for Qwik components or Vendors. Default <code>[]</code>                                                                                       |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/plugins/vite.ts" target="_blanks">Edit this section</a></p>

<h2 id="path-relative" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#path-relative"><span class="icon icon-link"></span></a>relative </h2>

```typescript
relative(from: string, to: string): string;
```

| Parameter | Type   | Description |
| --------- | ------ | ----------- |
| from      | string |             |
| to        | string |             |

**Returns:**

string

<h2 id="path-resolve" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#path-resolve"><span class="icon icon-link"></span></a>resolve </h2>

```typescript
resolve(...paths: string[]): string;
```

| Parameter | Type       | Description |
| --------- | ---------- | ----------- |
| paths     | string\[\] |             |

**Returns:**

string

<h2 id="singleentrystrategy" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#singleentrystrategy"><span class="icon icon-link"></span></a>SingleEntryStrategy </h2>

```typescript
export interface SingleEntryStrategy
```

| Property     | Modifiers | Type                         | Description  |
| ------------ | --------- | ---------------------------- | ------------ |
| [manual?](#) |           | Record&lt;string, string&gt; | _(Optional)_ |
| [type](#)    |           | 'single'                     |              |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="smartentrystrategy" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#smartentrystrategy"><span class="icon icon-link"></span></a>SmartEntryStrategy </h2>

```typescript
export interface SmartEntryStrategy
```

| Property     | Modifiers | Type                         | Description  |
| ------------ | --------- | ---------------------------- | ------------ |
| [manual?](#) |           | Record&lt;string, string&gt; | _(Optional)_ |
| [type](#)    |           | 'smart'                      |              |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="sourcelocation" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#sourcelocation"><span class="icon icon-link"></span></a>SourceLocation </h2>

```typescript
export interface SourceLocation
```

| Property       | Modifiers | Type   | Description |
| -------------- | --------- | ------ | ----------- |
| [endCol](#)    |           | number |             |
| [endLine](#)   |           | number |             |
| [hi](#)        |           | number |             |
| [lo](#)        |           | number |             |
| [startCol](#)  |           | number |             |
| [startLine](#) |           | number |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="sourcemapsoption" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#sourcemapsoption"><span class="icon icon-link"></span></a>SourceMapsOption </h2>

```typescript
export type SourceMapsOption = "external" | "inline" | undefined | null;
```

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="symbolmapper" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#symbolmapper"><span class="icon icon-link"></span></a>SymbolMapper </h2>

```typescript
export type SymbolMapper = Record<
  string,
  readonly [symbol: string, chunk: string]
>;
```

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="symbolmapperfn" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#symbolmapperfn"><span class="icon icon-link"></span></a>SymbolMapperFn </h2>

```typescript
export type SymbolMapperFn = (
  symbolName: string,
  mapper: SymbolMapper | undefined
) => readonly [symbol: string, chunk: string] | undefined;
```

**References:** [SymbolMapper](#symbolmapper)

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="systemenvironment" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#systemenvironment"><span class="icon icon-link"></span></a>SystemEnvironment </h2>

```typescript
export type SystemEnvironment =
  | "node"
  | "deno"
  | "webworker"
  | "browsermain"
  | "unknown";
```

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="optimizer-transformfs" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#optimizer-transformfs"><span class="icon icon-link"></span></a>transformFs </h2>

Transforms the directory from the file system.

```typescript
transformFs(opts: TransformFsOptions): Promise<TransformOutput>;
```

| Parameter | Type                                      | Description |
| --------- | ----------------------------------------- | ----------- |
| opts      | [TransformFsOptions](#transformfsoptions) |             |

**Returns:**

Promise&lt;[TransformOutput](#transformoutput)&gt;

<h2 id="transformfsoptions" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#transformfsoptions"><span class="icon icon-link"></span></a>TransformFsOptions </h2>

```typescript
export interface TransformFsOptions extends TransformOptions
```

**Extends:** [TransformOptions](#transformoptions)

| Property         | Modifiers | Type       | Description |
| ---------------- | --------- | ---------- | ----------- |
| [vendorRoots](#) |           | string\[\] |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="optimizer-transformfssync" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#optimizer-transformfssync"><span class="icon icon-link"></span></a>transformFsSync </h2>

Transforms the directory from the file system.

```typescript
transformFsSync(opts: TransformFsOptions): TransformOutput;
```

| Parameter | Type                                      | Description |
| --------- | ----------------------------------------- | ----------- |
| opts      | [TransformFsOptions](#transformfsoptions) |             |

**Returns:**

[TransformOutput](#transformoutput)

<h2 id="transformmodule" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#transformmodule"><span class="icon icon-link"></span></a>TransformModule </h2>

```typescript
export interface TransformModule
```

| Property     | Modifiers | Type                                  | Description |
| ------------ | --------- | ------------------------------------- | ----------- |
| [code](#)    |           | string                                |             |
| [hook](#)    |           | [HookAnalysis](#hookanalysis) \| null |             |
| [isEntry](#) |           | boolean                               |             |
| [map](#)     |           | string \| null                        |             |
| [path](#)    |           | string                                |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="transformmoduleinput" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#transformmoduleinput"><span class="icon icon-link"></span></a>TransformModuleInput </h2>

```typescript
export interface TransformModuleInput
```

| Property  | Modifiers | Type   | Description |
| --------- | --------- | ------ | ----------- |
| [code](#) |           | string |             |
| [path](#) |           | string |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="optimizer-transformmodules" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#optimizer-transformmodules"><span class="icon icon-link"></span></a>transformModules </h2>

Transforms the input code string, does not access the file system.

```typescript
transformModules(opts: TransformModulesOptions): Promise<TransformOutput>;
```

| Parameter | Type                                                | Description |
| --------- | --------------------------------------------------- | ----------- |
| opts      | [TransformModulesOptions](#transformmodulesoptions) |             |

**Returns:**

Promise&lt;[TransformOutput](#transformoutput)&gt;

<h2 id="transformmodulesoptions" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#transformmodulesoptions"><span class="icon icon-link"></span></a>TransformModulesOptions </h2>

```typescript
export interface TransformModulesOptions extends TransformOptions
```

**Extends:** [TransformOptions](#transformoptions)

| Property   | Modifiers | Type                                              | Description |
| ---------- | --------- | ------------------------------------------------- | ----------- |
| [input](#) |           | [TransformModuleInput](#transformmoduleinput)\[\] |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="optimizer-transformmodulessync" data-kind="method-signature" data-kind-label="M"><a aria-hidden="true" tabindex="-1" href="#optimizer-transformmodulessync"><span class="icon icon-link"></span></a>transformModulesSync </h2>

Transforms the input code string, does not access the file system.

```typescript
transformModulesSync(opts: TransformModulesOptions): TransformOutput;
```

| Parameter | Type                                                | Description |
| --------- | --------------------------------------------------- | ----------- |
| opts      | [TransformModulesOptions](#transformmodulesoptions) |             |

**Returns:**

[TransformOutput](#transformoutput)

<h2 id="transformoptions" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#transformoptions"><span class="icon icon-link"></span></a>TransformOptions </h2>

```typescript
export interface TransformOptions
```

| Property                 | Modifiers | Type                            | Description  |
| ------------------------ | --------- | ------------------------------- | ------------ |
| [entryStrategy?](#)      |           | [EntryStrategy](#entrystrategy) | _(Optional)_ |
| [explicitExtensions?](#) |           | boolean                         | _(Optional)_ |
| [isServer?](#)           |           | boolean                         | _(Optional)_ |
| [minify?](#)             |           | [MinifyMode](#minifymode)       | _(Optional)_ |
| [mode?](#)               |           | EmitMode                        | _(Optional)_ |
| [preserveFilenames?](#)  |           | boolean                         | _(Optional)_ |
| [regCtxName?](#)         |           | string\[\]                      | _(Optional)_ |
| [rootDir?](#)            |           | string                          | _(Optional)_ |
| [scope?](#)              |           | string                          | _(Optional)_ |
| [sourceMaps?](#)         |           | boolean                         | _(Optional)_ |
| [srcDir](#)              |           | string                          |              |
| [stripCtxName?](#)       |           | string\[\]                      | _(Optional)_ |
| [stripEventHandlers?](#) |           | boolean                         | _(Optional)_ |
| [stripExports?](#)       |           | string\[\]                      | _(Optional)_ |
| [transpileJsx?](#)       |           | boolean                         | _(Optional)_ |
| [transpileTs?](#)        |           | boolean                         | _(Optional)_ |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="transformoutput" data-kind="interface" data-kind-label="I"><a aria-hidden="true" tabindex="-1" href="#transformoutput"><span class="icon icon-link"></span></a>TransformOutput </h2>

```typescript
export interface TransformOutput
```

| Property          | Modifiers | Type                                    | Description |
| ----------------- | --------- | --------------------------------------- | ----------- |
| [diagnostics](#)  |           | [Diagnostic](#diagnostic)\[\]           |             |
| [isJsx](#)        |           | boolean                                 |             |
| [isTypeScript](#) |           | boolean                                 |             |
| [modules](#)      |           | [TransformModule](#transformmodule)\[\] |             |

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="transpileoption" data-kind="type-alias" data-kind-label="T"><a aria-hidden="true" tabindex="-1" href="#transpileoption"><span class="icon icon-link"></span></a>TranspileOption </h2>

```typescript
export type TranspileOption = boolean | undefined | null;
```

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/types.ts" target="_blanks">Edit this section</a></p>

<h2 id="versions" data-kind="variable" data-kind-label="V"><a aria-hidden="true" tabindex="-1" href="#versions"><span class="icon icon-link"></span></a>versions </h2>

```typescript
versions: {
  qwik: string;
}
```

<p class="api-edit"><a href="https://github.com/BuilderIO/qwik/tree/main/packages/qwik/src/optimizer/src/versions.ts" target="_blanks">Edit this section</a></p>