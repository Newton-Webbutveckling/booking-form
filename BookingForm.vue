<template>
<article class="booking-form">
    <h1>ÅKA TÅG</h1>
    <div class="from">
        <h2>
            STOCKHOLM
            <p class="time">10.30</p>
        </h2>
    </div>
    <div class="to">
        <p class="arrow">→</p>
        <h2>
            GÖTEBORG
            <p class="time">14.45</p>
        </h2>
    </div>
    <p>
        <input type="radio" name="klass" value="second" v-model="formData.klass">
        <label>2:a klass</label>
    </p>
    <p>
        <input type="radio" name="klass" value="first" v-model="formData.klass">
        <label>1:a klass</label>
    </p>
    <span class="num-tickets">
        <label>Antal biljetter</label>
        <select v-model="formData.numTickets">
            <option v-bind:value="1">1</option>
            <option v-bind:value="2">2</option>
            <option v-bind:value="3">3</option>
        </select>
    </span>
    <span class="title">
        <label>Titel</label>
        <select v-model="formData.title">
            <option value="ms">Ms.</option>
            <option value="mr">Mr.</option>
            <option value="empty">Ingen titel</option>
        </select>
    </span>
    <span class="first-name">
        <label>Förnamn</label>
        <input type="text" v-model="formData.firstName">
    </span>
    <span class="last-name">
        <label>Efternamn</label>
        <input type="text" v-model="formData.lastName">
    </span>
    <span class="terms">
        <input type="checkbox" v-model="formData.terms">
        <label>Godkänner villkoren</label>
    </span>
    <button>Boka biljetter</button>
</article>
</template>

<script>
export default {
    data(){ return {
        formData: {
            firstName: "",
            lastName: "",
            klass: "first",
            terms: false,
            numTickets: 1,
            title: "ms"
        }

    }}
}
</script>

<style scoped>
h1,h2,p{ margin:0; padding: 0; }

.booking-form{
    margin: auto;
    margin-top: 2.5rem;
    display: grid;
    grid-auto-rows: 4rem;
    max-width: 350px;
    font-family: Helvetica, sans-serif;
    grid-template-columns: 1fr 1fr;
    box-shadow: 0px 0px 7px 2px rgba(0,0,0,0.39);
    border-radius: 5px;
    padding-bottom: 0.5rem;
}

.booking-form > p{
    display: flex;
    align-items: center;
    padding: 1rem;
}

h1,.first-name,.last-name,.terms,button{
    grid-column: span 2;
}
h1{
    display: grid;
    place-items: center;
    background-color: lightgrey;
}

.to,.from{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: rgb(230,230,230);
    position: relative;
}

.to{
    background-color: #EEE;
}
.arrow{
    position: absolute;
    left: 0;
    transform: translateX(-50%);
}
.to h2, .from h2{
    position: relative;
    font-size: 1.25rem;

}
.time{
    position: absolute;
    align-self: flex-start;
    
    font-size: 0.70rem;
    font-weight: 200;
    color: #AAA;

}

span{
    display: flex;
    flex-direction: column;
    padding: 0.5rem;
}
.terms{
    flex-direction: row;
    align-items: center;
}

input[type="checkbox"],input[type="radio"]{
    width: 1.25rem;
    height: 1.25rem;
    filter: grayscale(1);
}
span > label{
    font-size: 0.75rem;
    color: #333;
    padding-left: 0.5rem;
    margin-left: -0.25rem;
}
input, select{
    padding: 0.75rem;
    margin: 0.25rem;
    border-radius: 5px;
    border: 1px solid black;
    outline: none;
}

button{
    background-color: black;
    color: white;
    font-weight: 800;
    font-size: 1rem;
    outline: 0;
    border: 0;
    margin: 0.5rem;

}
</style>