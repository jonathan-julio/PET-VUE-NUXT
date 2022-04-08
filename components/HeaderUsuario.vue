<template>
    <div>
        <b-navbar background="black" toggleable="lg" type="light" variant="suscess">
            <b-collapse id="nav-collapse" isnav>
                <b-navbar-nav>
                    <b-nav-item to="usuario/pets/">Pets</b-nav-item>
                    <b-nav-item to="usuario/consultas/">Consultas</b-nav-item>
                </b-navbar-nav>
                <b-navbar-nav class="ml-auto">
                    <b-nav-item to="/">Sair</b-nav-item>
                </b-navbar-nav>
            </b-collapse>                    
        </b-navbar>
    </div>
</template>
<script>

export default {
    name: 'Header'
}
</script>
