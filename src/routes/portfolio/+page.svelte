<h1>Portfolio Page</h1>
<div class="portfolio">

    <Parallax />
    <div class="flex-row">
        <div class="cut-off">
        <img width="300px" src="./CSS.jpg" alt=""/>
        <h2>CSS</h2>
        </div>
        <ul>
            <li>style elements via class</li>
            <li>CSS properties like display, border, margins, etc.</li>
        </ul>
    </div>
    <Parallax />
    <div class="flex-row">
        <div class="cut-off">
        <img width="300px" src="./Javascript.jpg" alt=""/>
        <h2>Javascript</h2>
        </div>
        <ul>
            <li>functions are pieces of code that we can repeatedly run over</li>
            <li>parameters are part of the function signature that the function uses</li>
        </ul>
    </div>
    <Parallax />
    <div class="flex-row">
        <div class="cut-off">
        <img width="300px" src="./HTML.jpg" alt=""/>
        <h2>HTML</h2>
        </div>
        <ul>
            <li>the basic structure of the web page</li>
            <li>it contains the elemts that we use too build the web</li>
        </ul>
    </div>
</div>

<style>
    .portfolio {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
    }

    /* media query : in this case, max-width means max size */
    /*(when the max size is less than 100px,
    we want to display the content as a column)*/
    @media (max-width: 1000px) {
        .portfolio {
            /* if the maz size is less than 1000px as stated above */
            /* we apply this flex direction property */
            flex-direction: column;
            align-items: center;

        }
    }

    .flex-row {
        margin-bottom: 80px;
    }

    .flex-row {
        display: flex;
        flex-direction: column;
    }

    .cut-off {
        height: 175px;
        overflow: hidden;
        position: relative;
        margin-bottom: 20px;
        border-style: double;
        border-width: 6px;
        border-radius: 7px;
        box-shadow: 4px 4px 12px #888888;
        /*RedRedGreenGreenBlueBlue*/
    }

    ul {
        list-style: circle;
        width: 300px;
        padding-left: 16px;
    }

    h2 {
        position: absolute;
        top: 10px;
        left: 10px;
        color: white;
    }

</style>

