<template>
    <div>
        <div id="sidebar-cont">
            <div class="profile">
                <div class="pic">
                    <img src="../assets/pic.png" alt="User Picture">
                </div>
                <p>{{ userName }}</p>
            </div>

            <ul class="menu-list">
                <li class="list"><i class="fa-solid fa-table-columns"></i><span>Dashboard</span></li>
                <li class="list"><i class="fa-solid fa-bars-progress"></i><span>Tasks</span></li>
                <li @click="collapsSidebar" class="list logout"><i
                        class="fa-solid fa-right-from-bracket"></i><span>Logout</span></li>
            </ul>
        </div>
    </div>
</template>
    
<script>
export default {
    name: 'side-bar',
    data() {
        return {
            userName: 'Mohsen Ahmadi',
        }
    },
    methods: {
        collapsSidebar() {
            document.querySelector('#sidebar-cont').classList.toggle('collaps_sidebar');
        }
    }

}
</script>

<style scoped>
#sidebar-cont {
    width: 350px;
    /* min-width: 300px; */
    height: 100vh;
    background-color: white;
    transition: .1s ease;
    padding: 20px 15px;
}

#sidebar-cont .menu-list .logout {
    margin-top: auto;
}

#sidebar-cont .menu-list {
    height: 82vh;
    /* background-color: gainsboro; */
    display: flex;
    flex-direction: column;
}





/* collaps sidbar */



#sidebar-cont .profile {
    display: flex;
    justify-content: start;
    align-items: center;
    background-color: var(--primary-color);
    border-radius: 10px;
    /* height: 72px; */
    padding: 10px 15px;
    color: white;
}

#sidebar-cont .profile .pic {
    width: 52px;
    height: 52px;
    border-radius: 50px;
    overflow: hidden;
    margin-right: 20px;
}

#sidebar-cont .profile .pic img {
    width: 100%;
    height: 100%;
}

#sidebar-cont .menu-list {
    margin-top: 40px;
}

#sidebar-cont .menu-list .list {
    list-style: none;
    padding: 20px 30px;
    display: flex;
    align-items: center;
    border-radius: 10px;
    cursor: pointer;
    font-weight: 500;
    /* transition: 0.1s linear; */
}

#sidebar-cont .menu-list .list i {
    opacity: 0.3;
    font-size: 1.3rem;
    margin-right: 15px;
}

#sidebar-cont .menu-list .list:hover {
    background-color: rgba(71, 181, 255, 0.1);
    color: var(--primary-color);
}

#sidebar-cont .menu-list .list:hover i {
    opacity: 1;
}













.collaps_sidebar {
    width: 100px !important;
}

.collaps_sidebar .profile p,
.collaps_sidebar .menu-list .list span {
    display: none !important;
}

.collaps_sidebar .profile {
    justify-content: center !important;
    align-items: center !important;
    padding: 10px 10px !important;
}

.collaps_sidebar .profile .pic {
    margin-right: 0 !important;
}

.collaps_sidebar .menu-list .list {
    justify-content: center !important;
    align-items: center !important;
    /* margin-right: 0 !important; */
}

.collaps_sidebar .menu-list .list i {
    margin-right: 0 !important;
}





@media only screen and (max-width: 768px) {
    #sidebar-cont {
        width: 100px !important;
    }

    #sidebar-cont .profile p,
    #sidebar-cont .menu-list .list span {
        display: none !important;
    }

    #sidebar-cont .profile {
        justify-content: center !important;
        align-items: center !important;
        padding: 10px 10px !important;
    }

    #sidebar-cont .profile .pic {
        margin-right: 0 !important;
    }

    #sidebar-cont .menu-list .list {
        justify-content: center !important;
        align-items: center !important;
        /* margin-right: 0 !important; */
    }

    #sidebar-cont .menu-list .list i {
        margin-right: 0 !important;
    }
}
</style>