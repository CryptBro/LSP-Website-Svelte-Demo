<!-- Two Column Row -->
<div class="wrapper2">
    <div class="two-column">
      <div class="left">
        <h2>Luxury Staging Pro</h2>
        <p>Unlock the potential of your listings with Virtual Staging + Digital Architecture from Luxury Staging Pro. 
          LSP produces high-end virtual staging; 2D and 3D floor plans and 3D architectural renders. 
          Each project is managed by an experienced and talented design team, 
          with the final results to perfectly match the sophistication and refinement 
          that your clients expect.</p>
          <b><p>Unlock the potential of your listings with Virtual Staging + Digital Architecture from Luxury Staging Pro. 
            LSP produces high-end virtual staging.sefsdfsdfsdfsdf</p></b>
            <p>Unlock the potential of your listings with Virtual Staging + Digital Architecture from Luxury Staging Pro. 
                LSP produces high-end virtual staging; 2D and 3D floor plans and 3D architectural renders. 
                Each project is managed by an experienced and talented design team, 
                with the final results to perfectly match the sophistication and refinement 
                that your clients expect.</p>
                <b><p>Unlock the potential of your listings with Virtual Staging + Digital Architecture from Luxury Staging Pro. 
                  LSP produces high-end virtual staging.sefsdfsdfsdfsdf</p></b>
         
      </div>
      <div class="right">
        <div class="container">
            <div class="row">
              <!-- Order Form -->
              <form on:submit={submitForm}>
                <h3>Virtual Staging</h3>
                <p>Upload the image you'd like virtually staged in the boxes on the right. For each image, you can add virtual furniture removal or virtual renovation if those options are needed.</p>
                <p><b>Pro tip:</b> <i>Higher resolution images produce higher quality results.</i></p><hr>
          
                <!-- Image Upload Section -->
                <div class="image-upload">
                  <h4>Upload an Image ($40.00)</h4>
                  <input type="file" accept="image/*" on:change={handleImageUpload}>
                </div>
          
                <!-- Image Preview Section -->
                {#if uploadedImage}
                  <div id="image-preview" style="background-image: url({uploadedImage});"></div>
                {/if}
          
                <div class="form-section">
                  <h4>Color</h4>
                  <label for="color-select">Select Time Frame</label>
                  <select id="color-select" bind:value={dropdownValue}>
                    <option value="0">None</option>
                    <option value="20">24 Hours ($20)</option>
                    <option value="10">48 Hours ($10)</option>
                    <option value="5">Longer Than 48 Hours ($5)</option>
                  </select>
                </div>
          
                <div class="form-section">
                  <h4>Extra Options</h4>
                  {#each checkboxes.slice(0, 2) as checkbox}
                    <label>
                      <input type="checkbox" bind:checked={checkbox.checked}>
                      {checkbox.label}
                    </label>
                  {/each}
                </div>
          
                <div class="form-section">
                  <h4>Type Of Style</h4>
                  {#each checkboxes.slice(2) as checkbox}
                    <label>
                      <input type="checkbox" bind:checked={checkbox.checked}>
                      {checkbox.label}
                    </label>
                  {/each}
                </div>
          
                <!-- More Info Field -->
                <div class="form-section">
                  <h4>Room Name & More Info</h4>
                  <textarea bind:value={moreInfo} placeholder="Add a description (up to 200 words)" maxlength="200"></textarea>
                </div>
          
                <div>
                  <h4>Total: ${total.toFixed(2)}</h4>
                </div>
          
                <div class="button-container">
                  <button type="submit">Submit Order</button>
                  <button type="button" on:click={clearSelections}>Clear All</button>
                </div>
              </form>
            </div>
          </div>
          
      </div>
    </div>
  </div>

  
  
  
  
  
  
  
  <style>
   .wrapper2 {
    display: flex;
    justify-content: center; /* Center the two-column content horizontally */
    align-items: center;     /* Center vertically if needed */
    padding: 40px 10px;
   

}

.two-column {
  display: flex;
    flex-direction: row;
    justify-content: space-between; /* Space between the columns */
    max-width: 80%;              /* Limits the width of the content */
    width: 100%;                    /* Ensures it stretches inside the wrapper */

}


.left {
      flex: 1;                        /* Make both columns take equal space */
      margin: 0 10px;   
    }

    .right {
      flex: 1;                        /* Make both columns take equal space */
      margin: 0 10px;   
    }

/* Media query for screens smaller than 768px (typical mobile screen size) */
@media (max-width: 1200px) {
  .two-column {
    flex-direction: column; /* Stacks columns vertically */
  }

  header, footer {
    text-align: center;
  }
}

    .form-section {
      margin-bottom: 20px;
    }
  
    label {
      margin-right: 10px;
      color: #b0b0b0;
    }
  
    input[type="checkbox"], select {
      background-color: #333333;
      color: #ffffff;
      border: 1px solid #555555;
      padding: 5px;
      margin-left: 10px;
    }
  
    #total-display {
      font-size: 1.5rem;
      font-weight: bold;
      color: #00e676;
    }
  
    button {
      background-color: #00796b;
      color: #ffffff;
      padding: 10px 20px;
      border: none;
      cursor: pointer;
      font-size: 1rem;
    }
  
    button:hover {
      background-color: #004d40;
    }
  
    form {
      background-color: #1e1e1e;
      padding: 20px;
      border-radius: 8px;
    }
  
    .button-container {
      display: flex;
      gap: 10px;
    }
  
    #image-preview {
      width: 200px;
      height: 200px;
      background-size: contain;
      background-position: center;
      background-repeat: no-repeat;
      border: 1px solid #555;
      margin-top: 10px;
    }
  
    textarea {
      width: 100%;
      height: 100px;
      background-color: #333333;
      color: #e0e0e0;
      border: 1px solid #555555;
      padding: 10px;
      border-radius: 5px;
    }
  </style>
  
  <script>
    let total = 0;
    let imageUploaded = false;
    let dropdownValue = "0";
    let checkboxes = [
      { label: 'Virtual Furniture Removal (+ $15.00)', price: 15, checked: false },
      { label: 'Virtual Renovation (+ $15.00)', price: 15, checked: false },
      { label: 'Modern ($10)', price: 10, checked: false },
      { label: 'Classic ($15)', price: 15, checked: false },
      { label: 'Futuristic ($20)', price: 20, checked: false }
    ];
    let moreInfo = '';
    let uploadedImage = null;
  
    // Update total when dropdown or checkboxes change
    $: total = parseFloat(dropdownValue) + checkboxes.reduce((acc, checkbox) => {
      return checkbox.checked ? acc + checkbox.price : acc;
    }, 0) + (imageUploaded ? 40 : 0);
  
    // Handle image upload
    function handleImageUpload(event) {
      const file = event.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function(e) {
          uploadedImage = e.target.result;
        };
        reader.readAsDataURL(file);
        imageUploaded = true;
      }
    }
  
    // Clear all selections
    function clearSelections() {
      dropdownValue = "0";
      checkboxes = checkboxes.map(checkbox => ({ ...checkbox, checked: false }));
      imageUploaded = false;
    }
  
    // Handle form submission
    function submitForm(event) {
      event.preventDefault();
      const infoMessage = moreInfo ? `More Info: ${moreInfo}` : 'No additional info provided.';
      alert(`Order submitted. Total: $${total.toFixed(2)}\n${infoMessage}`);
    }


  import { fade } from 'svelte/transition';

  let showImage = true; // Controls the visibility of the image




  </script>
  