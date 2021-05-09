<template>
    <div class="select">
        <label for="genre-select">Filter by genre:</label>
        <select
            name="genre"
            id="genre-select"
            v-model="selected"
            @change="$emit('changed', selected)"
        >
            <option value="all">All</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'Select',
    data() {
        return {
            selected: 'all',
        };
    },
};
</script>

<style scoped lang="scss">
.select {
    background-color: #1d2d3c;
    text-align: center;
    padding: 50px;
    color: #fff;
    label {
        margin-right: 20px;
    }
    select {
        background-color: #2e3a46;
        color: white;
        outline: none;
        padding: 5px 10px;
        border: 0;
        border-radius: 5px; // Adoro il border radius :D
    }
}
</style>
