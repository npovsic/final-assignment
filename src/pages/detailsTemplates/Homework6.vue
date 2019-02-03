<template>
    <article>
        <div class="image-container">
            <div class="image-hover-trigger">
                <img class="hide-on-hover" :src="'./static/img/homework6/image.jpg'">
                <img class="show-on-hover" :src="'./static/img/homework6/image2.jpg'">
            </div>
        </div>
        
        <p>
            Z embalažo imamo veliko problemov. Narejena je za to, da pritegne kupca, to je pa to. To privede do zelo
            velike količine odpadne embalaže. Naša naloga je bila razviti tako embalažo, ki bi jo lahko uporabnik še 
            naprej uporabljal. Iskali smo drugi namen embalaže poleg osnovnega ("second life").
        </p>
        
        <p>
            Nakupi monitorjev ali televizorjev pustijo za sabo ogromno škatlo, ki je ne moremo več uporabiti. S tem problemom
            sem se srečal tudi na delovnem mestu, kjer nam te škatle zavzemajo preveč prostora, a si z njimi ne moremo pomagati.
            Da bi ta problem rešili, smo si zamislili škatlo, ki bi funkcionirala tudi kot predal, kot vidimo na interaktivni sliki.
        </p>
        
        <p>
            
        </p>
    </article>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
    .image-container {
        display: flex;
    }
    
    .image-hover-trigger {
        width: 50%;
        margin: 0 auto;
    }
    
    .image-hover-trigger > .hide-on-hover {
        display: block;
    }

    .image-hover-trigger > .show-on-hover {
        display: none;
    }

    .image-hover-trigger:hover > .hide-on-hover {
        display: none;
    }

    .image-hover-trigger:hover > .show-on-hover {
        display: block;
    }
</style>