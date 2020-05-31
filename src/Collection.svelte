<script>
    export let image;
    export let title;
    export let tags;
</script>

<style>
	.item {
        margin: 1rem;  
        width: 18rem;
        border-radius: 20px 20px 0 0;
	}

    #image {
        margin: 0 0 1rem 0;
        width: 18rem;
        height: auto;
        border-radius: 20px 20px 0 0;
    }

    #title {
        margin: 0 1rem 0 1.5rem;
        font-size: 1.1rem;
        color: #330033;
    }

    #tags {
        margin: .5rem 1rem 1rem 1.5rem;
        font-size: 1rem;
        color: #999999;
    }
</style>

<div class = "item">
	<img id = "image" src = { 'https://russia.rozarioflowers.ru/uploads/email/2020/06/' + image } loading="lazy" alt='no images'/>
    <h4 id = "title">{ title }</h4>
    <p id = "tags">{ tags.join(' • ') }</p>
</div>