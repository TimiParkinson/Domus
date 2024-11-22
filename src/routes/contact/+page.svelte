<script>
    // Add any logic or variables here if needed
  </script>
  
  <style lang="scss">
    :global(*) {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
  
    :global(body, html) {
      height: 100%;
      width: 100%;
      position: fixed;
      margin: 0;
      padding: 0;
      background-color: #121212;
      color: #ffffff;
    }
  
    .content-wrapper {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      padding: 2rem;
    }
  
    h1, h2 {
      color: #ffffff;
      margin-bottom: 0.5rem;
    }
  
    h1 {
      font-size: 2rem;
    }
  
    h2 {
      font-size: 1.5rem;
      font-weight: 300;
      color: #b0b0b0;
    }
  
    p {
      margin-bottom: 2rem;
      color: #b0b0b0;
      font-size: 1rem;
    }
  
    .container {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 1rem;
      margin-bottom: 1rem;
      width: 100%;
      max-width: 600px;
    }
  
    .form {
      flex: 1;
      display: flex;
      flex-direction: column;
      background-color: #1e1e1e;
      border-radius: 8px;
      padding: 1rem;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }
  
    .textarea {
      flex-grow: 1;
      margin-top: 0.5rem;
      background-color: #333;
      border: 1px solid #444;
      border-radius: 4px;
      padding: 0.5rem;
      color: #ffffff;
      font-size: 0.9rem;
  
      &:focus {
        outline: none;
        border-color: #4CAF50;
      }
    }
  
    #send {
      margin-top: 1rem;
      padding: 0.75rem;
      background-color: #4CAF50;
      color: #ffffff;
      text-align: center;
      font-weight: bold;
      border-radius: 4px;
      cursor: pointer;
      transition: background-color 0.3s ease;
  
      &:hover {
        background-color: #45a049;
      }
    }
  
    .floating-contact {
      position: fixed;
      bottom: 2rem;
      right: 2rem;
      display: flex;
      flex-direction: column;
      gap: 1rem;
  
      .contact {
        background-color: #1e1e1e;
        color: #b0b0b0;
        padding: 1rem;
        border-radius: 8px;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        font-size: 0.9rem;
  
        &:hover {
          background-color: #333;
          color: #ffffff;
        }
  
        strong {
          display: block;
          color: #ffffff;
          font-size: 1rem;
          margin-bottom: 0.5rem;
        }
      }
    }
  </style>
  
  <div class="content-wrapper">
    <h1>Got a Question?</h1>
    <h2>Contact Domus</h2>
    <p>We're here to help and answer any questions you might have. We look forward to hearing from you.</p>
  
    <div class="container">
      <div id="first" class="form">
        <h1>First Name</h1>
        <div class="textarea" contenteditable="true"></div>
      </div>
      <div id="last" class="form">
        <h1>Last Name</h1>
        <div class="textarea" contenteditable="true"></div>
      </div>
    </div>
    <div class="container">
      <div id="email" class="form">
        <h1>Email</h1>
        <div class="textarea" contenteditable="true"></div>
      </div>
    </div>
    <div class="container">
      <div id="message" class="form">
        <h1>Message</h1>
        <div class="textarea" contenteditable="true"></div>
      </div>
    </div>
    <div id="send">Send Message</div>
  </div>
  
  <div class="floating-contact">
    <div class="contact">
      <strong>Email</strong>
      info@davincischools.org
    </div>
    <div class="contact">
      <strong>Phone</strong>
      310-725-5800
    </div>
  </div>
  