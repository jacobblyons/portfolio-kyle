<template>
    <div class="navbar">
        <div class="navbar-brand">
            LOGO
        </div>
        <div class="navbar-collapse">
            COL
        </div>
    </div>
</template>

<style lang="scss" scoped>
.navbar {
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    justify-content: space-between;
    color: white;

    &-brand{
        padding: {
            top: 1em;
            left: 2em;
            right: 2em;
            bottom: 1em;
        }
    }

    &-collapse {
        padding: {
            top: 1em;
            left: 2em;
            right: 2em;
            bottom: 1em;
        } 
    }
}
</style>
