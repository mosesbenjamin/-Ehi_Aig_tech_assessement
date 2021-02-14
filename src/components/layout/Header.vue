<template>
    <header class="navbar">
        <img 
        src="../../assets/github_logo.png" 
        alt="logo"
        height="50px"
        width="50px">
        <form>
            <input type="text" placeholder="Search or jumb to...">
        </form>
        <a href="#!">Pull requests</a>
        <a href="#!">Issues</a>
        <a href="#!">Marketplace</a>
        <a href="#!">Explore</a>
        <div class="navbar-right">
            <i class="fas fa-bell"></i>
            <span>
                <i class="fas fa-plus"></i>
                <i class="fas fa-caret-down"></i>
            </span>
             <span id="navbar-right__last">
                <img 
                src="../../assets/github_logo.png" 
                alt="logo"
                height="23px"
                width="23px">
                <i class="fas fa-caret-down"></i>
            </span>
        </div>
    </header>
</template>

<script>
export default {
    
}
</script>

<style scoped>
    .navbar {
        display: flex;
        background: rgba(17, 17, 17, 0.97);
        align-items: center;
        padding: 0 30px;
        height: 4rem;
        font-family: 'Roboto', Helvetica, sans-serif;
    }
    .navbar-right {
        margin-left: auto;
    }
    .navbar-right i {
        color: rgba(255, 255, 255, 1);
    }
    .navbar-right i.fas.fa-bell {
        padding: 0 25px;
    }
    .navbar-right span#navbar-right__last {
        padding: 0 20px;
    }
    .navbar-right span i.fas.fa-caret-down {
        margin: 0 10px;
    }
    .navbar-right span img {
        border-radius: 50%;
    }
    form, a {
        margin-left: 20px;
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
</style>