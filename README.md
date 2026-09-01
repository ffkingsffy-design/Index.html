<!DOCTYPE html>
<html lang="en">
<head>

<meta charset="UTF-8">
<meta name="viewport"
      content="width=device-width, initial-scale=1.0,
               maximum-scale=1.0, user-scalable=no">

<title>For You ♡</title>

<style>

@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600;700&family=Inter:wght@300;400;500&display=swap');


/* =========================================================
   RESET
========================================================= */

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    -webkit-tap-highlight-color:transparent;
}

:root{
    --bg:#050509;
    --bg2:#09070b;

    --pink:#e9a6b8;
    --pink2:#c4778e;
    --pink3:#f3cbd6;

    --paper:#fffaf3;
    --ink:#38292e;
    --muted:#777078;
}

html,
body{
    width:100%;
    height:100%;
    overflow:hidden;
}

body{
    background:var(--bg);
    color:white;
    font-family:Inter,sans-serif;
}


/* =========================================================
   BACKGROUND
========================================================= */

#background{
    position:fixed;
    inset:0;
    overflow:hidden;
    background:
        radial-gradient(
            circle at 50% 45%,
            rgba(220,100,140,.14),
            transparent 32%
        ),
        radial-gradient(
            circle at 10% 90%,
            rgba(120,70,150,.10),
            transparent 30%
        ),
        radial-gradient(
            circle at 90% 10%,
            rgba(220,130,160,.07),
            transparent 25%
        ),
        #050509;
}

#stars{
    position:absolute;
    inset:0;
    overflow:hidden;
}

.star{
    position:absolute;
    border-radius:50%;
    background:#fff;
    opacity:.5;
    animation:starFloat linear infinite;
}

@keyframes starFloat{

    0%{
        transform:translateY(110vh);
        opacity:0;
    }

    15%{
        opacity:.7;
    }

    80%{
        opacity:.5;
    }

    100%{
        transform:translateY(-10vh);
        opacity:0;
    }
}


/* =========================================================
   MOVING AURA
========================================================= */

.aura{
    position:absolute;
    width:500px;
    height:500px;
    border-radius:50%;

    background:
        radial-gradient(
            circle,
            rgba(233,166,184,.10),
            transparent 68%
        );

    animation:auraPulse 6s ease-in-out infinite;
    pointer-events:none;
}

@keyframes auraPulse{

    0%,100%{
        transform:scale(.8);
        opacity:.5;
    }

    50%{
        transform:scale(1.15);
        opacity:1;
    }
}


/* =========================================================
   MOUSE GLOW
========================================================= */

#mouseGlow{
    position:fixed;

    width:300px;
    height:300px;

    border-radius:50%;

    pointer-events:none;

    transform:translate(-50%,-50%);

    background:
        radial-gradient(
            circle,
            rgba(233,166,184,.08),
            transparent 68%
        );

    z-index:2;
}


/* =========================================================
   COMMON SCREEN
========================================================= */

.screen{
    position:fixed;
    inset:0;

    display:flex;
    align-items:center;
    justify-content:center;

    transition:
        opacity 1s ease,
        transform 1s ease,
        filter 1s ease;
}


/* =========================================================
   INTRO
========================================================= */

#intro{
    z-index:30;
}

.intro{
    position:relative;
    text-align:center;
    z-index:5;
}

.introAura{
    position:absolute;

    width:600px;
    height:600px;

    left:50%;
    top:50%;

    transform:translate(-50%,-50%);

    border-radius:50%;

    background:
        radial-gradient(
            circle,
            rgba(230,120,150,.11),
            transparent 65%
        );

    animation:introAura 5s ease-in-out infinite;

    z-index:-1;
}

@keyframes introAura{

    0%,100%{
        transform:translate(-50%,-50%) scale(.8);
    }

    50%{
        transform:translate(-50%,-50%) scale(1.12);
    }
}

.kicker{
    color:#777;

    font-size:9px;

    letter-spacing:7px;

    text-transform:uppercase;

    margin-bottom:28px;

    animation:fadeUp 1.2s ease;
}

.intro h1{

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:
        clamp(75px,11vw,145px);

    font-weight:400;

    line-height:.76;

    letter-spacing:-5px;

    animation:titleAppear 1.5s ease;
}

.intro h1 span{

    color:var(--pink);

    text-shadow:
        0 0 40px
        rgba(233,166,184,.25);
}

.intro p{

    margin-top:38px;

    color:#777;

    font-size:11px;

    letter-spacing:2px;

    animation:fadeUp 1.8s ease;
}

.begin{

    margin-top:42px;

    padding:16px 44px;

    border:
        1px solid
        rgba(233,166,184,.45);

    border-radius:50px;

    background:
        rgba(255,255,255,.025);

    color:#ddd;

    font-size:9px;

    letter-spacing:5px;

    cursor:pointer;

    transition:
        .4s ease;

    animation:fadeUp 2s ease;
}

.begin:hover{

    background:var(--pink);

    color:#1b1115;

    transform:translateY(-4px);

    box-shadow:
        0 0 45px
        rgba(233,166,184,.25);
}

.begin:active{
    transform:scale(.95);
}

.fadeOut{

    opacity:0!important;

    pointer-events:none!important;

    transform:
        scale(1.08)!important;

    filter:blur(15px);
}

@keyframes titleAppear{

    from{

        opacity:0;

        transform:
            translateY(45px);

        letter-spacing:15px;
    }

    to{

        opacity:1;

        transform:none;

        letter-spacing:-5px;
    }
}

@keyframes fadeUp{

    from{

        opacity:0;

        transform:
            translateY(20px);
    }

    to{

        opacity:1;

        transform:none;
    }
}


/* =========================================================
   ENVELOPE
========================================================= */

#envelopeScene{

    z-index:20;

    opacity:0;

    pointer-events:none;
}

#envelopeScene.show{

    opacity:1;

    pointer-events:auto;
}

.envelopeArea{
    text-align:center;
}

.caption{

    color:#666;

    font-size:9px;

    letter-spacing:6px;

    text-transform:uppercase;

    margin-bottom:55px;
}

.envelopeWrap{

    width:460px;

    height:310px;

    position:relative;

    perspective:1800px;

    cursor:pointer;

    transition:
        transform .5s ease;
}

.envelopeWrap:hover{

    transform:
        translateY(-7px);
}

.envelopeWrap:active{

    transform:
        scale(.97);
}

.envelope{

    position:absolute;

    bottom:0;

    width:100%;

    height:250px;

    background:
        linear-gradient(
            135deg,
            #e3a5b3,
            #bc7285
        );

    box-shadow:
        0 40px 80px
        rgba(0,0,0,.6);
}

.envelope:before{

    content:"";

    position:absolute;

    left:0;
    bottom:0;

    width:0;
    height:0;

    border-left:
        230px solid transparent;

    border-right:
        230px solid transparent;

    border-bottom:
        145px solid #b86e82;

    z-index:5;
}

.envelope:after{

    content:"";

    position:absolute;

    left:0;
    top:0;

    width:0;
    height:0;

    border-left:
        230px solid transparent;

    border-right:
        230px solid transparent;

    border-top:
        150px solid #efb8c4;

    z-index:4;
}

.flap{

    position:absolute;

    z-index:10;

    left:0;
    top:0;

    width:0;
    height:0;

    border-left:
        230px solid transparent;

    border-right:
        230px solid transparent;

    border-top:
        170px solid #f3bdc9;

    transform-origin:top center;

    transition:
        1.2s
        cubic-bezier(.2,.8,.2,1);
}

.letterPeek{

    position:absolute;

    z-index:7;

    width:380px;
    height:220px;

    left:40px;
    bottom:20px;

    background:
        var(--paper);

    color:var(--ink);

    display:flex;

    align-items:center;

    justify-content:center;

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:34px;

    box-shadow:
        0 15px 35px
        rgba(0,0,0,.35);

    transition:
        1.5s
        cubic-bezier(.2,.8,.2,1);
}

.seal{

    position:absolute;

    z-index:15;

    top:112px;
    left:50%;

    transform:
        translateX(-50%);

    width:68px;
    height:68px;

    border-radius:50%;

    background:
        radial-gradient(
            circle at 35% 25%,
            #d8879e,
            #8b4b60
        );

    display:flex;

    align-items:center;
    justify-content:center;

    font-size:28px;

    box-shadow:
        0 8px 25px
        rgba(0,0,0,.35);

    transition:.7s;
}

.envelopeWrap.open .flap{

    transform:
        rotateX(180deg);

    z-index:3;
}

.envelopeWrap.open .seal{

    opacity:0;

    transform:
        translateX(-50%)
        scale(.1)
        rotate(45deg);
}

.envelopeWrap.open .letterPeek{

    transform:
        translateY(-155px);
}

.tap{

    position:absolute;

    width:100%;

    bottom:-60px;

    color:#777;

    font-size:8px;

    letter-spacing:5px;

    animation:
        pulse 2s infinite;
}

@keyframes pulse{

    50%{
        opacity:.25;
    }
}


/* =========================================================
   LETTER BOOK
========================================================= */

#letterScene{

    z-index:40;

    opacity:0;

    pointer-events:none;

    transform:
        scale(.94);

    filter:blur(8px);
}

#letterScene.show{

    opacity:1;

    pointer-events:auto;

    transform:
        scale(1);

    filter:blur(0);
}

.book{

    width:min(1050px,88vw);

    height:min(650px,76vh);

    position:relative;

    perspective:2500px;
}

.paper{

    position:absolute;

    inset:0;

    overflow:hidden;

    color:var(--ink);

    background:

        radial-gradient(
            circle at 15% 15%,
            rgba(190,100,120,.08),
            transparent 30%
        ),

        radial-gradient(
            circle at 85% 85%,
            rgba(170,100,120,.06),
            transparent 30%
        ),

        var(--paper);

    box-shadow:
        0 45px 120px
        rgba(0,0,0,.75);
}

.paper:before{

    content:"";

    position:absolute;

    inset:18px;

    border:
        1px solid
        rgba(80,50,60,.12);

    pointer-events:none;
}


/* =========================================================
   PAGES
========================================================= */

.page{

    position:absolute;

    inset:0;

    padding:75px 100px;

    display:none;

    flex-direction:column;

    justify-content:center;

    z-index:2;
}

.page.active{

    display:flex;
}

.page.next{

    animation:
        pageNext .8s
        cubic-bezier(.2,.8,.2,1);
}

.page.prev{

    animation:
        pagePrev .8s
        cubic-bezier(.2,.8,.2,1);
}

@keyframes pageNext{

    from{

        opacity:0;

        transform:
            rotateY(-80deg)
            translateX(30px);

        transform-origin:left;
    }

    to{

        opacity:1;

        transform:
            rotateY(0)
            translateX(0);
    }
}

@keyframes pagePrev{

    from{

        opacity:0;

        transform:
            rotateY(80deg)
            translateX(-30px);

        transform-origin:right;
    }

    to{

        opacity:1;

        transform:
            rotateY(0)
            translateX(0);
    }
}


/* =========================================================
   PAGE CONTENT
========================================================= */

.number{

    position:absolute;

    top:35px;

    right:45px;

    color:#a78c92;

    font-size:9px;

    letter-spacing:3px;
}

.label{

    font-size:9px;

    letter-spacing:5px;

    text-transform:uppercase;

    color:#b17484;

    margin-bottom:18px;
}

.page h1{

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:68px;

    font-weight:500;

    line-height:.9;

    color:#54343f;

    margin-bottom:30px;
}

.page h2{

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:53px;

    font-weight:500;

    color:#54343f;

    margin-bottom:28px;
}

.page p{

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:23px;

    line-height:1.55;

    max-width:760px;

    margin-bottom:15px;

    color:#46363b;
}

.quote{

    border-left:
        2px solid
        #d398a8;

    padding-left:20px;

    color:#704655!important;

    font-style:italic;
}

.center{

    text-align:center;

    align-items:center;
}

.signature{

    font-family:
        "Cormorant Garamond",
        serif;

    color:#945469;

    font-size:27px;

    margin-top:25px;

    font-style:italic;
}


/* =========================================================
   TYPEWRITER
========================================================= */

.typeTarget{

    visibility:hidden;
}

.typeTarget.typing{

    visibility:visible;
}

.typeTarget.cursor:after{

    content:"";

    display:inline-block;

    width:2px;

    height:.8em;

    margin-left:4px;

    background:#b86d83;

    vertical-align:-.05em;

    animation:
        blink .7s infinite;
}

@keyframes blink{

    0%,45%{
        opacity:1;
    }

    46%,100%{
        opacity:0;
    }
}


/* =========================================================
   NAVIGATION
========================================================= */

.nav{

    position:absolute;

    left:0;
    right:0;

    bottom:-65px;

    display:flex;

    justify-content:space-between;

    align-items:center;

    z-index:20;
}

.nav button{

    border:0;

    background:none;

    color:#888;

    font-size:9px;

    letter-spacing:3px;

    cursor:pointer;

    padding:10px;

    transition:.3s;
}

.nav button:hover{

    color:white;

    transform:
        translateY(-2px);
}

.nav button:active{

    transform:
        scale(.9);
}

.middle{

    display:flex;

    align-items:center;

    gap:15px;
}

.pageCount{

    color:#666;

    font-size:8px;

    letter-spacing:2px;
}

.bar{

    width:180px;

    height:1px;

    background:#302b30;
}

.bar span{

    display:block;

    width:16.6%;

    height:1px;

    background:var(--pink);

    box-shadow:
        0 0 12px
        rgba(233,166,184,.5);

    transition:.7s;
}


/* =========================================================
   FINAL "THAT'S ALL"
========================================================= */

#final{

    z-index:60;

    display:none;

    text-align:center;

    background:

        radial-gradient(
            circle at center,
            rgba(210,80,120,.14),
            transparent 38%
        ),

        #050507;
}

#final.show{

    display:flex;

    animation:
        finalAppear 1.5s ease;
}

.final{

    position:relative;

    padding:40px;
}

.ring{

    position:absolute;

    width:280px;
    height:280px;

    left:50%;
    top:50%;

    transform:
        translate(-50%,-50%);

    border:
        1px solid
        rgba(233,166,184,.09);

    border-radius:50%;

    animation:
        ringPulse 4s
        infinite ease-in-out;
}

.ring2{

    position:absolute;

    width:190px;
    height:190px;

    left:50%;
    top:50%;

    transform:
        translate(-50%,-50%);

    border:
        1px solid
        rgba(233,166,184,.07);

    border-radius:50%;

    animation:
        ringPulse2 3s
        infinite ease-in-out;
}

@keyframes ringPulse{

    0%,100%{

        transform:
            translate(-50%,-50%)
            scale(.8);

        opacity:.2;
    }

    50%{

        transform:
            translate(-50%,-50%)
            scale(1.15);

        opacity:.8;
    }
}

@keyframes ringPulse2{

    0%,100%{

        transform:
            translate(-50%,-50%)
            scale(1.1);

        opacity:.2;
    }

    50%{

        transform:
            translate(-50%,-50%)
            scale(.8);

        opacity:.7;
    }
}

.finalHeart{

    font-size:100px;

    color:var(--pink);

    text-shadow:
        0 0 45px
        rgba(233,166,184,.3);

    animation:
        heartbeat 1.5s infinite;

    position:relative;
    z-index:3;
}

.final h1{

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:80px;

    font-weight:400;

    margin-top:20px;

    position:relative;
    z-index:3;
}

.finalLine{

    width:80px;

    height:1px;

    margin:28px auto;

    background:
        rgba(233,166,184,.55);

    position:relative;
    z-index:3;
}

.final p{

    color:#777;

    font-size:10px;

    letter-spacing:4px;

    position:relative;
    z-index:3;
}

@keyframes heartbeat{

    0%,100%{
        transform:scale(1);
    }

    15%{
        transform:scale(1.15);
    }

    30%{
        transform:scale(1);
    }
}

@keyframes finalAppear{

    from{

        opacity:0;

        transform:
            scale(.88);

        filter:blur(15px);
    }

    to{

        opacity:1;

        transform:
            scale(1);

        filter:blur(0);
    }
}


/* =========================================================
   LAST MESSAGE
========================================================= */

#last{

    position:fixed;

    inset:0;

    z-index:80;

    display:flex;

    align-items:center;

    justify-content:center;

    text-align:center;

    padding:30px;

    opacity:0;

    pointer-events:none;

    transform:
        scale(1.07);

    filter:blur(15px);

    background:

        radial-gradient(
            circle at center,
            rgba(210,80,120,.13),
            transparent 38%
        ),

        #050507;

    transition:

        opacity 1.8s ease,
        transform 1.8s ease,
        filter 1.8s ease;
}

#last.show{

    opacity:1;

    pointer-events:auto;

    transform:
        scale(1);

    filter:blur(0);
}

.lastBox{

    max-width:850px;

    position:relative;

    z-index:5;
}


/* =========================================================
   WAIT
========================================================= */

.wait{

    color:#777;

    font-size:9px;

    letter-spacing:7px;

    text-transform:uppercase;

    margin-bottom:30px;

    opacity:0;

    transform:
        translateY(15px);

    transition:1s;
}

#last.show .wait{

    opacity:1;

    transform:none;

    transition-delay:.5s;
}


/* =========================================================
   LAST TYPE
========================================================= */

#lastTyping{

    font-family:
        "Cormorant Garamond",
        serif;

    color:#f3dce3;

    font-size:
        clamp(42px,6vw,75px);

    line-height:1;

    min-height:80px;
}

.lastCursor:after{

    content:"";

    display:inline-block;

    width:2px;

    height:.8em;

    margin-left:5px;

    background:var(--pink);

    animation:
        blink .7s infinite;
}


/* =========================================================
   LAST LINE
========================================================= */

.lastLine{

    width:0;

    height:1px;

    background:
        rgba(233,166,184,.55);

    margin:35px auto;

    transition:
        width 1.2s ease;
}

#last.show .lastLine{

    width:90px;

    transition-delay:3s;
}


/* =========================================================
   LAST WORDS
========================================================= */

.lastWords{

    color:#aaa;

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:
        clamp(21px,3vw,31px);

    line-height:1.45;

    opacity:0;

    transform:
        translateY(25px);

    filter:blur(5px);

    transition:
        opacity 1.5s ease,
        transform 1.5s ease,
        filter 1.5s ease;
}

.lastWords.reveal{

    opacity:1;

    transform:none;

    filter:blur(0);
}

.lastWords .pink{

    color:var(--pink);

    font-style:italic;
}

.lastWords strong{

    color:#eee;

    font-weight:500;
}


/* =========================================================
   HEARTS
========================================================= */

#hearts{

    position:absolute;

    inset:0;

    overflow:hidden;

    pointer-events:none;
}

.heart{

    position:absolute;

    bottom:-30px;

    color:
        rgba(233,166,184,.4);

    animation:
        rise linear forwards;
}

@keyframes rise{

    from{

        transform:
            translateY(0)
            scale(.5)
            rotate(0deg);

        opacity:0;
    }

    15%{
        opacity:.6;
    }

    to{

        transform:
            translateY(-110vh)
            scale(1.2)
            rotate(30deg);

        opacity:0;
    }
}


/* =========================================================
   MOBILE
========================================================= */

@media(max-width:700px){

    #mouseGlow{
        display:none;
    }

    .introAura{
        width:400px;
        height:400px;
    }

    .intro h1{

        font-size:78px;

        letter-spacing:-3px;
    }

    .intro p{

        max-width:290px;

        line-height:1.6;

        margin-left:auto;
        margin-right:auto;
    }

    .begin{

        padding:
            15px 35px;
    }

    .envelopeWrap{

        transform:
            scale(.65);
    }

    .envelopeWrap:hover{

        transform:
            scale(.65);
    }

    .book{

        width:91vw;

        height:68vh;
    }

    .page{

        padding:
            50px 30px;
    }

    .page h1{

        font-size:48px;

        margin-bottom:22px;
    }

    .page h2{

        font-size:39px;

        margin-bottom:22px;
    }

    .page p{

        font-size:17px;

        line-height:1.43;

        margin-bottom:10px;
    }

    .label{

        font-size:7px;

        letter-spacing:4px;
    }

    .number{

        top:25px;

        right:25px;

        font-size:7px;
    }

    .nav{

        bottom:-55px;
    }

    .bar{

        width:70px;
    }

    .nav button{

        font-size:7px;
    }

    .pageCount{

        display:none;
    }

    .finalHeart{

        font-size:80px;
    }

    .final h1{

        font-size:55px;
    }

    .final p{

        font-size:8px;

        letter-spacing:2px;
    }

    .wait{

        font-size:7px;

        letter-spacing:4px;
    }

    #lastTyping{

        font-size:40px;

        min-height:55px;
    }

    .lastWords{

        font-size:20px;
    }

    .lastLine{

        margin:
            25px auto;
    }
}

</style>
</head>


<body>


<!-- =======================================================
     BACKGROUND
======================================================= -->

<div id="background">

    <div id="stars"></div>

    <div class="aura"
         style="
         left:10%;
         top:10%;
         opacity:.35;
         ">
    </div>

    <div class="aura"
         style="
         right:5%;
         bottom:5%;
         opacity:.25;
         ">
    </div>

</div>

<div id="mouseGlow"></div>


<!-- =======================================================
     INTRO
======================================================= -->

<section id="intro" class="screen">

    <div class="intro">

        <div class="introAura"></div>

        <div class="kicker">
            Something I made myself
        </div>

        <h1>
            For<br>
            <span>You ♡</span>
        </h1>

        <p>
            This isn't really a gift... it's a little experience.
        </p>

        <button
            class="begin"
            onclick="begin()">

            BEGIN

        </button>

    </div>

</section>


<!-- =======================================================
     ENVELOPE
======================================================= -->

<section
    id="envelopeScene"
    class="screen">

    <div class="envelopeArea">

        <div class="caption">
            I left something here for you
        </div>

        <div
            class="envelopeWrap"
            id="envelope"
            onclick="openEnvelope()">

            <div class="envelope">

                <div class="letterPeek">
                    A letter for you ♡
                </div>

                <div class="flap"></div>

                <div class="seal">
                    ♡
                </div>

            </div>

            <div class="tap">
                TAP TO OPEN
            </div>

        </div>

    </div>

</section>


<!-- =======================================================
     LETTER
======================================================= -->

<section
    id="letterScene"
    class="screen">

<div class="book">

<div class="paper">


<!-- =====================================================
     PAGE 1
===================================================== -->

<div class="page active">

<div class="number">
    01 / 06
</div>

<div class="label typeTarget">
    A little letter
</div>

<h1 class="typeTarget">
    Hey, you.
</h1>

<p class="typeTarget">
    I could have bought something.
</p>

<p class="typeTarget">
    But somehow, spending money didn't feel
    like the right way to make this special.
</p>

<p class="quote typeTarget">
    So I made something myself instead.
</p>

<p class="typeTarget">
    It isn't perfect.
    But neither am I.
    And that's okay.
</p>

</div>


<!-- =====================================================
     PAGE 2
===================================================== -->

<div class="page">

<div class="number">
    02 / 06
</div>

<div class="label typeTarget">
    The little things
</div>

<h2 class="typeTarget">
    I remember.
</h2>

<p class="typeTarget">
    Your random messages.
    Your little updates.
    The things you tell me without even
    thinking they're important.
</p>

<p class="typeTarget">
    And somehow, I remember more of them
    than I probably should.
</p>

<p class="quote typeTarget">
    Maybe that's because I actually
    like listening to you.
</p>

</div>


<!-- =====================================================
     PAGE 3
===================================================== -->

<div class="page">

<div class="number">
    03 / 06
</div>

<div class="label typeTarget">
    Things about you
</div>

<h2 class="typeTarget">
    Little details.
</h2>

<p class="typeTarget">
    Your favourite things.
    Your random interests.
    The things you love and the things
    you absolutely cannot stand.
</p>

<p class="typeTarget">
    I might not remember every single thing,
    but I genuinely like learning more
    about you.
</p>

<p class="quote typeTarget">
    The little details are usually
    the ones that stay.
</p>

</div>


<!-- =====================================================
     PAGE 4
===================================================== -->

<div class="page">

<div class="number">
    04 / 06
</div>

<div class="label typeTarget">
    02:00 AM
</div>

<h2 class="typeTarget">
    And somehow...
</h2>

<p class="typeTarget">
    A normal conversation turns into another
    conversation, which turns into another...
</p>

<p class="typeTarget">
    And suddenly it's ridiculously late.
</p>

<p class="quote typeTarget">
    I don't know how we keep finding things
    to talk about.
</p>

<p class="typeTarget">
    But I kind of hope we never run out.
</p>

</div>


<!-- =====================================================
     PAGE 5
===================================================== -->

<div class="page">

<div class="number">
    05 / 06
</div>

<div class="label typeTarget">
    Something honest
</div>

<h2 class="typeTarget">
    Somewhere along the way...
</h2>

<p class="typeTarget">
    You stopped being just someone
    I happened to talk to.
</p>

<p class="typeTarget">
    I started looking forward to seeing
    your messages.
</p>

<p class="typeTarget">
    I started remembering the little details.
</p>

<p class="quote typeTarget">
    And somewhere between all of that,
    I started genuinely caring about you.
</p>

<p class="typeTarget">
    No dramatic speech.
    I just wanted you to know.
</p>

</div>


<!-- =====================================================
     PAGE 6
===================================================== -->

<div class="page center">

<div class="number">
    06 / 06
</div>

<div class="label typeTarget">
    One last thing
</div>

<h2 class="typeTarget">
    Thank you. ♡
</h2>

<p class="typeTarget">
    I don't know what the future looks like.
</p>

<p class="typeTarget">
    So I won't make some huge promise
    about it.
</p>

<p class="typeTarget">
    I just hope there are more conversations,
    more stupid jokes, more random stories,
    and more moments that make us smile.
</p>

<p class="typeTarget">
    Because honestly...
</p>

<div class="signature typeTarget">
    I'm really glad I met you.
</div>

</div>


<!-- =====================================================
     NAVIGATION
===================================================== -->

<div class="nav">

<button
    id="back"
    onclick="previousPage()">

    ← BACK

</button>

<div class="middle">

<div
    class="pageCount"
    id="pageCount">

    01 / 06

</div>

<div class="bar">

<span id="progress"></span>

</div>

</div>

<button
    id="next"
    onclick="nextPage()">

    NEXT →

</button>

</div>


</div>
</div>

</section>


<!-- =======================================================
     THAT'S ALL
======================================================= -->

<section
    id="final"
    class="screen">

<div class="final">

<div class="ring"></div>

<div class="ring2"></div>

<div class="finalHeart">
    ♡
</div>

<h1>
    That's all.
</h1>

<div class="finalLine"></div>

<p>
    I hope this made you smile.
</p>

</div>

</section>


<!-- =======================================================
     LAST MESSAGE
======================================================= -->

<section id="last">

<div id="hearts"></div>

<div class="lastBox">

<div class="wait">
    Wait...
</div>

<div id="lastTyping"></div>

<div class="lastLine"></div>

<div
    class="lastWords"
    id="lastWords">

    Maybe these words can explain
    <br>

    <span class="pink">
        what I feel.
    </span>

    <br><br>

    But you're wrong.

    <br><br>

    <strong>
        There isn't a single word in this world
        that could ever explain it.
    </strong>

    <br><br>

    ♡

</div>

</div>

</section>


<!-- =======================================================
     JAVASCRIPT
======================================================= -->

<script>

// @ts-nocheck


/* =========================================================
   GLOBAL STATE
========================================================= */

let envelopeOpened = false;

let currentPage = 0;

let pageBusy = false;

let finalStarted = false;

let typingTimers = [];

let typingIntervals = [];


/* =========================================================
   ELEMENTS
========================================================= */

const intro =
    document.getElementById("intro");

const envelopeScene =
    document.getElementById("envelopeScene");

const envelope =
    document.getElementById("envelope");

const letterScene =
    document.getElementById("letterScene");

const finalScreen =
    document.getElementById("final");

const lastScreen =
    document.getElementById("last");

const pages =
    document.querySelectorAll(".page");

const progress =
    document.getElementById("progress");

const pageCount =
    document.getElementById("pageCount");

const back =
    document.getElementById("back");

const next =
    document.getElementById("next");

const lastTyping =
    document.getElementById("lastTyping");

const lastWords =
    document.getElementById("lastWords");


/* =========================================================
   CREATE STARS
========================================================= */

const stars =
    document.getElementById("stars");

for(let i=0;i<150;i++){

    const star =
        document.createElement("div");

    star.className = "star";

    star.style.left =
        Math.random()*100 + "%";

    const size =
        .5 + Math.random()*2;

    star.style.width =
        size + "px";

    star.style.height =
        size + "px";

    star.style.animationDuration =
        (7 + Math.random()*20) + "s";

    star.style.animationDelay =
        (-Math.random()*25) + "s";

    stars.appendChild(star);
}


/* =========================================================
   MOUSE GLOW
========================================================= */

const mouseGlow =
    document.getElementById("mouseGlow");

document.addEventListener(
    "mousemove",
    function(e){

        mouseGlow.style.left =
            e.clientX + "px";

        mouseGlow.style.top =
            e.clientY + "px";

    }
);


/* =========================================================
   BEGIN
========================================================= */

function begin(){

    if(intro.classList.contains("fadeOut"))
        return;

    intro.classList.add("fadeOut");

    setTimeout(function(){

        intro.style.display = "none";

        envelopeScene.classList.add("show");

    },900);
}


/* =========================================================
   OPEN ENVELOPE
========================================================= */

function openEnvelope(){

    if(envelopeOpened)
        return;

    envelopeOpened = true;

    envelope.classList.add("open");

    setTimeout(function(){

        envelopeScene.classList.remove("show");

        letterScene.classList.add("show");

        setTimeout(function(){

            updatePage();

            typeCurrentPage();

        },600);

    },1500);
}


/* =========================================================
   CLEAR TYPING
========================================================= */

function clearTyping(){

    typingTimers.forEach(
        function(timer){
            clearTimeout(timer);
        }
    );

    typingIntervals.forEach(
        function(interval){
            clearInterval(interval);
        }
    );

    typingTimers = [];

    typingIntervals = [];
}


/* =========================================================
   TYPE CURRENT PAGE
========================================================= */

function typeCurrentPage(){

    clearTyping();

    const page =
        pages[currentPage];

    const targets =
        page.querySelectorAll(".typeTarget");

    targets.forEach(
        function(element){

            element.classList.remove(
                "typing",
                "cursor"
            );

            element.style.visibility =
                "hidden";

        }
    );


    let delay = 250;


    targets.forEach(
        function(element){

            const timer =
                setTimeout(
                    function(){

                        typeElement(
                            element
                        );

                    },
                    delay
                );

            typingTimers.push(timer);


            const length =
                element.textContent
                .trim()
                .length;


            delay +=
                Math.min(
                    1200,
                    Math.max(
                        450,
                        length * 13
                    )
                );

            delay += 180;

        }
    );
}


/* =========================================================
   TYPE ONE ELEMENT
========================================================= */

function typeElement(element){

    const originalText =
        element.textContent;

    element.textContent = "";

    element.style.visibility =
        "visible";

    element.classList.add(
        "typing",
        "cursor"
    );


    let index = 0;


    const interval =
        setInterval(
            function(){

                element.textContent =
                    originalText.substring(
                        0,
                        index + 1
                    );

                index++;


                if(index >= originalText.length){

                    clearInterval(interval);

                    element.classList.remove(
                        "cursor"
                    );
                }

            },
            22
        );


    typingIntervals.push(interval);
}


/* =========================================================
   UPDATE PAGE
========================================================= */

function updatePage(){

    pages.forEach(
        function(page){

            page.classList.remove(
                "active",
                "next",
                "prev"
            );

        }
    );


    pages[currentPage]
        .classList
        .add("active");


    progress.style.width =
        (
            (currentPage + 1)
            / pages.length
            * 100
        ) + "%";


    pageCount.textContent =
        String(currentPage + 1)
        .padStart(2,"0")
        + " / "
        + String(pages.length)
        .padStart(2,"0");


    back.style.visibility =
        currentPage === 0
        ? "hidden"
        : "visible";


    next.textContent =
        currentPage === pages.length - 1
        ? "FINISH →"
        : "NEXT →";
}


/* =========================================================
   NEXT PAGE
========================================================= */

function nextPage(){

    if(pageBusy)
        return;

    if(!letterScene.classList.contains("show"))
        return;


    if(currentPage < pages.length - 1){

        pageBusy = true;

        currentPage++;

        pages[currentPage]
            .classList
            .add("next");

        updatePage();


        setTimeout(
            function(){

                typeCurrentPage();

                pageBusy = false;

            },
            120
        );

        return;
    }


    finishLetter();
}


/* =========================================================
   PREVIOUS PAGE
========================================================= */

function previousPage(){

    if(pageBusy)
        return;

    if(currentPage <= 0)
        return;

    if(!letterScene.classList.contains("show"))
        return;


    pageBusy = true;

    currentPage--;

    pages[currentPage]
        .classList
        .add("prev");

    updatePage();


    setTimeout(
        function(){

            typeCurrentPage();

            pageBusy = false;

        },
        120
    );
}


/* =========================================================
   FINISH LETTER
========================================================= */

function finishLetter(){

    if(finalStarted)
        return;

    finalStarted = true;

    pageBusy = true;

    clearTyping();


    letterScene.classList.remove("show");


    setTimeout(
        function(){

            finalScreen.classList.add("show");


            /*
               EXACT 2 SECOND WAIT
               after "That's all."
            */

            setTimeout(
                function(){

                    finalScreen.classList.remove(
                        "show"
                    );


                    setTimeout(
                        function(){

                            showLastMessage();

                        },
                        300
                    );

                },
                2000
            );

        },
        900
    );
}


/* =========================================================
   LAST MESSAGE
========================================================= */

function showLastMessage(){

    lastScreen.classList.add("show");

    createHearts();

    startFinalTyping();
}


/* =========================================================
   FINAL TYPEWRITER
========================================================= */

function startFinalTyping(){

    lastTyping.textContent = "";

    lastTyping.classList.add(
        "lastCursor"
    );


    const text =
        "What are you thinking?";


    let index = 0;


    setTimeout(
        function(){

            const interval =
                setInterval(
                    function(){

                        lastTyping.textContent =
                            text.substring(
                                0,
                                index + 1
                            );

                        index++;


                        if(index >= text.length){

                            clearInterval(interval);

                            lastTyping.classList.remove(
                                "lastCursor"
                            );


                            /*
                               Strong reveal after
                               question finishes
                            */

                            setTimeout(
                                function(){

                                    lastWords.classList.add(
                                        "reveal"
                                    );

                                },
                                900
                            );

                        }

                    },
                    75
                );

        },
        700
    );
}


/* =========================================================
   FLOATING HEARTS
========================================================= */

function createHearts(){

    const container =
        document.getElementById("hearts");


    for(let i=0;i<35;i++){

        setTimeout(
            function(){

                const heart =
                    document.createElement("div");

                heart.className =
                    "heart";


                heart.textContent =
                    Math.random() > .3
                    ? "♡"
                    : "·";


                heart.style.left =
                    Math.random()*100
                    + "%";


                heart.style.fontSize =
                    (
                        8 +
                        Math.random()*18
                    ) + "px";


                heart.style.animationDuration =
                    (
                        6 +
                        Math.random()*8
                    ) + "s";


                heart.style.opacity =
                    .2 +
                    Math.random()*.4;


                container.appendChild(
                    heart
                );


                setTimeout(
                    function(){

                        heart.remove();

                    },
                    15000
                );

            },
            i * 280
        );
    }
}


/* =========================================================
   KEYBOARD
========================================================= */

document.addEventListener(
    "keydown",
    function(e){

        if(
            !letterScene
                .classList
                .contains("show")
        ){
            return;
        }


        if(e.key === "ArrowRight"){

            e.preventDefault();

            nextPage();
        }


        if(e.key === "ArrowLeft"){

            e.preventDefault();

            previousPage();
        }

    }
);


/* =========================================================
   TOUCH SWIPE
========================================================= */

let startX = 0;

let startY = 0;


document.addEventListener(
    "touchstart",
    function(e){

        if(
            !letterScene
                .classList
                .contains("show")
        ){
            return;
        }


        startX =
            e.changedTouches[0]
            .screenX;

        startY =
            e.changedTouches[0]
            .screenY;

    },
    {
        passive:true
    }
);


document.addEventListener(
    "touchend",
    function(e){

        if(
            !letterScene
                .classList
                .contains("show")
        ){
            return;
        }


        const endX =
            e.changedTouches[0]
            .screenX;

        const endY =
            e.changedTouches[0]
            .screenY;


        const deltaX =
            startX - endX;

        const deltaY =
            startY - endY;


        /*
           Ignore vertical scrolling
        */

        if(
            Math.abs(deltaY)
            >
            Math.abs(deltaX)
        ){
            return;
        }


        if(Math.abs(deltaX) < 60)
            return;


        if(deltaX > 0){

            nextPage();

        }else{

            previousPage();

        }

    },
    {
        passive:true
    }
);


/* =========================================================
   INITIAL STATE
========================================================= */

updatePage();

</script>

</body>
</html>
