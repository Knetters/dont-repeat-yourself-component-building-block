<script>

</script>

<ul class="filter-item-list" id="filterList">
    <li class="active">Alles</li>
    <li>Klimaatadaptatie</li>
    <li>Waterkwaliteit</li>
    <li>B-RAIN</li>
</ul>

<style>
    .filter-item-list {
        list-style: none;
        padding: 0;
        display: flex;
        margin: .35rem 0rem 1rem 0rem;
        color: #2B3F5A;
        width: 50%;
    }

    .filter-item-list li {
        margin-right: 1.5rem;
        padding: .2rem .6rem;
        border-radius: .5rem;
        cursor: pointer;
        font-size: .8rem;
        -webkit-user-select: none; /* Safari */
        -ms-user-select: none; /* IE 10 and IE 11 */
        user-select: none; /* Standard syntax */
        transition: .2s;
    }

    .filter-item-list li:hover {
        background-color: #4ECD5D;
        color: #FFFFFF;
        box-shadow: rgba(0, 0, 0, 0.14) 0px 3px 8px;
    }

    .active {
        background-color: #4ECD5D;
        color: #FFFFFF;
        border-radius: .5rem;
        box-shadow: rgba(0, 0, 0, 0.14) 0px 3px 8px;
    }

    @media only screen and (max-width: 800px) {
        .filter-item-list {
            width: 100%;
        }
    }
</style>