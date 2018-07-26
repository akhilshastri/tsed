---
sidebar: auto
meta:
 - name: keywords
   description: api typescript node.js documentation Returns decorator
---
# Returns <Badge text="Decorator" type="decorator"/>
<!-- Summary -->
<section class="symbol-info"><table class="is-full-width"><tbody><tr><th>Module</th><td><div class="lang-typescript"><span class="token keyword">import</span> { Returns }&nbsp;<span class="token keyword">from</span>&nbsp;<span class="token string">"@tsed/swagger"</span></div></td></tr><tr><th>Source</th><td><a href="https://github.com/Romakita/ts-express-decorators/blob/v4.30.1/src//swagger/decorators/returns.ts#L0-L0">/swagger/decorators/returns.ts</a></td></tr></tbody></table></section>

<!-- Overview -->
## Overview


<pre><code class="typescript-lang ">function <span class="token function">Returns</span><span class="token punctuation">(</span>statusCode<span class="token punctuation">:</span> <span class="token keyword">number</span><span class="token punctuation">,</span> options<span class="token punctuation">:</span> <a href="/api/swagger/interfaces/ISwaggerResponses.html"><span class="token">ISwaggerResponses</span></a><span class="token punctuation">)</span><span class="token punctuation">:</span> <span class="token keyword">any</span><span class="token punctuation">;</span>
function <span class="token function">Returns</span><span class="token punctuation">(</span>options<span class="token punctuation">:</span> <a href="/api/swagger/interfaces/ISwaggerResponses.html"><span class="token">ISwaggerResponses</span></a><span class="token punctuation">)</span><span class="token punctuation">:</span> <span class="token keyword">any</span><span class="token punctuation">;</span>
function <span class="token function">Returns</span><span class="token punctuation">(</span>model<span class="token punctuation">:</span> <a href="/api/core/interfaces/Type.html"><span class="token">Type</span></a>&lt<span class="token punctuation">;</span><span class="token keyword">any</span>&gt<span class="token punctuation">;</span><span class="token punctuation">)</span><span class="token punctuation">:</span> <span class="token keyword">any</span><span class="token punctuation">;</span>
function <span class="token function">Returns</span><span class="token punctuation">(</span>model<span class="token punctuation">:</span> <a href="/api/core/interfaces/Type.html"><span class="token">Type</span></a>&lt<span class="token punctuation">;</span><span class="token keyword">any</span>&gt<span class="token punctuation">;</span><span class="token punctuation">,</span> options<span class="token punctuation">:</span> <a href="/api/swagger/interfaces/ISwaggerResponses.html"><span class="token">ISwaggerResponses</span></a><span class="token punctuation">)</span><span class="token punctuation">:</span> <span class="token keyword">any</span><span class="token punctuation">;</span>
function <span class="token function">Returns</span><span class="token punctuation">(</span>...args<span class="token punctuation">:</span> <span class="token keyword">any</span><span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
  <span class="token keyword">const</span> configuration<span class="token punctuation">:</span> <span class="token keyword">any</span><span class="token punctuation"> = </span><span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>

  args.<span class="token function">forEach</span><span class="token punctuation">(</span><span class="token punctuation">(</span>value<span class="token punctuation">:</span> <span class="token keyword">any</span><span class="token punctuation">)</span> =&gt<span class="token punctuation">;</span> <span class="token punctuation">{</span>
    configuration<span class="token punctuation">[</span>typeof value<span class="token punctuation">]</span><span class="token punctuation"> = </span>value<span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

  <span class="token keyword">const</span> <span class="token punctuation">{</span><span class="token keyword">number</span><span class="token punctuation">:</span> code<span class="token punctuation">,</span> object<span class="token punctuation">:</span> options<span class="token punctuation"> = </span><span class="token punctuation">{</span><span class="token punctuation">}</span> <span class="token keyword">as</span> <span class="token keyword">any</span><span class="token punctuation">,</span> function<span class="token punctuation">:</span> type<span class="token punctuation">}</span><span class="token punctuation"> = </span>configuration<span class="token punctuation">;</span>

  if <span class="token punctuation">(</span>type<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    options.type<span class="token punctuation"> = </span>type<span class="token punctuation">;</span>
  <span class="token punctuation">}</span>

  return <a href="/api/core/class/Store.html"><span class="token">Store</span></a>.<span class="token function">decorate</span><span class="token punctuation">(</span><span class="token punctuation">(</span>store<span class="token punctuation">:</span> <a href="/api/core/class/Store.html"><span class="token">Store</span></a><span class="token punctuation">)</span> =&gt<span class="token punctuation">;</span> <span class="token punctuation">{</span>
    <span class="token keyword">const</span> response<span class="token punctuation"> = </span><span class="token function">mapReturnedResponse</span><span class="token punctuation">(</span>options<span class="token punctuation">)</span><span class="token punctuation">;</span>

    if <span class="token punctuation">(</span>code !== undefined<span class="token punctuation">)</span> <span class="token punctuation">{</span>
      store.<span class="token function">merge</span><span class="token punctuation">(</span>"responses"<span class="token punctuation">,</span> <span class="token punctuation">{</span>
        <span class="token punctuation">[</span>code<span class="token punctuation">]</span><span class="token punctuation">:</span> response
      <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span> else <span class="token punctuation">{</span>
      store.<span class="token function">merge</span><span class="token punctuation">(</span>"response"<span class="token punctuation">,</span> response<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>




<!-- Params -->
Param | Type | Description
---|---|---
 statusCode|<code>number</code>|Code status  options|<code>&lt;a href="/api/swagger/interfaces/ISwaggerResponses.html"&gt;&lt;span class="token"&gt;ISwaggerResponses&lt;/span&gt;&lt;/a&gt;</code>|Swagger responses documentations 



<!-- Description -->
## Description

::: v-pre

Add responses documentation for a specific status code.

## Examples
## With status code

```typescript
 @Returns(404, {description: "Not found"})
 @Returns(200, {description: "OK", type: Model})
 async myMethod(): Promise<Model>  {

 }
```

This example will produce this documentation in swagger:

```json
{
  "responses": {
    "404": {
      "description": "Description"
    },
    "2OO": {
      "description": "Description",
      "schema": {"schemaOfModel": "..."}
    }
  }
}
```

### Without status code

Returns can be use without status code. In this case, the response will be added to the default status code
(200 or the status code seated with `@Status`).

```typescript
 @Returns({description: "Description"})
 async myMethod(): Promise<Model>  {

 }
```

This example will produce this documentation in swagger:

```json
{
  "responses": {
    "200": {
      "description": "Description"
    }
  }
}
```

### With type schema

Returns accept another signature with a type.

```typescript
 @Returns(Model, {description: "Description"}) //OR
 @Returns(Model)
 async myMethod(): Promise<Model>  {

 }
```

This example will produce this documentation in swagger:

```json
{
  "responses": {
    "200": {
      "description": "Description",
      "schema": {"schemaOfModel": "..."}
    }
  }
}
```

:::