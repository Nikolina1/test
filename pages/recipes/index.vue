<template>
    <section class="recipes">
        <Recipe
            v-for="recipe in recipes"
            :key="recipe.id"
            :thumbnail="recipe.thumbnail"
            :title="recipe.title"
            :previewText="recipe.previewText"/>        
    </section>
</template>



<script>
import Recipe from '@/components/Recipe'
export default {
    components: {
        Recipe
    },
    asyncData() {
        return new Promise ((resolve, reject) => {
            setTimeout(() => {
                resolve({
                        recipes: [
                        {
                            id: "1",
                            title: "Delicious Pizza",
                            previewText: "Awesome Pizza!",
                            thumbnail: "https://www.bbcgoodfood.com/sites/default/files/recipe-collections/collection-image/2013/05/chorizo-mozarella-gnocchi-bake-cropped.jpg"
                        },
                        {
                            id: "2",
                            title: "Pasta",
                            previewText: "Awesome Pasta!",
                            thumbnail: "https://drop.ndtv.com/albums/COOKS/pasta-vegetarian/pastaveg_640x480.jpg"
                        },
                    ]
                })
            }, 1500)
        })

    }
    
};
</script>

<style scoped>
.recipes{
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
}
.recipe{
    box-sizing: border-box;
    width: 280px;
    padding: 8px;
    border: 1px solid #cccccc;
    box-shadow: 0 2px 2px #aaaaaa;
    margin: 10px;

}

.thumbnail{
    background-position: center;
    background-size: cover;
    width: 100%;
    height: 200px;
}
</style>