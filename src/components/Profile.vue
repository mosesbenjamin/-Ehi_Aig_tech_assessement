<template>
    <main>
        <section class="about">
            <div class="about__image-container-sm">
                <img :src= "user.avatar_url"
                alt="user"
                width="80%"
                height="auto"
                >
                <div class="about__image-container-sm__content">
                    <h2 id="name">{{ user.name }}</h2>
                    <p id="username">{{ user.login }}</p>
                </div>
            </div>
            <div class="about__user">
                <h2 id="name">{{ user.name }}</h2>
                <p id="username">{{ user.login }}</p>
                <div class="about__user__body">
                    <button id="status">
                        <i class="far fa-smile"></i>
                        Set status
                    </button>
                    <p>{{ user.bio }}</p>
                    <button>Edit profile</button>
                    <div class="about__user__body__stat" >
                        <p v-if="user.followers"><i class="fas fa-user-friends"></i> <span>{{ user.followers }}</span> followers</p>
                        <p v-else><i class="fas fa-user-friends"></i> <span>0</span> followers</p>
                        <p><i class="fas fa-circle"></i></p>
                        <p v-if="user.following"><span>{{ user.following }} </span> following</p>
                        <p v-else><span>0</span> following</p>
                        <p><i class="fas fa-circle"></i></p>
                        <p v-if="starred.length"><i class="far fa-star"></i> <span>{{ starred.length }}</span></p>
                        <p v-else><i class="far fa-star"></i> <span>0</span></p>
                    </div>
                    <div>
                         <div class="about__user__body_link">
                             <i class="fas fa-map-marker-alt"></i>
                             <p v-if="user.location">{{ user.location }}</p>
                             <p v-else>World</p>
                         </div>
                         <a href="#!" class="about__user__body_link">
                             <i class="far fa-envelope"></i>
                             <a v-if="user.email" :href="user.email">{{ user.email }}</a>
                             <p v-else>email@example.com</p>
                         </a>
                         <a href="#!" class="about__user__body_link">
                             <i class="fas fa-link"></i>
                             <a v-if="user.blog" :href="user.blog" target="_blank">{{ user.blog }}</a>
                             <p v-else>bio..</p>
                         </a>
                         <a href="#!" class="about__user__body_link">
                             <i class="fab fa-twitter"></i>
                             <p v-if="user.twitter_username">@{{ user.twitter_username }}</p>
                             <p v-else>@twitter</p>
                         </a>
                    </div>
                </div>
            </div>
            <div class="about__organization">
                <h2>Organizations</h2>
                <div class="logo" v-if="orgs.length > 0">
                    <Organization v-bind:key="orgs.id" v-bind:orgs="orgs" />
                </div>
                <div class="logo" v-else>
                    <i class="fab fa-github fa-2x"></i>
                    <i class="fab fa-github fa-2x"></i>
                    <i class="fab fa-github fa-2x"></i>
                </div>
            </div>
        </section>

        <section class="repos">
            <nav class="navbar">
                <ul class="navbar-list">
                    <li class="navbar-list-item">
                        <i class="fas fa-book-open"></i>
                        <a href="#!">Overview</a>
                    </li>
                    <li class="navbar-list-item">
                        <i class="fas fa-book"></i>
                        <a href="#!">Repositories {{ repos.length}}</a>
                    </li>
                    <li class="navbar-list-item">
                        <i class="fas fa-tasks"></i>
                        <a href="#!">Projects</a>
                    </li>
                    <li class="navbar-list-item">
                        <i class="fas fa-cube"></i>
                        <a href="#!">Packages</a>
                    </li>
                </ul>
            </nav>
            <div class="repos-nav">
                <form>
                    <input type="text" placeholder="Find a repository...">
                </form>
                <div class="repos-nav__bottom">
                    <button>Type: All  <i class="fas fa-caret-down"></i></button>
                    <button>Language: All  <i class="fas fa-caret-down"></i> </button>
                    <button id="last">
                        <i class="fas fa-book"></i>
                        New
                    </button>
                </div>  
            </div>
            <hr style="border: 1px solid rgba(0, 0, 0, 0.1);">
            <div v-for="repo in repos" v-bind:key="repo.id">
                <Repository v-bind:repo="repo" />
            </div>
        </section>
    </main>
</template>

<script>
import Repository from './Repository'
import Organization from './Organization'

export default {
    name: "Profile",
    components: {
        Repository,
        Organization
    },
    props: ["user", "starred", "repos", "orgs"]
}
</script>

<style scoped>
    nav .navbar-list {
        display: flex;
        list-style-type: none;
    }
    .navbar-list-item {
        margin-right: 30px;
    }
    .navbar-list-item i {
        margin-right: 10px;
    }
    main {
        padding: 80px 40px;
        font-family: 'Roboto', Helvetica, sans-serif;
        display: grid;
        grid-template-columns: 1fr 3fr;
        grid-gap: 30px;
    }
    section.about {
        background: white;
    }
    .about img {
        border-radius: 100%;
    }
    .about__user  {
        padding: 20px 0;
        font-size: 1.4rem;
    }
    #username {
        margin-bottom: 10px;
        font-size: 1.1rem;
        color: rgba(17, 17, 17, 0.5);
        margin-bottom: 10px;
    }
    .about__image-container-sm {
        display: flex; 
        align-items:center;
    }
    .about__image-container-sm div.about__image-container-sm__content {
        margin-left: 20px; 
        display: none;
    }

    .about__user__body {
        font-size: 1rem;   
    }
    .about__user__body button#status {
        display: none;
        opacity: 0.6;
    }
    .about__user__body button {
        width: 100%;
        height: 30px;
        margin: 15px 0;
        border-radius: 0.3rem;
        border:  0.1rem solid rgba(0, 0, 0, 0.1)
    }
    .about__user__body button:focus {
        outline: 0;
    }
    .about__user__body__stat {
        display: flex;
        align-items: center;
        margin-bottom: 30px;
    }
    .about__user__body__stat p span {
        font-weight: bold;
    }
    .about__user__body__stat i.fas.fa-circle {
        font-size: 0.1rem;
        margin-bottom: 7px;
        color: rgba(0, 0, 0, 0.7);
    }
    i {
        color: rgba(0, 0, 0, 0.7);
    }
    .about__user__body_link {
        display: flex;
        margin: 5px 0;
    }
    .about__user__body_link i {
        margin-right: 8px;
    }
    .about__organization div.logo {
        display: flex;
    }
    .about__organization div.logo i {
        margin-right: 10px;
    }
    a {
        color: rgba(0, 0, 0);
    }
    a p:hover {
        text-decoration: underline;
        color: blue;
    }

    section.repos div.repos-nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
    }
    section.repos div.repos-nav form input{
        width: 30em;
        height: 2rem;
        border-radius: 0.3rem;
        border: 0.8px solid rgba(0, 0, 0, 0.3);
        padding: 0 0.6rem;
        margin: 10px 0 20px 0;
    }
    section.repos div.repos-nav form input:focus {
        outline: 0;
    }
    .repos-nav__bottom button {
        height: 35px;
        margin-right: 10px;
        padding: 3px 10px;
        background: #fff;
        border: 0.8px solid rgba(0, 0, 0, 0.3);
        border-radius: 0.3rem;
    }
    .repos-nav__bottom button:focus {
        outline: 0;
    }
    .repos-nav__bottom button#last{
        background:green;
        color: #fff;
    }
    .repos-nav__bottom button#last i {
        color: #fff;
    } 

    .repo-list {
        display: flex;
        justify-content: space-between;
        padding: 30px 0;
        border-bottom: 1px solid rgba(0, 0, 0, 0.1);
    }
    .repo-list button {
        height: 30px;
        padding: 3px 30px;
        background: #fff;
        border: 0.8px solid rgba(0, 0, 0, 0.3);
        border-radius: 0.3rem;
    }
    @media (max-width: 700px) {
        .navbar-list-item {
            margin-right: 5px;
        }
        .navbar-list-item i {
            margin-right: 2px;
        }
        main {
            display: flex;
            flex-direction: column;
        }
        section.about img {
            width: 100px;
            height: 100px;
        }
        section.about div.about__user h2#name,
        section.about div.about__user p#username {
            display: none;
        }
        section.about {
            width: 82vw;
        }
        .about__image-container-sm div.about__image-container-sm__content {
            display: block;
        }
        .about__user__body button#status {
            display: block !important;
        }
        section.repos div.repos-nav form {
            display: none;
        }
        section.repos div.repos-nav form input{
            width: 2em;
            height: 2rem;
            border-radius: 0.3rem;
            border: 0.8px solid rgba(0, 0, 0, 0.3);
            padding: 0 0.6rem;
            margin: 2px 0 2px 0;
        }
        section.repos div.repos-nav form input:focus {
            outline: 0;
        }
        .repos-nav__bottom button {
            height: 35px;
            margin-right: 43px;
            padding: 3px 10px;
            background: #fff;
            border: 0.8px solid rgba(0, 0, 0, 0.3);
            border-radius: 0.3rem;
        }
        .repos-nav__bottom button:focus {
            outline: 0;
        }
        .repos-nav__bottom button#last{
            background:green;
            color: #fff;
        }
        .repos-nav__bottom button#last i {
            color: #fff;
        }
    }

    @media (max-width: 1000px) {
        section.repos div.repos-nav {
            display: flex;
            flex-direction: column;
        }
        section.repos div.repos-nav form input{
            width: 30em;
            height: 2rem;
            border-radius: 0.3rem;
            border: 0.8px solid rgba(0, 0, 0, 0.3);
            padding: 0 0.6rem;
            margin: 10px 0 20px 0;
        }
        section.repos div.repos-nav form input:focus {
            outline: 0;
        }
        .repos-nav__bottom button {
            height: 35px;
            margin-right: 43px;
            padding: 3px 10px;
            background: #fff;
            border: 0.8px solid rgba(0, 0, 0, 0.3);
            border-radius: 0.3rem;
        }
        .repos-nav__bottom button:focus {
            outline: 0;
        }
        .repos-nav__bottom button#last{
            background:green;
            color: #fff;
        }
        .repos-nav__bottom button#last i {
            color: #fff;
        }        
    }
</style>