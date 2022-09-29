<script>
    export let className;
    
</script>

<button class={className} on:click><slot /></button>

<style lang="scss">
  @import '../scss/global';
    .btn{
        white-space: nowrap;
        background-color: $cyan;
        color: white;
        font-weight: $fontweight-heavy;
       cursor: pointer;
        &--CTA{
            border-radius: 2rem;
            width: 10rem;
            padding: .5rem;
        }
        &--signup{
            border-radius: 2rem;
            width: 6rem;
            padding: .5rem;
        }
        &--shorten{
            border-radius: .5rem;
            width: 10rem;
            padding: .5rem;
        }
    }

    @media (max-width: 375px){
        .btn{
            &--signup{
                margin-left: .25rem;
                margin-top: 1rem;
            }
            &--shorten{
            border-radius: .5rem;
            width: 100%;
            padding: .5rem;
        }
        }
    }

</style>
