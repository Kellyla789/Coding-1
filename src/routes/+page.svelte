<script lang="ts">
    import Player from "./player.svelte";

    let player = "x";
    let gameover = false
    let board = [
        ["", "", ""],
        ["", "", ""],
        ["", "", ""],
    ];

    // --- is comparison
    function togglePlayer() {
        if (player === "x") {
            // = is assignment operator
            player = "o";
        } else {
            player = "x";
        }
    }

    function check(x, y) {
        if (gameover) return; // just ends here // early return;

        console.log(x, y);
        if (board[x][y] === "") {
            board[x][y] = player;
            togglePlayer();
        }
        console.log(player);

        let rowMatch = checkRowMatch(x);
        let colMatch = checkColumnMatch(y);
        let diagonalMatch = checkDiagonal();
        console.log("row", rowMatch);
        console.log("col", colMatch);

        if (rowMatch || colMatch || diagonalMatch) {
            gameover = true
        }
    }

    function checkRowMatch(row) {
        let item1 = board[row][0];
        let item2 = board[row][1];
        let item3 = board[row][2];
        if (item1 === item2 && item2 === item3) {
            return true;
        }
        return false;
    }

    function checkColumnMatch(col) {
        let item1 = board[0][col];
        let item2 = board[1][col];
        let item3 = board[2][col];
        if (item1 === item2 && item2 === item3) {
            return true;
        }
        return false;
    }

    function checkDiagonal() {
        let item1 = board[2][0] && board[2][2];
        let item2 = board[1][1] && board[1][1];
        let item3 = board[0][2] && board[0][0];
        if (item1 !== "" && item1 === item2 && item2 === item3) {
            return true;
        } return false;

    }

     function restartGame() {
      
      }

</script>

<h1>Let's Make Tic Tac Toe</h1>

<Player player="x" />

<div>
    <button on:click={() => check(0, 0)}><Player player={board[0][0]} /></button>
    <button on:click={() => check(0, 1)}><Player player={board[0][1]} /></button>
    <button on:click={() => check(0, 2)}><Player player={board[0][2]} /></button>
</div>
<div>
    <button on:click={() => check(1, 0)}><Player player={board[1][0]} /></button>
    <button on:click={() => check(1, 1)}><Player player={board[1][1]} /></button>
    <button on:click={() => check(1, 2)}><Player player={board[1][2]} /></button>
</div>
<div>
    <button on:click={() => check(2, 0)}><Player player={board[2][0]} /></button>
    <button on:click={() => check(2, 1)}><Player player={board[2][1]} /></button >
    <button on:click={() => check(2, 2)}><Player player={board[2][2]} /></button>
</div>

<style>
    button {
        width: 100px;
        height: 100px;
        font-family: Arial, Helvetica, sans-serif;
        font-size: large;
        font-style: bold;
        border-spacing: 10px;
        border-color: black;
        background-color: #82d4bb;
    }
    h1 {
        font-family: "Courier New", Courier, monospace;
    }
    div {
        display: flex;
    }
</style>

branch