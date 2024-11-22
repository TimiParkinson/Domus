<script>
    let checked = $state();
    import WhyComponent from "./Why/+page.svelte"
    import HowComponent from "./How/+page.svelte"

    $effect(() => {console.log(checked)});
</script>

<div class="switch">
    
    <div id="button" class="button r">
        <input class="checkbox" type="checkbox" bind:checked={checked}>
        <div class="knobs"></div>                                             
        <div class="layer"></div>
    </div>
</div>

checked: {checked}
{#if checked == false}
    <WhyComponent />
{:else if checked == true}
    <HowComponent />
{/if}

<style lang="sass">
    .switch {
        display: table-cell;
        position: relative;
        width: 200px;
        height: 140px;
        box-sizing: border-box;
    }
    
    
    
    .button-cover:before {
        counter-increment: button-counter;
        content: counter(button-counter);
        position: absolute;
        right: 0;
        bottom: 0;
        color: #d7e3e3;
        font-size: 12px;
        line-height: 1;
        padding: 5px;
    }
    
    .button-cover,
    .knobs,
    .layer {
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
    left: 0;
    }
    
    .button {
        position: relative;
        top: 50%;
        width: 74px;
        height: 36px;
        margin: -20px auto 0 auto;
        overflow: hidden;
    }
    
    .checkbox {
        position: relative;
        width: 100%;
        height: 100%;
        padding: 0;
        margin: 0;
        opacity: 0;
        cursor: pointer;
        z-index: 3;
    }
    
    .knobs {
        z-index: 2;
    }
    
    .layer {
        width: 100%;
        background-color: #ebf7fc;
        transition: 0.3s ease all;
        z-index: 1;
    }
    
    .button.r,
    .button.r .layer {
        border-radius: 100px;
    }
    
    #button .knobs:before {
        content: "Why";
        position: absolute;
        top: 4px;
        left: 4px;
        width: 20px;
        height: 10px;
        color: #fff;
        font-size: 10px;
        font-weight: bold;
        text-align: center;
        line-height: 1;
        padding: 9px 4px;
        background-color: #03a9f4;
        border-radius: 50%;
        transition: 0.3s ease all, left 0.3s cubic-bezier(0.18, 0.89, 0.35, 1.15);
    }
    
    #button .checkbox:active + .knobs:before {
        width: 46px;
        border-radius: 100px;
    }
    
    #button.checkbox:checked:active + .knobs:before {
        margin-left: -26px;
    }
    
    #button .checkbox:checked + .knobs:before {
        content: "How";
        left: 42px;
        background-color: #03a9f4;
    }
    
    #button .checkbox:checked ~ .layer {
    
    }
</style>