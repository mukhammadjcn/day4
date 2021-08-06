<template>
    <div class="istatic row">
        <div class="istatic__img" v-html="img">
            
        </div>
        <div class="istatic__details row">
            <h4 class="istatic__title title">
                {{title}}
            </h4>
            <p class="istatic__label binfo">
                {{num}}
            </p>
        </div>
    </div>
</template>

<script>
export default {
    name : "I-statistics",
    props : ["img", "title", "num"]
}
</script>

<style lang="scss">
.istatic{
    background: #FFFFFF;
    box-shadow: 0px 12px 26px rgba(16, 30, 115, 0.06);
    border-radius: 8px;
    padding: 26px 24px;
    gap: 24px;
    transition: 0.2s ease-in-out;
    &:hover{
        box-shadow: 0px 12px 26px rgba(85, 142, 255, 0.25);
    }
    &__details{
        flex-direction: column;
        align-items: flex-start;
        gap: 4px;
    }
}
</style>