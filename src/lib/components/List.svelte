<script>
</script>

<section>
    <div class="ul-container">
        <p>List met het id <span>filterMe</span>.</p>
        <ul id="filterMe">
            <li id="Klimaatadaptatie">Rood</li>
            <li id="Klimaatadaptatie">Blauw</li>
            <li id="Waterkwaliteit">Groen</li>
            <li id="Klimaatadaptatie">Geel</li>
            <li id="B-RAIN">Grijs</li>
            <li id="Klimaatadaptatie">Bruin</li>
            <li id="Waterkwaliteit">Paars</li>
            <li id="B-RAIN">Zwart</li>
        </ul>
    </div>
</section>

<style>
    * {
        font-family: 'Poppins', sans-serif;
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    .ul-container {
        width: 80%;
        margin-left: 10%;
        margin-top: 10rem;
        border: 2px solid #f1f1f1;
        padding: 1rem;
    }
    
    p {
        margin-bottom: .5rem;
    }

    ul {
        padding: 0;
        list-style-type: none;
    }

    li {
        padding: .5rem 1rem;
        background-color: rgb(239, 239, 239);
        margin-bottom: .5rem;
        border-radius: .5rem;
    }

    #Klimaatadaptatie:after {
        content: "klimaatadaptatie";
        background-color: #ffffff;
        border: 1px solid #4ECD5D;
        border-radius: .5rem;
        margin-left: 1rem;
        padding: .2rem .5rem;
        font-size: .7rem;
    }

    #Waterkwaliteit:after {
        content: "waterkwaliteit";
        background-color: #ffffff;
        border: 1px solid #4e72cd;
        border-radius: .5rem;
        margin-left: 1rem;
        padding: .2rem .5rem;
        font-size: .7rem;
    }

    #B-RAIN:after {
        content: "b-rain";
        background-color: #ffffff;
        border: 1px solid #cd614e;
        border-radius: .5rem;
        margin-left: 1rem;
        padding: .2rem .5rem;
        font-size: .7rem;
    }
</style>