<template>
    <form v-on:submit.prevent class="modal">
        <div class="modal__content">
            <div class="modal__content__header">
                <h3>Add new car</h3>
            </div><!-- Modal header end -->
            <div class="modal__content__body">
                <label>Title *</label>
                <input v-model="formData.title" type="text" name="title" placeholder="Title">
                <label>Price *</label>
                <input v-model="formData.price" type="text" name="Price" placeholder="Price">
                <label>Image URL *</label>
                <input v-model="formData.imageUrl" type="text" name="Image URL" placeholder="Image URL">
                <div class="modal__content__body-group">
                    <div class="">
                        <label>Persons *</label>
                        <input v-model="formData.persons" type="text" name="Persons" placeholder="Persons">
                    </div>
                    <div class="">
                        <label>Doors *</label>
                        <input v-model="formData.doors" type="text" name="Doors" placeholder="Doors">
                    </div>
                    <div class="">
                        <label>Litres per 100km *</label>
                        <input v-model="formData.litres" type="text" name="Litres per 100km" placeholder="Litres per 100km">
                    </div>
                </div>
                <label>Description *</label>
                <textarea v-model="formData.description" rows="4" cols="50" placeholder="Description"></textarea>
            </div><!-- Modal body end-->
            <div class="modal__content__footer">
                <button class="modal__button modal__button--white">Cancel</button>
                <button @click="submitForm" class="modal__button modal__button--blue">Submit</button>
            </div><!-- Modal footer -->
        </div><!-- Modal content end -->
    </form><!-- Modal end -->
</template>

<script>
export default {
  name: 'NewCarModal',
  data: function () {
    return {
      formData: {
        title: '',
        price: '',
        imageUrl: '',
        persons: '',
        doors: '',
        litres: '',
        description: ''
      }
    }
  },
  methods: {
    submitForm (event) {
      this.$emit('addNewCar', this.formData)
    }
  }
}
</script>

<style scoped>
.modal {
    position: fixed;
    z-index: 1;
    padding-top: 250px; /*Distance from the top of the viewport*/
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0,0.6); /* black opactiy background */
}
.modal__content {
    position: relative;
    background-color: white;
    margin: auto;
    border: 1px solid var(--grey-light);
    width: 40%;
    box-shadow: 0 10px 50px 0 rgba(0,0,0,0.2);
    border-radius: var(--border-radius);
}
.modal__content__header {
    border-bottom: 1px solid var(--grey-medium);
    font-size: var(--text-medium);
    padding: var(--spacing-medium);
}
.modal__content__body {
    display: flex;
    flex-direction: column;
    padding: var(--spacing-medium);
}
.modal__content__body input, textarea {
    padding: var(--spacing-small);
    margin: var(--spacing-small) 0 var(--spacing-medium) 0; /*distance between input fields, textarea and labels*/
    border-radius: var(--border-radius);
    border: 1px solid var(--grey-medium);
}
.modal__content__body-group {
    display: flex;
    flex-direction: row;
    width: 100%;
}
.modal__content__body-group div:nth-child(2) {
    padding: 0 var(--spacing-medium); /* Adds space to the second child of the modal body group*/
}
.modal__content__body-group div input {
    width: 100%; /* fixes the inputs going outside the modal*/
}
.modal__content__footer {
    display: flex;
    margin: 0 var(--spacing-medium) var(--spacing-medium);
    justify-content: space-between;
}
.modal__button {
    padding: var(--spacing-small) var(--spacing-medium);
    border: 2px solid var(--blue-dark);
    border-radius: var(--border-radius);
    font-size: var(--text-medium)
}
.modal__button--blue {
    color: var(--grey-light);
    background-color: var(--blue-dark);
}
.modal__button--blue:hover, .modal__button--white:hover {
    background-color: var(--blue-medium);
    color: white;
    cursor: pointer;
}
.modal__button--white {
    color: var(--blue-dark);
    background-color: white;
}
</style>
