<script>
    let homeAddress = '';
</script>

<div class="container">
    <div class="content">
        <h1>Get an O-Home Today!</h1>
        <p>Find affordable housing in Downtown LA. Starting at only $249,000.</p>
        <div class="input-section">
            <input 
                type="text" 
                placeholder="Enter Home Address" 
                bind:value={homeAddress}
            >
            <button class="btn">Get Started</button>
        </div>
    </div>
</div>

<style lang="scss">

    .container {
        background-color: #121212;
        color: #ffffff;
        display: flex;
        height: 100%;
        width: 100%;
        position: relative;
        top: 0;
        left: 0;
        overflow: hidden;
    }

    .content {
        width: 50%;
        padding: 4rem;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    h1 {
        color: #e0e0e0;
        font-size: 2.5rem;
        margin-bottom: 1rem;
    }

    p {
        color: #b0b0b0;
        margin-bottom: 2rem;
    }

    .input-section {
        display: flex;
        gap: 1rem;
    }

    input {
        flex-grow: 1;
        padding: 0.75rem;
        background-color: #1e1e1e;
        border: 1px solid #333;
        color: #ffffff;
    }

    .btn {
        background-color: #4CAF50;
        color: white;
        border: none;
        border-radius: 4px;
        padding: 0.75rem 1.5rem;
        cursor: pointer;
        transition: background-color 0.3s;

        &:hover {
            background-color: #45a049;
        }
    }
</style>