<script context="module">
  export async function load({ fetch }) {
    const res = await fetch(`https://the-dune-api.herokuapp.com/quotes/1`);
    const data = await res.json();
    console.log(data);
    if (res.ok) {
      return {
	props: { quote: data[0].quote }
      };
    }
  }
</script>

<script>
  import Quotes from '../components/Quotes.svelte';
  export let quote;
</script>

<body>
  <section>
    <Quotes {quote}/>
  </section>
</body>

<style>

  *,
  *::after,
  *::before {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    background-color: #181818;
  }

  body {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    background-color: #181818;
    color: white;
    font-family: Arial;
  }
</style>
