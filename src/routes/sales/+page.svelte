<script lang="ts">
    let slides: number = 4
</script>

<div id="slideshow">
    {#each {length: slides} as _, _}
        <div class="slide">
            <div class="single">
                [picture of a single]
            </div>
            <div class="double">
                [picture of a double]
            </div>
        </div>
    {/each}
</div>

<div id="slider">
    {#each {length: slides} as _, _}
        <div class="point"></div>
    {/each}
</div>

<div id="type">
    <p>I</p>
    <p>II</p>
</div>

<style lang="scss">

</style>