<template>
    <main>
        <section class="about">
            <img :src= "user.avatar_url"
            alt="user"
            width="80%"
            height="auto"
            >
            <div class="about__user">
                <h2 id="name">{{ user.name }}</h2>
                <p id="username">{{ user.login }}</p>
                <div class="about__user__body">
                    <p>{{ user.bio }}</p>
                    <button>Edit profile</button>
                    <div class="about__user__body__stat" >
                        <p><i class="fas fa-user-friends"></i> <span>{{ user.followers }}</span> followers</p>
                        <p><i class="fas fa-circle"></i></p>
                        <p><span>{{ user.following }} </span> following</p>
                        <p><i class="fas fa-circle"></i></p>
                        <p><i class="far fa-star"></i> <span>{{ starred.length }}</span></p>
                    </div>
                    <div>
                         <div class="about__user__body_link">
                             <i class="fas fa-map-marker-alt"></i>
                             <p>{{ user.location }}</p>
                         </div>
                         <div class="about__user__body_link">
                             <i class="far fa-envelope"></i>
                             <p>{{ user.type }}</p>
                         </div>
                         <div class="about__user__body_link">
                             <i class="fas fa-link"></i>
                             <p>{{ user.blog }}</p>
                         </div>
                         <div class="about__user__body_link">
                             <i class="fab fa-twitter"></i>
                             <p>@{{ user.twitter_username }}</p>
                         </div>
                    </div>
                </div>
            </div>
            <div class="about__organization">
                <h2>Organizations</h2>
                <div class="logo">
                    <p>logo</p>
                    <p>logo</p>
                    <p>logo</p>
                </div>
            </div>
        </section>

        <section class="repos">
            guigug
        </section>
    </main>
</template>

<script>
export default {
    name: "Profile",
    props: ["user", "starred"]
}
</script>

<style scoped>
    main {
        padding: 50px 40px;
        font-family: 'Roboto', Helvetica, sans-serif;
        /* background: red; */
        display: grid;
        grid-template-columns: 350px 1fr;
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
    .about__user__body {
        font-size: 1rem;   
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
    .about__organization div.logo p {
        margin-right: 5px;
    }
</style>