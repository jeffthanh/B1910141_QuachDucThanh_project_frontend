<template>
    <nav class="navbar navbar-expand navbar-dark bg-dark">
        <a href="/" class="navbar-brand">Website Review Phim</a>
        <div class="mr-auto navbar-nav">
            <li class="nav-item">
                <router-link :to="{ name: 'post' }" class="nav-link">
                </router-link>
            </li>
        </div>
    </nav>
</template>