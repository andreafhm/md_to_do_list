<script setup lang="ts">
import IconGeneral from '../icons/IconGeneral.vue'
import IconDay from '../icons/IconDay.vue'
import IconWeek from '../icons/IconWeek.vue'
import IconMonth from '../icons/IconMonth.vue'
import IconUser from '../icons/IconUser.vue'
import IconUp from '../icons/IconUp.vue'
import IconPlus from '../icons/IconPlus.vue'
</script>

<template>
    <aside>
        <div class="logo">
            <img src="../../assets/logo_microdata_blanco.webp" alt="Logo_Microdata">
        </div>
        <div class="user">
            <span class="icon">
                <IconUser />
            </span>
            <h1 class="salute"><b>Bienvenido (a), </b></h1>
            <h1>Lorena</h1>
        </div>
        <div class="menu">

            <router-link class="button" to="/">
                <span class="icon">
                    <IconGeneral />
                </span>
                <span class="text">General</span>
            </router-link>

            <div class="item-button">
                <router-link class="button" to="/">
                    <span class="icon">
                        <IconDay />
                    </span>
                    <span class="text">Mi día</span>

                </router-link>
                <div class="circle-count">
                    <span class="count">1</span>
                </div>

            </div>



            <router-link class="button" to="/">
                <span class="icon">
                    <IconWeek />
                </span>
                <span class="text">Mi semana</span>
            </router-link>

            <router-link class="button" to="/">
                <span class="icon">
                    <IconMonth />
                </span>
                <span class="text">Mi mes</span>
            </router-link>

        </div>

        <div class="list-apart">
            <span class="icon">
                <IconUp />
            </span>

            <h1>
                <b>Mis listas</b>
            </h1>
            <span class="icon-plus">
                <IconPlus />
            </span>

        </div>

    </aside>
</template>

<style lang="css" scoped>
aside {
    display: flex;
    flex-direction: column;
    width: var(--sidebar-width);
    overflow: hidden;
    min-height: 100vh;
    padding: 1rem;

    background-color: var(--dark);
    color: var(--light);

    .logo {
        margin-top: 1rem;
        margin-bottom: 1rem;

        img {
            width: auto;
        }
    }

    .user {
        display: flex;
        margin-top: 2rem;
        margin-bottom: 2rem;
        align-items: center;

        .salute {
            margin-right: 0.5rem;
        }

        .icon {
            margin-right: 1rem;
        }
    }

    .menu {
        margin: 0 0.5rem;

        .button {
            display: flex;
            align-items: center;
            text-decoration: none;
            border-radius: 4px;
            width: 15rem;
            padding: 0.5rem 1rem;

            .text {
                color: var(--light);
            }

            .icon {
                font-size: 2rem;
                color: var(--light);
                padding-right: 1rem;
            }

            

            .count-circle {
                margin-left: auto;
            }
        }

    }

    .item-button {
        display: flex;
        align-items: center;
        justify-content: space-between;
        
        &:hover {
                background-color: var(--primary);

                .text {
                    color: var(--light)
                }

                .icon {
                    color: var(--light)
                }
            }

    }

    .list-apart {
        margin-top: 2rem;
        display: flex;
        align-items: center;

        .icon {
            margin-right: 1rem;
        }

        .icon-plus {
            margin-left: 6rem;
        }
    }

    @media (max-width: 768px) {
        position: fixed;
        z-index: 99;
    }
}
</style>