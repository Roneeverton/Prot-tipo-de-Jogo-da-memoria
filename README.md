# Prot-tipo-de-Jogo-da-memoria

var board = [1, 2, 1, 2];
var boardFlipped = [false, false, false, false];
var cardFlipped = -1;

function flipCard(card) {
    if (boardFlipped[card]) {
        console.log("Esta carta já foi virada.");
        return;
    }
    console.log("Carta " + card + " é o número " + board[card]);
    boardFlipped[card] = true;
    if (cardFlipped < 0) {
        cardFlipped = card;
    } else {
        if (board[card] == board[cardFlipped]) {
            console.log("Par encontrado!");
        } else {
            console.log("As cartas não combinam. Vire-as de volta.");
            boardFlipped[card] = false;
            boardFlipped[cardFlipped] = false;
        }
        cardFlipped = -1;
    }
}
