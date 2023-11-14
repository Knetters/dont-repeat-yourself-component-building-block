<script>
    import { onMount } from "svelte";

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
    <div class="filter-row">
        <ul class="filter-item-list" id="filterList">
            <li class="active">Alles</li>
            <li>Klimaatadaptatie</li>
            <li>Waterkwaliteit</li>
            <li>B-RAIN</li>
        </ul>
        <div class="search-container">
            <input class="searchbar" type="search" id="search" name="search" autocomplete="off" placeholder="Zoek een project"/>
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

    .filter-item-list {
        list-style: none;
        padding: 0;
        display: flex;
        margin: .3rem 0rem 1rem 0rem;
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

    .search-container {
        width: 50%;
    }

    .searchbar {
        width: 100%;
        padding: .5rem .6rem;
        border-radius: .5rem;
        border: none;
        box-shadow: rgba(0, 0, 0, 0.14) 0px 3px 8px;
    }

    .searchbar:focus {
        outline: none
    }

    .searchbar::placeholder {
        color: #B7B7B7;
    }

    @media only screen and (max-width: 800px) {
        .filter-row {
            flex-direction: column;
        }

        .filter-item-list {
            width: 100%;
        }

        .search-container {
            width: 100%;
        }
    }
</style>