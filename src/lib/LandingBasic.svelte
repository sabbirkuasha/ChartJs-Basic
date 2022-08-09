<script>
    import {goto} from '$app/navigation'

    export let heading = "Hello there"
    export let paragraph = "Provident cupiditate voluptatem et in. Quaerat fugiat ut assumenda excepturi exercitationem quasi. In deleniti eaque aut repudiandae et a id nisi."
    export let buttonTxt = "Ger Started"
    export let buttonURL = "/barCharts"

    const buttonURLf = ()=> {
        // this is static way to change route
        // goto("buttonURL")

        // this is dynamic way to change route 
        goto(`${buttonURL}`)
        // console.log(searchedValue)
    }
</script>

<div class="hero min-h-screen bg-base-200">
    <div class="hero-content text-center">
      <div class="w-auto text-center">
        <h1 class="text-5xl font-bold">{heading}</h1>
        <p class="max-w-md py-6 m-auto">{paragraph}</p>
        <button class="btn btn-primary"
                on:click={buttonURLf}>
            {buttonTxt}
        </button>
      </div>
    </div>
</div>