<template>
    <div class="navigation row">
        <router-link to="">Dashboard</router-link>
        <router-link to="">Appointments</router-link>
        <router-link to="">Doctors</router-link>
        <router-link to="">Departments</router-link>
        <router-link to="">Patients</router-link>
        <router-link to="">Payments</router-link>
        <hr>
        <router-link to="">Help</router-link>
    </div>
</template>

<script>
export default {
    name : "Navigation"
}
</script>

<style lang="scss">
.navigation{
    display: none !important;
    justify-content: flex-start;
    width: 100%;
    gap: 32px;
    padding: 14px 0 26px;
    a{
        font-weight: bold;
        font-size: 14px;
        line-height: 20px;
        letter-spacing: 0.1px;
        color: #52575C;
        transition: 0.2s ease-in-out;
        &:hover{
            color: #336CFB;
        }
    }
    hr{
        border-width: 0 2px 0 0;
        height: 20px;
        border-style: solid;
        border-color: #E8E8E8;
    }
}

@media (max-width:996px) {
    .navigation{
        display: flex !important;
    }
}
@media (max-width:776px) {
    .navigation{
        gap: 20px;
        flex-wrap: wrap;
    }
}

@media (max-width:500px) {
    .navigation{
        display: none !important;
    }
}
</style>