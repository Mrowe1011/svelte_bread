<script>
    import { fly, fade } from 'svelte/transition';
    const images = [
        {title: 'oven', src: 'oven.jpg'},
        {title: 'bread', src: 'bread.jpg'},
        {title: 'shelf', src: 'shelf.jpg'}
    ]
    const text = [
        {header: 'Fresh made daily in a wood fired oven.', text:"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. "},
        {header: 'Sourdoughs made from organic flour.', text:"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. "},
        {header: 'Many varieties of breads made of all organic ingredients.', text:"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. "},
            ]
    let tick = 0
        setInterval(() => {
        tick += 1
        if (tick === images.length) {
            tick = 0
        }
    }, 10000)

    console.log(tick)
</script>
<div class="image" style="background: url({images[tick].src}) no-repeat  center"transition:fly="{{y: 200, duration: 500 }}"></div>
<div class="blurb">
    <h1>{text[tick].header}</h1>
    <br>
    <p>{text[tick].text}</p>
</div>
<div class="about">
    <section class="header">
        <h1 id="title">BRIMFIELD BREAD OVEN</h1>
        <h4 id='subtitle'>scratch made bread & pastry
            baked in a wood fired oven</h4>
    </section>

    <section class="text">
        <h1>Brimfield Bread Oven is a European style bakery in Brimfield Township, Ohio. Everything is made from scratch with simple ingredients, hand-shaped and baked in a wood-fired oven.</h1>
        <br>
        <p>The bakery began from a cottage foods bakery that we (Jud and Genevieve Smith) began in 2014 using a mobile wood fired oven at our home. After learning that Ohio does not allow cottage food bakeries to use wood fired ovens that are outdoors, we decided to get a permanent space to build a bigger oven and share our passion with our community. With determination, luck, the support of everyone who backed our Kickstarter and of course our family and friends, Brimfield Bread Oven officially opened its doors January 6, 2016. 

        </p>
    </section>
    
</div>


<style>
* {
    margin: 0;
}
#title {
    font-size: 4em;
    letter-spacing: 0.3em;

}
#subtitle {
    font-weight: lighter;
    font-size: 2em;
}
.text  {
    width: 60%;
    margin-left:20%;
    text-align: center;
}
.header {
    display: flex;
    align-items: center;
    flex-direction: column;
    margin-top: 3%;
    margin-bottom:5% ;
}
.about {
    position: absolute;
    top: 100%;

}
.blurb {
    z-index: 99;
    background-color: white;
    position: absolute;
    padding: 2%;
    width: 30%;
    top: 50%;
    left: 3%;
}
.image {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;}
</style>