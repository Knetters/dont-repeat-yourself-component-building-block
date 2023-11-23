<script>
    import { onMount } from "svelte";
    import FilterList from "../organism/FilterList.svelte";
    import Searchbar from "../atom/Searchbar.svelte";

    onMount(() => {
        
        const filterItems = document.getElementById('filterList').getElementsByTagName('li');
        const listItems = document.getElementById('filterMe').getElementsByTagName('li');

        for (let i = 0; i < filterItems.length; i++) {
            filterItems[i].addEventListener('click', function() {
                const filterId = this.textContent.trim();

                for (let j = 0; j < filterItems.length; j++) {
                    filterItems[j].classList.remove('active');
                }
                this.classList.add('active');

                if (filterId.toLowerCase() === 'alles') {
                    for (let j = 0; j < listItems.length; j++) {
                        listItems[j].style.display = 'block';
                    }
                } else {
                    for (let j = 0; j < listItems.length; j++) {
                        const listItem = listItems[j];
                        if (listItem.id === filterId) {
                            listItem.style.display = 'block';
                        } else {
                            listItem.style.display = 'none';
                        }
                    }
                }
            });
        }

        document.getElementById('search').addEventListener('input', function() {
            const searchValue = this.value.toLowerCase();
            let noResults = true;

            for (let i = 0; i < listItems.length; i++) {
                const currentItem = listItems[i].textContent.toLowerCase();
                if (currentItem.includes(searchValue)) {
                    listItems[i].style.display = 'block';
                    noResults = false;
                } else {
                    listItems[i].style.display = 'none';
                }
            }

            for (let j = 0; j < filterItems.length; j++) {
                filterItems[j].classList.remove('active');
            }
            filterItems[0].classList.add('active'); // Adding 'active' class to the first filter item

            const noResultItem = document.getElementById('noResult');
            if (noResults) {
                if (!noResultItem) {
                    const noResultLi = document.createElement('li');
                    noResultLi.textContent = 'Er zijn (nog) geen projecten met die naam.';
                    noResultLi.id = 'noResult';
                    document.getElementById('filterMe').appendChild(noResultLi);
                } else {
                    noResultItem.style.display = 'block';
                }
            } else {
                if (noResultItem) {
                    noResultItem.style.display = 'none';
                }
            }
        });

    });
</script>

<section>
    <noscript>
        <div class="no-js-message">
            Schakel JavaScript in om de filterfunctionaliteit te gebruiken.
        </div>
    </noscript>
    <div class="filter-row">
        <FilterList />
        <div class="search-container">
            <Searchbar />
        </div>
    </div>
</section>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;1,100;1,200;1,300;1,400;1,500;1,600&display=swap');

    * {
        font-family: 'Poppins', sans-serif;
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    /* Styling of filter options */
    .filter-row {
        height: max-content;
        width: 100%;
        display: flex;
        margin: 1rem 0rem;
    }

    .search-container {
        width: 50%;
    }

    .no-js-message {
        background-color: #eb3939;
        color: #FFFFFF;
        padding: .2rem .5rem;
        width: max-content;
        border-radius: .5rem;
        font-size: .8rem;
        margin-bottom: -1rem;
    }

    @media only screen and (max-width: 800px) {
        .filter-row {
            flex-direction: column;
        }

        .search-container {
            width: 100%;
        }
    }
</style>