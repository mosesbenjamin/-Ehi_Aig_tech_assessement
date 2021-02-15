<template>
    <footer>
        <nav class="navbar">
            <ul class="navbar-list">
                <li class="navbar-list-item" style="opacity: 0.5">
                    &copy; 2021 Github, Inc.
                </li>
                <li class="navbar-list-item">
                    <a href="#!">Terms</a>
                </li>
                <li class="navbar-list-item">
                    <a href="#!">Privacy</a>
                </li>
                <li class="navbar-list-item">
                    <a href="#!">Security</a>
                </li>
                <li class="navbar-list-item">
                    <a href="#!">Status</a>
                </li>
                <li class="navbar-list-item">
                    <a href="#!">Docs</a>
                </li>
                <li class="navbar-list-item logo">
                    <i class="fab fa-github fa-2x"></i>
                </li>
                <li class="navbar-list-item">
                    <a href="#!">Contact Github</a>
                </li>
                <li class="navbar-list-item">
                    <a href="#!">Pricing</a>
                </li>
                <li class="navbar-list-item">
                    <a href="#!">API</a>
                </li>
                <li class="navbar-list-item">
                    <a href="#!">Training</a>
                </li>
                <li class="navbar-list-item">
                    <a href="#!">Blog</a>
                </li>
                <li class="navbar-list-item">
                    <a href="#!">About</a>
                </li>
            </ul>
        </nav>
    </footer>
</template>

<script>
export default {
    name: "Footer"
}
</script>

<style scoped>
    ul {
        list-style-type: none;
        display: flex;
        justify-content: space-around;
        flex-wrap: wrap;
        margin-bottom: 37px;
        font-size: 0.9em;
    }

    li i {
        color: rgba(0, 0, 0, 0.2);
    }
    
    @media (max-width: 700px) {
        li a {
            margin-right: 20px;
        }
        li i {
            display: none
        }
    }
</style>

