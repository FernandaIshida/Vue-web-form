<template>
  <form>
    <label>Email:</label>
    <input type="email" required>
  </form>
</template>

<script>
export default {

}
</script>

<style>
    form {
        max-width: 26.25rem;
        margin: 1.875rem auto;
        background: white;
        text-align: left;
        padding: 2.5rem;
        border-radius: .625rem;
    }
    label {
        color: #aaa;
        display:inline-block;
        margin: 1.5625rem 0 0.9375rem;
        font-size: 0.6em;
        text-transform: uppercase;
        letter-spacing: .0625rem;
        font-weight: bold;
    }
    input {
        display: block;
        padding: .625rem .375rem;
        width: 100%;
        box-sizing: border-box;
        border: none;
        border-bottom: .0625rem solid #ddd;
        color: #555;
    }
</style>