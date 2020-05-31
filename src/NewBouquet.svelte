<script>
    export let image;
    export let title;
    export let price;
    export let recipe;

    let comment;
    let ru = '₽';
</script>

<style>
	.item {
        margin: 0 1em 1em 1em;  
        width: 38rem;
        border-radius: 20px 20px 0 0;
	}

    #image {
        margin: 0 1em 1em 1em;
        width: 16rem;
        height: auto;
        float: left;
        border-radius: 20px 20px 0 0;
    }

    #title {
        margin: 1rem 1rem 1rem 0;
        font-size: 1.3rem;
        color: #330033;
    }

    #recipe {
        margin: 0 1rem 1rem 0;
        font-size: 1rrem;
        color: #666666;
    }

    #price {
        margin: 1rem 1rem 1rem 0;
        font-size: 1.5rem;
        color: #330033; 
    }

    #button {
        margin: 0 .5rem 1rem 0;
        padding: .5rem 5rem;
        text-align: center;
        font-size: 1.2rem;
        color: #666666; 
        border-radius: 20px;
    }

    @media (max-width: 320px) {
        .item {
            width: 18rem;
        }

		#image {
            float: none;
        }

        #title {
            margin: 0 1em 0 1.5em;
        }

        #recipe {
            margin: 0 1rem 1rem 1.5em;
        }

        #price {
            margin: 1rem 1rem 1rem 1.5em;
        }

        #button {
            margin: 0 .5rem 1rem 1.5em;
        }
	}

</style>

<div class = "item">
	<img id = "image" src = { 'https://russia.rozarioflowers.ru/uploads/email/2020/05/22/' + image } loading="lazy" alt='no images'/>
    <h4 id = "title">{ title }</h4>
    <p id = "recipe">{ recipe }</p>
    <h4 id = "price">{ price }{ru}</h4>
     <button id = "button">Купить</button>
</div>