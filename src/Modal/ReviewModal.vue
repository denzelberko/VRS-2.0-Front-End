<template>
    <Modal>
      <ModalHeader>
        <h3>Add Review</h3>
      </ModalHeader>
      <ModalBody>

      <label for="rating">Give this trip a rating. 5 (best) - 1 (worst):</label>
      <select v-model="rating" id="rating">
        <option placeholder = "Give this trip a rating!" ></option>
        <option v-for = "rating in ratingChoices">{{rating}}</option>
      </select>
      <pre></pre>
      <textarea v-model= "message" rows="4" cols="40" class="textarea1" placeholder = "Enter your review!"></textarea> 
      
        
      </ModalBody>
      <ModalFooter>
       
        <button @click="close('Modal closed')" class="btn btn-danger">Cancel</button>
        <button @click="dismiss('Modal dismissed'); insertReview();" class="btn btn-primary">Add Review</button>
        
      </ModalFooter>
    </Modal>


  </template>
  
  <script>
  import Modal from './Modal.vue';
  import ModalHeader from './modalHeader.vue';
  import ModalFooter from './modalFooter.vue';
  import ModalBody from './modalBody.vue';
  import ModalMixin from './ModalMixin';
  import {EventBus} from '../main'
  export default {
    data() {
        return {
            ratingChoices: [1,2,3,4,5],
            tripId: '',
            message: '',
            rating: '',
          
            
            
           
        };
    },
    created(){

  

    },
    mounted(){


    },
    methods: {

      insertReview(){
       
        EventBus.$emit('sendMessage', this.message)
        EventBus.$emit('sendRating', this.rating);
        
        
      }

    },
    components: { Modal, ModalHeader, ModalBody, ModalFooter },
    mixins: [ModalMixin],
  }
  </script>

<style>

.textarea1 {
  resize: none;
}

</style>