<template>
        <b-card>
            <b-card-title>{{character.id}}</b-card-title>
            <b-card-text>
                
                <h4 class="card-title">{{character.name}}</h4>
                <p class="card-text">Height: {{character.height}}</p>
                <p class="card-text">Weight: {{character.mass}}</p>
                <p class="card-text">Hair Color: {{character.hair_color}}</p>
                <p class="card-text">Eye Color: {{character.eye_color}}</p>
            </b-card-text>
        </b-card>
</template>

<script>
export default {
    props: ['character'],
    data() {
        return {
        }
    },
    methods: {
        
    }
}
</script>