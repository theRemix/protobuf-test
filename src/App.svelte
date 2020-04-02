<script>
  import { writable } from 'svelte/store'
  import proto from './proto/hello'

  let helloBytes = []
  const name = writable('Svelte');
  const greeting = writable('Hi');

  name.subscribe(name => {
    const msg = new proto.Hello({
      name,
      greeting: $greeting,
    })
    helloBytes = proto.Hello.encode(msg).finish();
	});

  greeting.subscribe(greeting => {
    const msg = new proto.Hello({
      name: $name,
      greeting,
    })
    helloBytes = proto.Hello.encode(msg).finish();
	});

</script>

<svelte:head>
  <script src="//cdn.rawgit.com/dcodeIO/protobuf.js/6.8.8/dist/protobuf.min.js"></script>
</svelte:head>

<main>
  <h1>Encoding Hello.proto</h1>
<pre><code>syntax = "proto3";

message Hello &lbrace;
  string name = 1;
  string greeting = 2;
&rbrace;</code></pre>
  <input bind:value={$name} placeholder="name" />
  <input bind:value={$greeting} placeholder="greeting" />
  <p>Encoded ( name: '{$name}', greeting: '{$greeting}')</p>
	<p>Bytes: { helloBytes }</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

  pre, code{
		text-align: left;
    margin: auto;
    margin-bottom: 15px;
    width: 200px;
  }

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
