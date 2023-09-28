<template>
    <div>
        <div class="Event">
            <div class="text m-3 w-100 overflow-auto">
                <h3>{{title}}</h3>
                <h5>{{description}}</h5>
                <h2>{{nextDates}}</h2>
            </div>
            <img class="backgroundImage" :src="src"/>
        </div>
    </div>
</template>

<script>
export default {
  name: "Event",
  emits: [],
  props: {
      src: String,
      title: String,
      description: String,
      nextDates: String,
  },
}
</script>

<style scoped>
.Event{
    position: relative;
    display: flex;
    height: 14rem;
}
.text{
    background-color: #FFFFFFBB;
    border: 2px solid black;
    border-radius: 10px;
    z-index: 1;
    align-self: center;
    padding: 8px;
    height: 90%;
    text-shadow: 0px 0px 8px white
}

.backgroundImage{
    position: absolute;
    border: black;
    border-radius: 20px;
    width: 100%;
    height: 100%;
    opacity: 0.5;
    z-index: 0;
}

</style>