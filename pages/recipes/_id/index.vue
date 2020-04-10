<template>
    <section class="single-recipe">
        <h1>{{ recipe.title }}</h1>
        <div>
            <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title"> 
        </div>
        <p>{{ recipe.descriptionText }}</p>
    </section>
</template>
<script>
export default {
     asyncData(context) {
        return new Promise ((resolve, reject) => {
            setTimeout(() => {
                resolve({
                        recipe: [
                        {
                            id: "1",
                            title: "Delicious Pizza",
                            previewText: "Awesome Pizza!",
                            descriptionText: "This is really delicious meal",
                            thumbnail: "https://www.bbcgoodfood.com/sites/default/files/recipe-collections/collection-image/2013/05/chorizo-mozarella-gnocchi-bake-cropped.jpg"
                        },
                        {
                            id: "2",
                            title: "Pasta",
                            previewText: "Awesome Pasta!",
                            descriptionText: "This is really delicious meal",
                            thumbnail: "https://drop.ndtv.com/albums/COOKS/pasta-vegetarian/pastaveg_640x480.jpg"
                        },
                    ].find(el => el.id === context.params.id)
                })
            }, 1500)
        })

    }
}
</script>

<style scoped>
.single-recipe{
    display:flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
}

.recipe-image{
    width: 100px;
    
}
</style>