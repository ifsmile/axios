<div class="cons-inner" data-flag="zh">
        <article><h1 id="doc-zh-axios">axios</h1>

<p>基于 Promise 的 HTTP 请求客户端，可同时在浏览器和 node.js 中使用</p>

<h2 id="doc-zh-功能特性">功能特性</h2>

<ul>
<li>在浏览器中发送 <a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest">XMLHttpRequests</a> 请求</li>
<li>在 node.js 中发送 <a href="http://nodejs.org/api/http.html">http</a>请求</li>
<li>支持 <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise">Promise</a> API</li>
<li>拦截请求和响应</li>
<li>转换请求和响应数据</li>
<li>自动转换 JSON 数据</li>
<li>客户端支持保护安全免受 <a href="http://en.wikipedia.org/wiki/Cross-site_request_forgery">XSRF</a> 攻击</li>
</ul>

<h2 id="doc-zh-浏览器支持">浏览器支持</h2>

<p><a href="https://saucelabs.com/u/axios"><img src="https://saucelabs.com/browser-matrix/axios.svg" alt="Browser Matrix"></a></p>

<h2 id="doc-zh-安装">安装</h2>

<p>使用 bower:</p>

<pre lang="bash" class="  language-bash"><code class=" language-bash">$ bower <span class="token function">install</span> axios
</code></pre>

<p>使用 npm:</p>

<pre lang="bash" class="  language-bash"><code class=" language-bash">$ npm <span class="token function">install</span> axios
</code></pre>

<h2 id="doc-zh-例子">例子</h2>

<p>发送一个 <code>GET</code> 请求</p>

<pre lang="js" class="  language-js"><code class=" language-js"><span class="token comment" spellcheck="true">// Make a request for a user with a given ID</span>
axios<span class="token punctuation">.</span><span class="token keyword">get</span><span class="token punctuation">(</span><span class="token string">'/user?ID=12345'</span><span class="token punctuation">)</span>
  <span class="token punctuation">.</span><span class="token function">then</span><span class="token punctuation">(</span><span class="token keyword">function</span> <span class="token punctuation">(</span>response<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span>
  <span class="token punctuation">.</span><span class="token keyword">catch</span><span class="token punctuation">(</span><span class="token keyword">function</span> <span class="token punctuation">(</span>response<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment" spellcheck="true">// Optionally the request above could also be done as</span>
axios<span class="token punctuation">.</span><span class="token keyword">get</span><span class="token punctuation">(</span><span class="token string">'/user'</span><span class="token punctuation">,</span> <span class="token punctuation">{</span>
    params<span class="token punctuation">:</span> <span class="token punctuation">{</span>
      ID<span class="token punctuation">:</span> <span class="token number">12345</span>
    <span class="token punctuation">}</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span>
  <span class="token punctuation">.</span><span class="token function">then</span><span class="token punctuation">(</span><span class="token keyword">function</span> <span class="token punctuation">(</span>response<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span>
  <span class="token punctuation">.</span><span class="token keyword">catch</span><span class="token punctuation">(</span><span class="token keyword">function</span> <span class="token punctuation">(</span>response<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>

<p>发送一个 <code>POST</code> 请求</p>

<pre lang="js" class="  language-js"><code class=" language-js">axios<span class="token punctuation">.</span><span class="token function">post</span><span class="token punctuation">(</span><span class="token string">'/user'</span><span class="token punctuation">,</span> <span class="token punctuation">{</span>
    firstName<span class="token punctuation">:</span> <span class="token string">'Fred'</span><span class="token punctuation">,</span>
    lastName<span class="token punctuation">:</span> <span class="token string">'Flintstone'</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span>
  <span class="token punctuation">.</span><span class="token function">then</span><span class="token punctuation">(</span><span class="token keyword">function</span> <span class="token punctuation">(</span>response<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span>
  <span class="token punctuation">.</span><span class="token keyword">catch</span><span class="token punctuation">(</span><span class="token keyword">function</span> <span class="token punctuation">(</span>response<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>

<p>发送多个并发请求</p>

<pre lang="js" class="  language-js"><code class=" language-js"><span class="token keyword">function</span> <span class="token function">getUserAccount</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
  <span class="token keyword">return</span> axios<span class="token punctuation">.</span><span class="token keyword">get</span><span class="token punctuation">(</span><span class="token string">'/user/12345'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">function</span> <span class="token function">getUserPermissions</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
  <span class="token keyword">return</span> axios<span class="token punctuation">.</span><span class="token keyword">get</span><span class="token punctuation">(</span><span class="token string">'/user/12345/permissions'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

axios<span class="token punctuation">.</span><span class="token function">all</span><span class="token punctuation">(</span><span class="token punctuation">[</span><span class="token function">getUserAccount</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">,</span> <span class="token function">getUserPermissions</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">]</span><span class="token punctuation">)</span>
  <span class="token punctuation">.</span><span class="token function">then</span><span class="token punctuation">(</span>axios<span class="token punctuation">.</span><span class="token function">spread</span><span class="token punctuation">(</span><span class="token keyword">function</span> <span class="token punctuation">(</span>acct<span class="token punctuation">,</span> perms<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment" spellcheck="true">// Both requests are now complete</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>

<h2 id="doc-zh-axios-api">axios API</h2>

<p>可以通过给 <code>axios</code>传递对应的参数来定制请求：</p>

<h5 id="doc-zh-axios(config)">axios(config)</h5>

<pre lang="js" class="  language-js"><code class=" language-js"><span class="token comment" spellcheck="true">// Send a POST request</span>
<span class="token function">axios</span><span class="token punctuation">(</span><span class="token punctuation">{</span>
  method<span class="token punctuation">:</span> <span class="token string">'post'</span><span class="token punctuation">,</span>
  url<span class="token punctuation">:</span> <span class="token string">'/user/12345'</span><span class="token punctuation">,</span>
  data<span class="token punctuation">:</span> <span class="token punctuation">{</span>
    firstName<span class="token punctuation">:</span> <span class="token string">'Fred'</span><span class="token punctuation">,</span>
    lastName<span class="token punctuation">:</span> <span class="token string">'Flintstone'</span>
  <span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>

<h5 id="doc-zh-axios(url[,-config])">axios(url[, config])</h5>

<pre lang="js" class="  language-js"><code class=" language-js"><span class="token comment" spellcheck="true">// Sned a GET request (default method)</span>
<span class="token function">axios</span><span class="token punctuation">(</span><span class="token string">'/user/12345'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>

<h3 id="doc-zh-请求方法别名">请求方法别名</h3>

<p>为方便起见，我们为所有支持的请求方法都提供了别名</p>

<h5 id="doc-zh-axios.get(url[,-config])">axios.get(url[, config])</h5>

<h5 id="doc-zh-axios.delete(url[,-config])">axios.delete(url[, config])</h5>

<h5 id="doc-zh-axios.head(url[,-config])">axios.head(url[, config])</h5>

<h5 id="doc-zh-axios.post(url[,-data[,-config]])">axios.post(url[, data[, config]])</h5>

<h5 id="doc-zh-axios.put(url[,-data[,-config]])">axios.put(url[, data[, config]])</h5>

<h5 id="doc-zh-axios.patch(url[,-data[,-config]])">axios.patch(url[, data[, config]])</h5>

<h6 id="doc-zh-注意">注意</h6>

<p>当使用别名方法时， <code>url</code>、 <code>method</code> 和 <code>data</code> 属性不需要在 config 参数里面指定。</p>

<h3 id="doc-zh-并发">并发</h3>

<p>处理并发请求的帮助方法</p>

<h5 id="doc-zh-axios.all(iterable)">axios.all(iterable)</h5>

<h5 id="doc-zh-axios.spread(callback)">axios.spread(callback)</h5>

<h3 id="doc-zh-创建一个实例">创建一个实例</h3>

<p>你可以用自定义配置创建一个新的 axios 实例。</p>

<h5 id="doc-zh-axios.create([config])">axios.create([config])</h5>

<pre lang="js" class="  language-js"><code class=" language-js"><span class="token keyword">var</span> instance <span class="token operator">=</span> axios<span class="token punctuation">.</span><span class="token function">create</span><span class="token punctuation">(</span><span class="token punctuation">{</span>
  baseURL<span class="token punctuation">:</span> <span class="token string">'https://some-domain.com/api/'</span><span class="token punctuation">,</span>
  timeout<span class="token punctuation">:</span> <span class="token number">1000</span><span class="token punctuation">,</span>
  headers<span class="token punctuation">:</span> <span class="token punctuation">{</span><span class="token string">'X-Custom-Header'</span><span class="token punctuation">:</span> <span class="token string">'foobar'</span><span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>

<h3 id="doc-zh-实例方法">实例方法</h3>

<p>所有可用的实例方法都列在下面了，指定的配置将会和该实例的配置合并。</p>

<h5 id="doc-zh-axios#request(config)">axios#request(config)</h5>

<h5 id="doc-zh-axios#get(url[,-config])">axios#get(url[, config])</h5>

<h5 id="doc-zh-axios#delete(url[,-config])">axios#delete(url[, config])</h5>

<h5 id="doc-zh-axios#head(url[,-config])">axios#head(url[, config])</h5>

<h5 id="doc-zh-axios#post(url[,-data[,-config]])">axios#post(url[, data[, config]])</h5>

<h5 id="doc-zh-axios#put(url[,-data[,-config]])">axios#put(url[, data[, config]])</h5>

<h5 id="doc-zh-axios#patch(url[,-data[,-config]])">axios#patch(url[, data[, config]])</h5>

<h2 id="doc-zh-请求配置">请求配置</h2>

<p>下面是可用的请求配置项，只有 <code>url</code> 是必需的。如果没有指定 <code>method</code> ，默认的请求方法是 <code>GET</code>。</p>

<pre lang="js" class="  language-js"><code class=" language-js"><span class="token punctuation">{</span>
  <span class="token comment" spellcheck="true">// `url` is the server URL that will be used for the request</span>
  url<span class="token punctuation">:</span> <span class="token string">'/user'</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `method` is the request method to be used when making the request</span>
  method<span class="token punctuation">:</span> <span class="token string">'get'</span><span class="token punctuation">,</span> <span class="token comment" spellcheck="true">// default</span>

  <span class="token comment" spellcheck="true">// `baseURL` will be prepended to `url` unless `url` is absolute. </span>
  <span class="token comment" spellcheck="true">// It can be convenient to set `baseURL` for an instance of axios to pass relative URLs </span>
  <span class="token comment" spellcheck="true">// to methods of that instance.</span>
  baseURL<span class="token punctuation">:</span> <span class="token string">'https://some-domain.com/api/'</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `transformRequest` allows changes to the request data before it is sent to the server</span>
  <span class="token comment" spellcheck="true">// This is only applicable for request methods 'PUT', 'POST', and 'PATCH'</span>
  <span class="token comment" spellcheck="true">// The last function in the array must return a string or an ArrayBuffer</span>
  transformRequest<span class="token punctuation">:</span> <span class="token punctuation">[</span><span class="token keyword">function</span> <span class="token punctuation">(</span>data<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment" spellcheck="true">// Do whatever you want to transform the data</span>

    <span class="token keyword">return</span> data<span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `transformResponse` allows changes to the response data to be made before</span>
  <span class="token comment" spellcheck="true">// it is passed to then/catch</span>
  transformResponse<span class="token punctuation">:</span> <span class="token punctuation">[</span><span class="token keyword">function</span> <span class="token punctuation">(</span>data<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment" spellcheck="true">// Do whatever you want to transform the data</span>

    <span class="token keyword">return</span> data<span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `headers` are custom headers to be sent</span>
  headers<span class="token punctuation">:</span> <span class="token punctuation">{</span><span class="token string">'X-Requested-With'</span><span class="token punctuation">:</span> <span class="token string">'XMLHttpRequest'</span><span class="token punctuation">}</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `params` are the URL parameters to be sent with the request</span>
  params<span class="token punctuation">:</span> <span class="token punctuation">{</span>
    ID<span class="token punctuation">:</span> <span class="token number">12345</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `paramsSerializer` is an optional function in charge of serializing `params`</span>
  <span class="token comment" spellcheck="true">// (e.g. https://www.npmjs.com/package/qs, http://api.jquery.com/jquery.param/)</span>
  paramsSerializer<span class="token punctuation">:</span> <span class="token keyword">function</span><span class="token punctuation">(</span>params<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> Qs<span class="token punctuation">.</span><span class="token function">stringify</span><span class="token punctuation">(</span>params<span class="token punctuation">,</span> <span class="token punctuation">{</span>arrayFormat<span class="token punctuation">:</span> <span class="token string">'brackets'</span><span class="token punctuation">}</span><span class="token punctuation">)</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `data` is the data to be sent as the request body</span>
  <span class="token comment" spellcheck="true">// Only applicable for request methods 'PUT', 'POST', and 'PATCH'</span>
  <span class="token comment" spellcheck="true">// When no `transformRequest` is set, must be a string, an ArrayBuffer or a hash</span>
  data<span class="token punctuation">:</span> <span class="token punctuation">{</span>
    firstName<span class="token punctuation">:</span> <span class="token string">'Fred'</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `timeout` specifies the number of milliseconds before the request times out.</span>
  <span class="token comment" spellcheck="true">// If the request takes longer than `timeout`, the request will be aborted.</span>
  timeout<span class="token punctuation">:</span> <span class="token number">1000</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `withCredentials` indicates whether or not cross-site Access-Control requests</span>
  <span class="token comment" spellcheck="true">// should be made using credentials</span>
  withCredentials<span class="token punctuation">:</span> <span class="token boolean">false</span><span class="token punctuation">,</span> <span class="token comment" spellcheck="true">// default</span>

  <span class="token comment" spellcheck="true">// `adapter` allows custom handling of requests which makes testing easier.</span>
  <span class="token comment" spellcheck="true">// Call `resolve` or `reject` and supply a valid response (see [response docs](#response-api)).</span>
  adapter<span class="token punctuation">:</span> <span class="token keyword">function</span> <span class="token punctuation">(</span>resolve<span class="token punctuation">,</span> reject<span class="token punctuation">,</span> config<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment" spellcheck="true">/* ... */</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `auth` indicates that HTTP Basic auth should be used, and supplies credentials.</span>
  <span class="token comment" spellcheck="true">// This will set an `Authorization` header, overwriting any existing</span>
  <span class="token comment" spellcheck="true">// `Authorization` custom headers you have set using `headers`.</span>
  auth<span class="token punctuation">:</span> <span class="token punctuation">{</span>
    username<span class="token punctuation">:</span> <span class="token string">'janedoe'</span><span class="token punctuation">,</span>
    password<span class="token punctuation">:</span> <span class="token string">'s00pers3cret'</span>
  <span class="token punctuation">}</span>

  <span class="token comment" spellcheck="true">// `responseType` indicates the type of data that the server will respond with</span>
  <span class="token comment" spellcheck="true">// options are 'arraybuffer', 'blob', 'document', 'json', 'text'</span>
  responseType<span class="token punctuation">:</span> <span class="token string">'json'</span><span class="token punctuation">,</span> <span class="token comment" spellcheck="true">// default</span>

  <span class="token comment" spellcheck="true">// `xsrfCookieName` is the name of the cookie to use as a value for xsrf token</span>
  xsrfCookieName<span class="token punctuation">:</span> <span class="token string">'XSRF-TOKEN'</span><span class="token punctuation">,</span> <span class="token comment" spellcheck="true">// default</span>

  <span class="token comment" spellcheck="true">// `xsrfHeaderName` is the name of the http header that carries the xsrf token value</span>
  xsrfHeaderName<span class="token punctuation">:</span> <span class="token string">'X-XSRF-TOKEN'</span><span class="token punctuation">,</span> <span class="token comment" spellcheck="true">// default</span>

  <span class="token comment" spellcheck="true">// `progress` allows handling of progress events for 'POST' and 'PUT uploads'</span>
  <span class="token comment" spellcheck="true">// as well as 'GET' downloads</span>
  progress<span class="token punctuation">:</span> <span class="token keyword">function</span><span class="token punctuation">(</span>progressEvent<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment" spellcheck="true">// Do whatever you want with the native progress event</span>
  <span class="token punctuation">}</span>
<span class="token punctuation">}</span>
</code></pre>

<h2 id="doc-zh-响应的数据结构">响应的数据结构</h2>

<p>响应的数据包括下面的信息：</p>

<pre lang="js" class="  language-js"><code class=" language-js"><span class="token punctuation">{</span>
  <span class="token comment" spellcheck="true">// `data` is the response that was provided by the server</span>
  data<span class="token punctuation">:</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `status` is the HTTP status code from the server response</span>
  status<span class="token punctuation">:</span> <span class="token number">200</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `statusText` is the HTTP status message from the server response</span>
  statusText<span class="token punctuation">:</span> <span class="token string">'OK'</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `headers` the headers that the server responded with</span>
  headers<span class="token punctuation">:</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">,</span>

  <span class="token comment" spellcheck="true">// `config` is the config that was provided to `axios` for the request</span>
  config<span class="token punctuation">:</span> <span class="token punctuation">{</span><span class="token punctuation">}</span>
<span class="token punctuation">}</span>
</code></pre>

<p>当使用 <code>then</code> 或者 <code>catch</code> 时, 你会收到下面的响应：</p>

<pre lang="js" class="  language-js"><code class=" language-js">axios<span class="token punctuation">.</span><span class="token keyword">get</span><span class="token punctuation">(</span><span class="token string">'/user/12345'</span><span class="token punctuation">)</span>
  <span class="token punctuation">.</span><span class="token function">then</span><span class="token punctuation">(</span><span class="token keyword">function</span><span class="token punctuation">(</span>response<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">.</span>data<span class="token punctuation">)</span><span class="token punctuation">;</span>
    console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">.</span>status<span class="token punctuation">)</span><span class="token punctuation">;</span>
    console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">.</span>statusText<span class="token punctuation">)</span><span class="token punctuation">;</span>
    console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">.</span>headers<span class="token punctuation">)</span><span class="token punctuation">;</span>
    console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">.</span>config<span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>

<h2 id="doc-zh-默认配置">默认配置</h2>

<p>你可以为每一个请求指定默认配置。</p>

<h3 id="doc-zh-全局-axios-默认配置">全局 axios 默认配置</h3>

<pre lang="js" class="  language-js"><code class=" language-js">axios<span class="token punctuation">.</span>defaults<span class="token punctuation">.</span>baseURL <span class="token operator">=</span> <span class="token string">'https://api.example.com'</span><span class="token punctuation">;</span>
axios<span class="token punctuation">.</span>defaults<span class="token punctuation">.</span>headers<span class="token punctuation">.</span>common<span class="token punctuation">[</span><span class="token string">'Authorization'</span><span class="token punctuation">]</span> <span class="token operator">=</span> AUTH_TOKEN<span class="token punctuation">;</span>
axios<span class="token punctuation">.</span>defaults<span class="token punctuation">.</span>headers<span class="token punctuation">.</span>post<span class="token punctuation">[</span><span class="token string">'Content-Type'</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token string">'application/x-www-form-urlencoded'</span><span class="token punctuation">;</span>
</code></pre>

<h3 id="doc-zh-自定义实例默认配置">自定义实例默认配置</h3>

<pre lang="js" class="  language-js"><code class=" language-js"><span class="token comment" spellcheck="true">// Set config defaults when creating the instance</span>
<span class="token keyword">var</span> instance <span class="token operator">=</span> axios<span class="token punctuation">.</span><span class="token function">create</span><span class="token punctuation">(</span><span class="token punctuation">{</span>
  baseURL<span class="token punctuation">:</span> <span class="token string">'https://api.example.com'</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment" spellcheck="true">// Alter defaults after instance has been created</span>
instance<span class="token punctuation">.</span>defaults<span class="token punctuation">.</span>headers<span class="token punctuation">.</span>common<span class="token punctuation">[</span><span class="token string">'Authorization'</span><span class="token punctuation">]</span> <span class="token operator">=</span> AUTH_TOKEN<span class="token punctuation">;</span>
</code></pre>

<h3 id="doc-zh-配置的优先顺序">配置的优先顺序</h3>

<p>Config will be merged with an order of precedence. The order is library defaults found in <code>lib/defaults.js</code>, then <code>defaults</code> property of the instance, and finally <code>config</code> argument for the request. The latter will take precedence over the former. Here's an example.</p>

<pre lang="js" class="  language-js"><code class=" language-js"><span class="token comment" spellcheck="true">// Create an instance using the config defaults provided by the library</span>
<span class="token comment" spellcheck="true">// At this point the timeout config value is `0` as is the default for the library</span>
<span class="token keyword">var</span> instance <span class="token operator">=</span> axios<span class="token punctuation">.</span><span class="token function">create</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment" spellcheck="true">// Override timeout default for the library</span>
<span class="token comment" spellcheck="true">// Now all requests will wait 2.5 seconds before timing out</span>
instance<span class="token punctuation">.</span>defaults<span class="token punctuation">.</span>timeout <span class="token operator">=</span> <span class="token number">2500</span><span class="token punctuation">;</span>

<span class="token comment" spellcheck="true">// Override timeout for this request as it's known to take a long time</span>
instance<span class="token punctuation">.</span><span class="token keyword">get</span><span class="token punctuation">(</span><span class="token string">'/longRequest'</span><span class="token punctuation">,</span> <span class="token punctuation">{</span>
  timeout<span class="token punctuation">:</span> <span class="token number">5000</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span> 
</code></pre>

<h2 id="doc-zh-拦截器">拦截器</h2>

<p>你可以在处理 <code>then</code> 或 <code>catch</code> 之前拦截请求和响应</p>

<pre lang="js" class="  language-js"><code class=" language-js"><span class="token comment" spellcheck="true">// 添加一个请求拦截器</span>
axios<span class="token punctuation">.</span>interceptors<span class="token punctuation">.</span>request<span class="token punctuation">.</span><span class="token function">use</span><span class="token punctuation">(</span><span class="token keyword">function</span> <span class="token punctuation">(</span>config<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment" spellcheck="true">// Do something before request is sent</span>
    <span class="token keyword">return</span> config<span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token keyword">function</span> <span class="token punctuation">(</span>error<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment" spellcheck="true">// Do something with request error</span>
    <span class="token keyword">return</span> Promise<span class="token punctuation">.</span><span class="token function">reject</span><span class="token punctuation">(</span>error<span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment" spellcheck="true">// 添加一个响应拦截器</span>
axios<span class="token punctuation">.</span>interceptors<span class="token punctuation">.</span>response<span class="token punctuation">.</span><span class="token function">use</span><span class="token punctuation">(</span><span class="token keyword">function</span> <span class="token punctuation">(</span>response<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment" spellcheck="true">// Do something with response data</span>
    <span class="token keyword">return</span> response<span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token keyword">function</span> <span class="token punctuation">(</span>error<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment" spellcheck="true">// Do something with response error</span>
    <span class="token keyword">return</span> Promise<span class="token punctuation">.</span><span class="token function">reject</span><span class="token punctuation">(</span>error<span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>

<p>移除一个拦截器：</p>

<pre lang="js" class="  language-js"><code class=" language-js"><span class="token keyword">var</span> myInterceptor <span class="token operator">=</span> axios<span class="token punctuation">.</span>interceptors<span class="token punctuation">.</span>request<span class="token punctuation">.</span><span class="token function">use</span><span class="token punctuation">(</span><span class="token keyword">function</span> <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span><span class="token comment" spellcheck="true">/*...*/</span><span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
axios<span class="token punctuation">.</span>interceptors<span class="token punctuation">.</span>request<span class="token punctuation">.</span><span class="token function">eject</span><span class="token punctuation">(</span>myInterceptor<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>

<p>你可以给一个自定义的 axios 实例添加拦截器：</p>

<pre lang="js" class="  language-js"><code class=" language-js"><span class="token keyword">var</span> instance <span class="token operator">=</span> axios<span class="token punctuation">.</span><span class="token function">create</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
instance<span class="token punctuation">.</span>interceptors<span class="token punctuation">.</span>request<span class="token punctuation">.</span><span class="token function">use</span><span class="token punctuation">(</span><span class="token keyword">function</span> <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span><span class="token comment" spellcheck="true">/*...*/</span><span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>

<h2 id="doc-zh-错误处理">错误处理</h2>

<pre lang="js" class="  language-js"><code class=" language-js">axios<span class="token punctuation">.</span><span class="token keyword">get</span><span class="token punctuation">(</span><span class="token string">'/user/12345'</span><span class="token punctuation">)</span>
  <span class="token punctuation">.</span><span class="token keyword">catch</span><span class="token punctuation">(</span><span class="token keyword">function</span> <span class="token punctuation">(</span>response<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">if</span> <span class="token punctuation">(</span>response <span class="token keyword">instanceof</span> <span class="token class-name">Error</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
      <span class="token comment" spellcheck="true">// Something happened in setting up the request that triggered an Error</span>
      console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">'Error'</span><span class="token punctuation">,</span> response<span class="token punctuation">.</span>message<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
      <span class="token comment" spellcheck="true">// The request was made, but the server responded with a status code</span>
      <span class="token comment" spellcheck="true">// that falls out of the range of 2xx</span>
      console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">.</span>data<span class="token punctuation">)</span><span class="token punctuation">;</span>
      console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">.</span>status<span class="token punctuation">)</span><span class="token punctuation">;</span>
      console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">.</span>headers<span class="token punctuation">)</span><span class="token punctuation">;</span>
      console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>response<span class="token punctuation">.</span>config<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>

<h2 id="doc-zh-promises">Promises</h2>

<p>axios 依赖一个原生的 ES6 Promise 实现，如果你的浏览器环境不支持 ES6 Promises，你需要引入 <a href="https://github.com/jakearchibald/es6-promise">polyfill</a></p>

<h2 id="doc-zh-typescript">TypeScript</h2>

<p>axios 包含一个 <a href="http://typescriptlang.org">TypeScript</a> 定义</p>

<pre lang="typescript" class="  language-typescript"><code class=" language-typescript">/// &lt;reference path="axios.d.ts" /&gt;
import * as axios from 'axios';
axios.get('/user?ID=12345');
</code></pre>
