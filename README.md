# code
repo
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Favorite Monument</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
body{
    font-family:  'Roboto', sans-serif;
    background-color: black;
    color: white;
    margin: 0;
    font-size: 17px;
    
}
a{
    color: white;
    text-decoration: none;
}
header{
    max-width: 80%;
    height: 50px;
    align-items: center;
    width: 1140px;
    margin: auto;
    display: flex;
    position: relative;
    z-index: 100;
}
header a{
    margin-right: 40px; 
}
.container {
    width: 100vw;
    height: 100vh;
    overflow: hidden;
    margin-top: -50px;
    position: relative;
}
.container .list .item {
   position: absolute;
   top: 0;
   left: 0;
   bottom: 0;
   right: 0;
   
}
.container .list .item img {
   width: 100%;
   object-fit: cover;
   height: 100%;
 }
 
 .container .list .item .content {
    max-width: 80%;
    position: absolute;
    top: 20%;
    left: 50%;
    transform: translateX(-50%);
    color: white;
    padding-right: 30%;
    box-sizing: border-box;
    text-shadow: 0 5px 10px #0004;
    width: 1140px;
  }
  .container .list .item .content .title {
        font-weight: bold;
        letter-spacing: 10px;
  }
  .container .list .item .content .title,
  .container .list .item .content .topic {
    font-weight: bold;
    font-size: 5em;
    list-style: 1.3em;
}
.container .list .item .content .topic {
    color: #221f1e;
    font-size: 2em;
}
.container .list .item .content .buttons {
    display: grid;
    grid-template-columns: repeat(2, 130px);
    grid-template-rows: 40px;
    gap: 5px;
    margin-top: 20px;
}
.container .list .item .content .buttons button {
    border: none;
    background-color: #eee;
    letter-spacing: 3px;
    font-weight: 500;
    font-family: 'Roboto', sans-serif;
}

.container .list .item .content button:nth-child(2) {
   border: 1px solid white;
   color: white;
   background-color: transparent;
}
.thumbnail {
    position: absolute;
    bottom: 50px;
    left: 50%;
    width: max-content;
    z-index: 100; 
    display: flex;
    gap: 20px;
}
.thumbnail .item {
    position: relative;
    width: 150px;
    height: 220px;
    flex-shrink: 0;
}

.thumbnail .item img{
    border-radius: 20px;
    width: 100%;
    height: 100%;
    object-fit: cover;
}
.thumbnail .item .content{
    position: absolute;
    left: 10px;
    bottom: 10px;
    right: 10px;
}  

.thumbnail .item .content .title{
    font-weight: bold;
}
.arrows {
    width: 300px;
    display: flex;
    max-width: 30%;
    top: 80%;
    right: 52%;
    position: absolute;
    gap: 10px;
    align-items: center;
    
}
.arrows button{
    width: 40px;
    border-radius: 50%;
    border: none;
    height: 40px;
    background-color: #eee4;
    color: white;
    font-family: monospace;
    transition: .5s;
    font-weight: bold;
    z-index: 100;
    font-size: large;
}
.arrows button:hover{
    background-color: #eee;
    color: #555; 
} 
.container .list .item:nth-child(1){
    z-index: 1;
}
.container .list .item:nth-child(1) .title,
.container .list .item:nth-child(1) .topic,
.container .list .item:nth-child(1) .des,
.container .list .item:nth-child(1) .buttons {
    transform: translateY(50px);
    filter: blur(20px) ;
    opacity: 0;
    animation: showContent 0.5s 1s linear 1 forwards;
}
@keyframes showContent{
    to{
        opacity: 1;
        filter: blur(0);
        transform: translateY(0);
    }
}
.container .list .item:nth-child(1) .title{
    animation-delay: 1.2s;
}
.container .list .item:nth-child(1) .topic{
    animation-delay: 1.4s;
}
.container .list .item:nth-child(1) .des{
    animation-delay: 1.6s;
}
.container .list .item:nth-child(1) .buttons{
    animation-delay: 1.8s;
}
.container .next .list .item:nth-child(1) img{
    position: absolute;
    left: 50%;
    width: 150px;
    height: 220px;
    bottom: 50px;
    border-radius: 20px;
    animation: showImage 0.5s linear 1 forwards;
}
@keyframes showImage{
    to{
        width: 100%;
        height: 100%;
        bottom: 0;
        left: 0;
        border-radius: 0;
    }
}
.carousel.next .thumbnail .item:nth-last-child(1){
    width: 0;
    overflow: hidden;
    animation: showThumbnail .5s linear 1 forwards;
}
@keyframes showThumbnail{
    to{
        width: 150px;
        
    }
}
.container.next .thumbnail{
    transform: translateX(150px);
    animation: transformThumbnail .5s linear 1 forwards;
}
@keyframes transformThumbnail{
    to{
        transform: translateX(0);
    }
}
.container.prev .list .item:nth-child(2){
    z-index: 2;
}
.container.prev .list .item:nth-child(2) img{
    left: 0;
    bottom: 0;
    position: absolute;;
    animation: outImage 0.5s linear 1 forwards;
}
@keyframes outImage{
    to{
        left: 50%;
        height: 220px;
        border-radius: 20px;
        bottom: 50px;
        width: 150px;
    }
}
.container.prev .thumbnail .item:nth-child(1){
    overflow: hidden;
    opacity: 0;
    width: 0;
    animation: showThumbnail 0.5s linear 1 forwards;
}

.container.prev .list .item:nth-child(2) .title ,
.container.prev .list .item:nth-child(2) .topic,
.container.prev .list .item:nth-child(2) .des,
.container.prev .list .item:nth-child(2) .buttons{
    animation: contentOut 1.5s linear 1 forwards;
}
@keyframes contentOut{
    to{
        transform: translateY(-150px);
        filter: blur(20px);
        opacity: 0;
    }
}
.container.next .arrows button,
.container.prev .arrows button{
    pointer-events: none;
}
.time{
    top: 0;
    left: 0;
    z-index: 100;
    position: absolute;
    background-color: #221f1e;
    height: 5px;
    width: 0%;
}
.container.next .time,
.container.prev .time{
    background-color: #555;
    width: 100%;
    animation: timeRunning 2s linear 1 forwards;
}
@keyframes timeRunning{
    to{
       width: 0;
    }
}
@media screen and (max-width: 678px) {
    .container .list .item .content{
        padding-right: 0;
    }
    
}
.container .list .item .content .title{
    font-size: 30px;
}
    </style>
</head>
<body>
    <header>
        <nav>
            <a href="#">Home</a>
            <a href="#">Contact</a>
            <a href="#">Info</a>
            <a href="#">PlanYourVist</a>
            <a href="#">History</a>
            <a href="#">Learning</a>
        </nav>
    </header>

    <div class="container">
        <div class="list">
            <div class="item">
                <img src="https://img.freepik.com/premium-photo/agra-taj-mahal-side-view-front-view-photography_862994-41388.jpg" alt="">
                <div class="content">
                    <div class="title">The Majestic Taj Mahal</div>
                    <div class="topic"> Marble</div>
                    <div class="des">
                        Discover the enchanting tale behind the creation of the iconic Taj Mahal and why it continues to captivate hearts worldwide 
                        Commissioned by the Mughal emperor Shah Jahan in the 17th century, the Taj Mahal is more than just a structure;it is a poignant expression of love. 
                        The narrative begins with the deep and enduring affection between Shah Jahan and his beloved wife Mumtaz Mahal. 
                        As the story unfolds, the Taj Mahal emerges as a grand testament to the emperor's grief and devotion following Mumtaz Mahal's untimely death during childbirt.

                    </div>
                    <div class="buttons">
                        <button>See More</button>
                        <button>Buy Ticket</button>
                    </div>
                </div>
            </div>
        

            <div class="item">
                <img src="https://img.freepik.com/premium-photo/agra-taj-mahal-side-view-front-view-photography_862994-41373.jpg" alt="">
                <div class="content">
                    <div class="title"> Celebrating Heritage</div>
                    <div class="topic"> Legacy</div>
                    <div class="des">
                         is an ode to the rich tapestry of our collective legacy, a journey that takes us through the corridors of time to explore,
                         appreciate, and preserve the cultural heritage that defines us. This topic unfolds as a celebration of the diverse facets of heritage, 
                         emphasizing the importance of safeguarding the treasures that connect us to our roots.Our world is a mosaic of cultures, 
                         each with its unique traditions, architectural marvels, and stories passed down through generations. 
                         "Celebrating Heritage" aims to spotlight this diversity, recognizing the myriad ways in which people across the globe have
                          shaped their heritage. From ancient monuments to living traditions, the celebration encompasses the wealth of our shared
                           human experience.
                    </div>
                    <div class="buttons">
                        <button>Explore</button>
                        <button>Learn More</button>
                    </div>
                </div>
            </div>

            <div class="item">
                <img src="https://img.freepik.com/premium-photo/agra-taj-mahal-side-view-front-view-photography_862994-51553.jpg" alt="">
                <div class="content">
                    <div class="title"> The Hidden Gem</div>
                    <div class="topic">MonuVoyage</div>
                    <div class="des">
                        Embark on a unique adventure with MonuVoyage as we invite you to uncover a hidden gem, a lesser-known monument 
                        that bears the weight of centuries and boasts a rich tapestry of history and cultural significance. 
                        Join us as we delve into the secrets of this architectural marvel, offering an immersive experience that goes beyond the ordinary 
                        and uncovers the stories that time has forgotten.MonuVoyage takes you off the beaten path, away from the bustling crowds and well-trodden 
                        tourist trails, to explore a hidden gem that has long awaited its moment in the spotlight. 
                        As you step into the shadow of this lesser-known monument, a world of history, mystery, and cultural richness unfolds before your eyes.
                    </div>
                    <div class="buttons">
                        <button>Explore</button>
                        <button>Learn More</button>
                    </div>
                </div>
            </div>

            <div class="item">
                <img src="https://th.bing.com/th/id/OIP.CWFI0ZSD6Ow5Tylwgrvu-AHaE6?rs=1&pid=ImgDetMain" alt="">
                <div class="content">
                    <div class="title">Architectural Marvel</div>
                    <div class="topic">Timeless </div>
                    <div class="des">
                        Prepare to be captivated as we embark on a journey to uncover the hidden depths of an architectural marvel that transcends time. 
                        In this exploration, we peel back the layers of history to reveal the beauty and innovation woven into the very fabric of a structure 
                        that stands as a testament to human ingenuity. Join us in discovering the enduring allure of this timeless masterpiece.This architectural marvel
                        stands as a silent witness to the ebb and flow of history, a structure that has weathered the passage of time with grace and resilience.As we peel back
                        the layers, we reveal not only the physical beauty of the monument but also the stories and narratives that  have unfolded within its walls.

                    </div>
                    <div class="buttons">
                        <button>Discover</button>
                        <button>Visit</button>
                    </div>
                </div>
            </div>
        
        </div>
    </div>
    
    <div class="thumbnail">
        <div class="item">
            <img src="https://img.freepik.com/premium-photo/agra-taj-mahal-side-view-front-view-photography_862994-41388.jpg" alt="">
            <div class="content">
                <div class="title">Marble</div>
                
            </div>
        </div>
    
        <div class="item">
            <img src="https://img.freepik.com/premium-photo/agra-taj-mahal-side-view-front-view-photography_862994-41373.jpg" alt="">
            <div class="content">
                <div class="title">Legacy</div>
            </div>
        </div>

        <div class="item">
            <img src="https://img.freepik.com/premium-photo/agra-taj-mahal-side-view-front-view-photography_862994-51553.jpg" alt="">
            <div class="content">
                <div class="title">MonuVoyage</div>
            </div>
        </div>
    
        <div class="item">
            <img src="https://th.bing.com/th/id/OIP.CWFI0ZSD6Ow5Tylwgrvu-AHaE6?rs=1&pid=ImgDetMain" alt="monument">
            <div class="content">
                <div class="title">Timeless</div>
            </div>
        </div>
    </div> 
    
    <div class="arrows">
        <button id="prev" onclick="showSlider('prev')"><</button>
        <button id="next" onclick="showSlider('next')">></button>
    </div>

    <div class="time"></div>

    <script>
          document.addEventListener('DOMContentLoaded', function () {
    let nextDom = document.getElementById('next');
    let prevDom = document.getElementById('prev');
    let containerDom = document.querySelector('.container');
    let listItemDom = document.querySelector('.container .list');
    let thumbnailDom = document.querySelector('.container .thumbnail');
    let runTimeOut
    let timeRunning
    nextDom.onclick = function () {
        showSlider('next');
    }
    prevDom.onclick = function () {
        showSlider('prev');
    }
    
    let timeAutoNext = 7000;
    let runAutoRun = setTimeout(() => {
        nextDom.click();
    }, timeAutoNext);

    function showSlider(type) {
        let itemSlider = document.querySelectorAll('.container .list .item');
        let itemThumbnail = document.querySelectorAll('.container .thumbnail .item');

        if (type === 'next') {
            listItemDom.appendChild(itemSlider[0]);
            thumbnailDom.appendChild(itemThumbnail[0]);
            containerDom.classList.add('next');
        } else {
            let positionLastItem = itemSlider.length - 1;
            listItemDom.prepend(itemSlider[positionLastItem]);
            thumbnailDom.prepend(itemThumbnail[positionLastItem]);
            containerDom.classList.add('prev');
        }

        clearTimeout(runTimeOut);
        runTimeOut = setTimeout(() => {
            containerDom.classList.remove('next');
            containerDom.classList.remove('prev');
        }, timeRunning);

        clearTimeout(runAutoRun);
        runAutoRun = setTimeout(() => {
            nextDom.click();
        }, timeAutoNext);
    }
});
    
    </script>
</body>
</html>
