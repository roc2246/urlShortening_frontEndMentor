<script>
    export let image
    export let heading;
    export let paragraph;
</script>

<div class="blurb">
    <div class="blurb__img-box">
        <img src="{image}" alt="{heading}">
    </div>
    <h1 class="heading-tertiary">{heading}</h1>
    <p class="paragraph-tertiary">{paragraph}</p>
</div>