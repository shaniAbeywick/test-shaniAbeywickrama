<template>
    <div v-if="isVisible" class="modal-backdrop">
      <div class="modal">
        <div class="modal-header">
          <span class="warning-icon"><svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 256 256"><path fill="currentColor" d="M236.8 188.09L149.35 36.22a24.76 24.76 0 0 0-42.7 0L19.2 188.09a23.51 23.51 0 0 0 0 23.72A24.35 24.35 0 0 0 40.55 224h174.9a24.35 24.35 0 0 0 21.33-12.19a23.51 23.51 0 0 0 .02-23.72m-13.87 15.71a8.5 8.5 0 0 1-7.48 4.2H40.55a8.5 8.5 0 0 1-7.48-4.2a7.59 7.59 0 0 1 0-7.72l87.45-151.87a8.75 8.75 0 0 1 15 0l87.45 151.87a7.59 7.59 0 0 1-.04 7.72M120 144v-40a8 8 0 0 1 16 0v40a8 8 0 0 1-16 0m20 36a12 12 0 1 1-12-12a12 12 0 0 1 12 12"></path></svg></span>
          <div>
            <h2>Deactivate account</h2>
          <p>Are you sure you want to deactivate your account? All of your data will be permanently removed. This action cannot be undone.</p>
          </div>
          
        </div>
        
        <div class="modal-footer">
          <button @click="cancel" class="cancel-btn">Cancel</button>
          <button @click="deactivate" class="deactivate-btn">Deactivate</button>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    isVisible: Boolean,
  });
  
  const emit = defineEmits(['close', 'deactivate']);
  
  function cancel() {
    emit('close');
  }
  
  function deactivate() {
    emit('deactivate');
  }
  </script>
  
  <style scoped>
  .modal-backdrop {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .modal {
    background: white;
    
    border-radius: 8px;
    width: 500px;
    text-align: start;
  }
  
  .modal-header {
    display: flex;
    padding:20px 20px 0 20px;
    gap: 4px;
    margin-bottom: 16px;
  }
  
  .warning-icon {
    font-size: 24px;
    margin-right: 8px;
    color: #e63946; 
    background-color: #e59ea5;
    width: 40px;
    height: 30px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 2px;
   
  }
  
  h2 {
    font-size: 18px;
    font-weight: bold;
  }
  
  p {
    margin-bottom: 24px;
    color: #555;
    font-size: 14px;

  }
  
  .modal-footer {
    display: flex;
    justify-content: space-between;
    padding: 20px;
    background-color: #f0eeee;
    border-radius:0px 0px 8px 8px;
    
  }
  
  .cancel-btn {
    background-color: #f5f5f5;
    color: #000;
    border: 1px solid #ccc;
    padding: 10px 20px;
    border-radius: 4px;
  }
  
  .deactivate-btn {
    background-color: #e63946;
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 4px;
  }
  
  .cancel-btn:hover, .deactivate-btn:hover {
    opacity: 0.9;
  }
  </style>
  
  
  
  