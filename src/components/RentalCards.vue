<template>
    <div class="card">
        <div class="card__image">
            <img :src=image :alt=title>
        </div> <!-- Image container end -->
        <div class="card__details">
            <h2 class="card__details__title">{{ title }}</h2>
            <ul class="card__details__list">
                <li class="card__details__list--item"> <img class="card__details__list--persons" src="./../assets/icons/persons.svg" alt="persons icon"> {{ persons }}</li>
                <li class="card__details__list--item"> <img class="card__details__list--doors" src="./../assets/icons/doors.svg" alt="persons icon"> {{ doors }}</li>
                <li class="card__details__list--item"> <img class="card__details__list--liters" src="./../assets/icons/liters.svg" alt="persons icon"> {{ liters }} l/100km</li>
            </ul>
            <h3 class="card__details__description-title">
                Description
            </h3>
            <p class="card__details__description-text">{{ description }}</p>
        </div> <!-- Info container end -->
        <div class="card__book">
            <span class="card__book__price">${{ price }}</span>
            <button class="card__book__button">Book Now</button>
            <button class="card__delete__button">Delete car</button>
        </div> <!-- Price end -->
    </div><!-- Card end -->
</template>

<script>
export default {
  name: 'RentalCards',
  props: {
    title: String,
    price: Number,
    image: String,
    persons: Number,
    doors: Number,
    liters: Number,
    description: String
  }
}
</script>

<style scoped>

.card {
    width: 100%;
    height: auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 0 0 var(--spacing-medium) 0;
    background-color: white;
}
.card__delete__button {
    margin-top: 5px;
    border: none;
    background: none;
    cursor: pointer;
    color: var(--grey-medium);
    padding: var(--spacing-small);
    font-size: var(--text-small)
}
.card__delete__button:hover {
    color: red;
}
.card__details {
    margin: 0 var(--spacing-medium) 0 var(--spacing-medium);
}
.card__details__list {
    /* spacing between the header, list and description is made here*/
    padding: var(--spacing-medium) 0 var(--spacing-medium) 0;
}
.card__details__list--item {
    display: inline;
    border: 1px solid var(--grey-medium);
    border-radius: var(--border-radius);
    padding: 0 var(--spacing-small) 0 var(--spacing-small);
}
.card__details__list--persons {
    width: 11px;
    height: auto;
}
.card__details__list--doors {
    width: 15px;
    height: auto;
}
.card__details__list--liters {
    width: 13px;
    height: auto;
}
.card__book {
    /* this is also a flex container so that price is always forced to be displayed above button */
    display: flex;
    flex-direction: column;
    align-self: flex-end;
    padding: var(--spacing-small) var(--spacing-medium) var(--spacing-small) var(--spacing-medium);
    /* border: 1px solid red; */
}
.card__book::before {
    /* Adds the grey line between details and booking containers. It's a bit rough and little versatile */
        content: "";
        position: relative;
        background-color: var(--grey-light);
        width: 2px;
        height: 160px;
        top: 155px;
        left: -25px;
}
.card__details__title {
    font-size: var(--text-large);
    font-weight: var(--weight-heavy);
}
.card__book__button {
    padding: var(--spacing-medium);
    background-color: var(--blue-dark);
    border: 2px solid var(--blue-dark);
    color: var(--grey-light);
    border-radius: var(--border-radius);
    font-size: var(--text-medium)
}
.card__book__button:hover {
    background-color: var(--blue-medium);
}
.card__details__description-title {
    font-weight: var(--weight-heavy);
    margin-bottom: var(--spacing-small)
}
.card__details__description-text {
    color: var(--grey-medium);
}
.card__book__price {
    font-size: var(--text-huge);
    color: var(--green-medium);
    font-weight: var(--weight-heavy);
}
</style>
