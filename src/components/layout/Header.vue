<template>
    <header>
        <nav class="navbar">
            <ul class="navbar-list">
                <li class="navbar-list-item">
                    <i class="fas fa-bars fa-2x menu-icon"></i>
                </li>
                <li class="navbar-list-item">
                    <img 
                    src="../../assets/github_logo.png" 
                    alt="logo"
                    height="40px"
                    width="40px"
                    style="border-radius: 50%"
                    >
                </li>
                <li class="navbar-list-item nav-sm">
                    <form>
                        <input type="text" placeholder="Search or jumb to...">
                    </form>
                </li>
                <li class="navbar-list-item nav-sm">
                    <a href="#!">Pull requests</a>
                </li>
                <li class="navbar-list-item nav-sm">
                    <a href="#!">Issues</a>
                </li>
                <li class="navbar-list-item nav-sm">
                    <a href="#!">Marketplace</a>
                </li>
                <li class="navbar-list-item nav-sm">
                    <a href="#!">Explore</a>
                </li>
                <div class="navbar-right">
                    <a href="#!">
                        <i class="fas fa-bell"></i>
                    </a>
                    <a href="#!" class="navbar-right__middle-item nav-sm">
                        <i class="fas fa-plus i-padding"></i>
                        <i class="fas fa-caret-down"></i>
                    </a>
                    <a href="#!" class="navbar-right__last-item nav-sm">
                        <img 
                        class="nav-sm"
                        :src= "user.avatar_url" 
                        alt="avatar"
                        height="20px"
                        width="20px"
                        style="border-radius: 50%">
                        <i class="fas fa-caret-down nav-sm"></i>
                    </a>
                </div>
            </ul>
        </nav>
    </header>
</template>

<script>
export default {
    name: "Header",
    props: ["user"]
}
</script>

<style scoped>
    .menu-icon{
        display: none;
    }
    nav ul.navbar-list {
        display: flex;
        background: rgba(17, 17, 17, 0.97);
        align-items: center;
        padding: 0 40px;
        height: 3.5rem;
        font-family: 'Roboto', Helvetica, sans-serif;
    }
    nav ul {
        list-style-type: none;
    }
    nav ul li {
        margin-right: 20px;
    }
    form input {
        height: 2rem;
        width: 18rem;
        background: rgba(17, 17, 17, 0.97);
        color: #fff;
        border:  0.1rem solid rgba(255, 255, 255, 0.3);
        border-radius: 0.3rem;
        padding: 0 0.3rem;
    }
    form input:focus {
        outline: 0;
    }
    a {
        text-decoration: none;
        color: rgba(255, 255, 255, 1);
    }
    .navbar-right {
        display: flex;
        margin-left: auto;
    }
    .navbar-right__middle-item {
        margin: 0 20px;
    }
    .navbar-right__last-item {
        display: flex;
    }
    .i-padding {
        padding-right: 8px;
    }
    
    @media (max-width: 1000px) {
        .nav-sm {
            display: none;
        }
        .navbar-list-item img {
            margin-left: 25vw;
        }
        .menu-icon{
            display: block;
            color: rgba(255, 255, 255, 1);
            font-size: 1em;
        }
    }
</style>