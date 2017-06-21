<template>
<section class="popup book-edit">
            <h1 v-if="book">Edit: {{book.title}}</h1>
            <h1 v-else>New Book</h1>
            <input type="text" v-model="bookToEdit.title" />
            <button @click="save">Save</button>
            <button @click="cancel">Cancel</button>
        </section>  
</template>

<<script>
export default {
  name: 'book-edit',
    created(){
        this.bookToEdit = Object.assign({}, this.book)
    },
    props: ['book'],
    data(){
        return {
            bookToEdit: null
        }
    },
    methods: {
        save() {
            console.log('Saving', this.bookToEdit)
            this.$emit('save', this.bookToEdit);
        },
        cancel() {
            console.log('Cancel')
        }
    }
}
</script>

