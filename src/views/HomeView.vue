<script>
export default {
    name: 'HomeView'
}
</script>

<template>
    <nav id="navbar" class="nav-menu navbar">
        <ul>
            <li><a href="#hero" class="nav-link scrollto active"><i class="bx bx-home"></i> <span>Home</span></a></li>
            <li><a href="#about" class="nav-link scrollto"><i class="bx bx-user"></i> <span>About</span></a></li>
            <li><a href="#contact" class="nav-link scrollto"><i class="bx bx-envelope"></i> <span>Contact</span></a>
            </li>
        </ul>
    </nav>

    <section id="hero" class="d-flex flex-column justify-content-center align-items-center jumbotron_home">
        <div class="hero-container">
            <h1>Matteo Gatto</h1>
            <p>I'm Full Stack Web Developer Student</p>
        </div>
    </section>
</template>

<style lang="scss" scoped>

</style>