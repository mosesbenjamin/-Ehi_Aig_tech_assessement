<template>
    <div class="repo-list">
        <a :href="repo.url" target="_blank">{{ repo.name }}</a>
        <button><i class="far fa-star"></i> Star</button>
    </div>
</template>

<script>
export default {
    name: "Repository",
    props: ["repo"]
}
</script>

<style scoped>
    a {
        font-size: 2em;
        color: blue;
        transition: a 100ms ease-in-out ;
    }

    a:hover {
        text-decoration: underline;
    }

    a:active {
        transform: scale(0.95);
    }
    .repo-list {
        display: flex;
        justify-content: space-between;
        padding: 30px 0;
        border-bottom: 1px solid rgba(0, 0, 0, 0.1);
    }
    button {
        height: 30px;
        padding: 3px 30px;
        background: #fff;
        border: 0.8px solid rgba(0, 0, 0, 0.3);
        border-radius: 0.3rem;
    }

    @media (max-width: 700px) {
        a {
            font-size: 1em;
            color: blue;
            transition: a 100ms ease-in-out ;
        }
    }
</style>