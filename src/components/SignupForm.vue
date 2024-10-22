<template>
  <form>
    <label>Email:</label>
    <input type="email" required v-model="email">

    <label>Password:</label>
    <input type="password" required v-model="password">

    <label>Role: </label>
    <select v-model="role">
        <option value="developer">Web Developer</option>
        <option value="designer">Web Designer</option>
    </select>

    <label>Skills: </label>
    <input type="text" v-model="tempSkill" @keyup.alt="addSkill">
    <div v-for="skill in skills" :key="skill" class="pill">
        <span @click="deleteSkill(skill)">{{ skill }}</span>

    </div>

    <div class="terms">
        <input type="checkbox" v-model="terms" required>
        <label>Accept terms and coditions</label>
    </div>


  </form>
  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
  <p>Role: {{ role }}</p>
  <p>Terms accepted: {{ terms }}</p>
 
</template>

<script>
// Challenge
// -When a user clicks on a skill, delete that skill
export default {
    data() {
        return {
            email: 'mario',
            password: '',
            role: 'designer',
            terms: false,
            tempSkill: '',
            skills: []

        }
    },
    methods: {
        addSkill(e) {
            if (e.key === ',' && this.tempSkill) {
                if (!this.skills.includes(this.tempSkill)) {
                    this.skills.push(this.tempSkill)
                }
                this.tempSkill = ''
            }
        },
        deleteSkill(skill) {
            this.skills = this.skills. filter((item) => {
                return skill !== item
            })
        }
    }
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
    input, select{
        display: block;
        padding: .625rem .375rem;
        width: 100%;
        box-sizing: border-box;
        border: none;
        border-bottom: .0625rem solid #ddd;
        color: #555;
    }
    input[type="checkbox"] {
        display: inline-block;
        width: 1rem;
        margin: 0 .625rem 0 0;
        position: relative;
        top: .125rem
    }
    .pill {
        display: inline-block;
        margin: 1.25rem .625rem 0 0;
        padding: .375rem .75rem;
        background: #eee;
        border-radius: 1.25rem;
        font-size: .75rem;
        letter-spacing: .0625rem;
        font-weight: bold;
        color: #777;
        cursor: pointer;
    }

</style>