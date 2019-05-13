<template>
  <section class="section">
    <div class="columns is-mobile">
        <div class="column is-8 is-offset-2">
            <p class="title is-2">Upload show</p>
             <b-field class="file">
                <b-upload v-model="file">
                    <a class="button is-primary">
                        <b-icon icon="upload"></b-icon>
                        <span>Click to uploaddd</span>
                    </a>
                </b-upload>
                <span class="file-name" v-if="file">
                    {{ file.name }}
                </span>
            </b-field>
        </div>
    </div>
  </section>
</template>

<script>

export default {
    name: 'HomePage',
    data() {
        return {
            file: null,
        }
    },
    mounted() {
        this.$axios.get('/.netlify/functions/hello/hello')
            .then( r => {
                console.log(r.data); 
            })
    }
}
</script>
