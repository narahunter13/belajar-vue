<template>
    <div>
        <b-jumbotron>
            <template v-slot:header>{{ counter }}</template>

            <template v-slot:lead>Simple Counter</template>
        </b-jumbotron>
    </div>
</template>

<script>
export default {
    name: 'Countdown',
    props: {
        counter: Number
    }
}
</script>