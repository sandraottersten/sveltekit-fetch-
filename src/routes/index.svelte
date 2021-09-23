<script context="module">

export async function load({ fetch }) {

  const url = 'https://swapi.dev/api/people/'
  const res = await fetch(url, {
    method: 'GET',
    headers: {
      'content-type': 'application/json'
    }
  })

  if (res.ok) {
    return {
      props: {
        data: await res.json()
      }
    };
  }

  return {
    status: res.status,
    error: new Error(`Could not load data`)
  };	
}
</script>

<script>
  export let data

  console.log(data)
</script>


<h1>Hämta från <a href="https://swapi.dev/">https://swapi.dev/</a></h1>