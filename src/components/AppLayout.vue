<template>
    <div class="app-layout">
        <header class="header">
            <div>
                <img src="../assets/logo.svg" class="img">
            </div>
            <div>Security First</div>
        </header>

        <!-- Menu will be here -->
        <router-view />
    </div>
</template>

<style lang="stylus">
    @import '../style/main';
</style>

<style lang="stylus" scoped>
    .header {
        .img {
            width: 64px;
            height: 64px;
        }
    }
</style>