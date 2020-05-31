<script>
    export let image;
    export let title;
    export let price;

    let comment;
    let min = 120;
    let ru = '₽';
    let star = '★';
    let rating = '4,5';
</script>

<style>
	.item {
        margin: 1rem;  
        width: 18rem;
        border-radius: 20px 20px 0 0;
	}

    #image {
        margin: 0 1rem 1rem 1rem;
        width: 16rem;
        height: auto;
        border-radius: 20px 20px 0 0;
    }

    #title {
        margin: 0 1rem 0 1.5rem;
        font-size: 1.1rem;
        color: #330033;
    }

    #comment {
        margin: 0 1rem 1rem 1.5rem;
        font-size: 1rem;
        color: #C4C4C4;
    }

    #min {
        font-size: 1rem;
        color: #330033;
    }

    #price {
        margin: 1rem 1rem 1rem 1.5rem;
        font-size: 1.5rem;
        color: #330033; 
        float: left;
    }

    #star {
        font-size: 1.5rem;
        color: #FFFF00; 
    }

    #rating {
        margin: 1rem;
        font-size: 1.5rem;
        color: #330033;
        float: right; 
    }

</style>

<div class = "item">
	<img id = "image" src = { 'https://russia.rozarioflowers.ru/uploads/email/2020/05/22/' + image } loading="lazy" alt='no images'/>
    <h4 id = "title">{ title }</h4>
    <h4 id = "comment">Доставим в течении <big id="min">{min}</big> минут</h4>
    <h4 id = "price">{ price }{ru}</h4>
    <h4 id = "rating"><big id="star">{star}</big>{ rating }</h4>
</div>