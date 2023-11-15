<script>
</script>

<section>
    <ul id="filterMe">
        <li id="Klimaatadaptatie">Rood</li>
        <li id="Klimaatadaptatie">Blauw</li>
        <li id="Waterkwaliteit">Groen</li>
        <li id="Klimaatadaptatie">Geel</li>
        <li id="B-RAIN">Grijs</li>
        <li id="Klimaatadaptatie">Bruin</li>
        <li id="Waterkwaliteit">Paars</li>
    </ul>
</section>

<style>
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
        content: "Klimaatadaptatie";
        background-color: #ffffff;
        border: 1px solid #4ECD5D;
        border-radius: .5rem;
        margin-left: 1rem;
        padding: .2rem .5rem;
        font-size: .7rem;
    }

    #Waterkwaliteit:after {
        content: "Waterkwaliteit";
        background-color: #ffffff;
        border: 1px solid #4e72cd;
        border-radius: .5rem;
        margin-left: 1rem;
        padding: .2rem .5rem;
        font-size: .7rem;
    }

    #B-RAIN:after {
        content: "B-RAIN";
        background-color: #ffffff;
        border: 1px solid #cd614e;
        border-radius: .5rem;
        margin-left: 1rem;
        padding: .2rem .5rem;
        font-size: .7rem;
    }
</style>