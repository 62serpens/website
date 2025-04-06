<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no"> <title>NODE::BLACKJACK_SIM</title>
    <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='32' height='32' viewBox='0 0 32 32'%3E%3Crect width='32' height='32' fill='%23000000'/%3E%3Ctext x='50%25' y='50%25' font-size='24' text-anchor='middle' dy='.35em' fill='%23FFD700'%3E%E2%99%A0%3C/text%3E%3C/svg%3E"> <style>
        :root {
            --bg-black: #000000;
            --text-light: #f0f0f0;
            --text-dark: #1a1a1a;
            --border-mid: #444;
            --card-bg: #ffffff;
            --card-red: #B22222; /* Firebrick */
            --card-black: #000000;
            --gold: #FFD700; /* Gold ONLY for scores */
            --button-bg: #333;
            --button-hover: #555;
            --button-active: #111;
            --button-disabled-bg: #222;
            --button-disabled-text: #666;
            --input-bg: #222;
            --message-color: #f0f0f0; /* Messages are light text */
            --score-display-color: #f0f0f0; /* Hand scores are light text */
        }

        *, *::before, *::after { box-sizing: border-box; }
        html { height: 100%; }

        body {
            font-family: Arial, Helvetica, sans-serif;
            background-color: var(--bg-black);
            color: var(--text-light);
            margin: 0;
            padding: 0;
            text-align: center;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
            overscroll-behavior-y: contain;
        }

        /* --- Status Bar --- */
        .status-bar {
            background-color: var(--bg-black);
            padding: 8px 15px;
            border-bottom: 1px solid var(--border-mid);
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 15px;
            flex-wrap: wrap;
            position: sticky; /* Keep visible on desktop */
            top: 0;
            z-index: 10;
        }
        .back-link {
            color: var(--text-light);
            text-decoration: none;
            font-size: 0.9em;
            white-space: nowrap;
            transition: color 0.1s ease;
        }
        .back-link:hover { color: var(--gold); }

        .player-info {
            display: flex;
            gap: 15px;
            font-size: 0.9em;
            white-space: nowrap;
        }
        .player-info span { color: var(--text-light); }
        .player-info span span { color: var(--gold); font-weight: bold; }

        /* --- Main Game Area --- */
        .game-area {
            flex-grow: 1;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px 10px;
            gap: 15px;
            width: 100%;
            max-width: 600px;
            margin: 0 auto;
        }

        #messages {
            min-height: 1.8em;
            font-weight: bold;
            font-size: 1.3em;
            color: var(--message-color);
            padding: 0 5px;
        }

        .hand-area { width: 100%; }
        .hand-area h2 {
            margin: 0 0 8px 0;
            font-size: 1em;
            font-weight: normal;
            opacity: 0.8;
            display: flex;
            justify-content: center;
            align-items: baseline;
            gap: 5px;
            color: var(--text-light);
        }
        .hand-area h2 span {
             color: var(--score-display-color);
             font-weight: bold;
             font-size: 1.1em;
        }

        .cards {
            min-height: 90px; /* Increased height for new card style */
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            align-items: center;
            gap: 8px; /* Increased gap */
        }

        /* --- New Card Styling --- */
        .card {
            background: var(--card-bg);
            color: var(--card-black);
            border: 1px solid var(--border-mid);
            border-radius: 5px; /* Slightly more rounded */
            width: 60px; /* Fixed width */
            height: 90px; /* Fixed height - Aspect ratio approx 1.5 */
            box-shadow: 2px 2px 3px rgba(0,0,0,0.4);
            position: relative; /* For positioning rank/suit */
            display: inline-block;
            vertical-align: top;
            margin: 3px;
            font-family: Arial, Helvetica, sans-serif; /* Standard font */
            font-size: 1.1em; /* Adjust base size if needed */
            user-select: none;
            overflow: hidden; /* Hide potential overflow */
        }
        .card.red { color: var(--card-red); }

        /* Positioning Rank/Suit using pseudo-elements */
        .card::before, .card::after {
            position: absolute;
            font-size: 0.9em; /* Smaller font for corners */
            line-height: 1;
             white-space: pre; /* Allow suit to space correctly */
             text-align: center;
             width: 100%; /* Center text block */
        }
        /* Top-left Rank & Suit */
        .card::before {
            content: attr(data-rank) "\A" attr(data-suit); /* Rank, newline, Suit */
            top: 5px;
            left: 0; /* Align text block left */
        }
         /* Bottom-right Rank & Suit (rotated) */
         .card::after {
            content: attr(data-rank) "\A" attr(data-suit);
            bottom: 5px;
            left: 0; /* Align text block left before rotating */
            transform: rotate(180deg);
        }

        /* Optional: Big central suit (simpler version: just show it larger) */
         /* We'll omit this for now to keep it simple & fast */

        /* Style for dealer's hidden card */
        .card.hidden {
            background: repeating-linear-gradient(
                45deg,
                #555, #555 5px, #666 5px, #666 10px
            );
            color: transparent;
            box-shadow: inset 0 0 5px rgba(0,0,0,0.5);
        }
        .card.hidden::before, .card.hidden::after { content: ''; } /* Hide corner text */


        /* --- Controls --- */
        .controls-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
            width: 100%;
            margin-top: 15px;
        }

        .betting-controls, .action-controls {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            align-items: center;
            gap: 10px;
        }

        .betting-controls label { font-size: 0.9em; opacity: 0.9; }

        .game-button, .bet-input, .bet-button {
            padding: 12px 18px;
            font-size: 1.1em;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            background-color: var(--button-bg);
            color: var(--text-light);
            transition: background-color 0.1s ease, transform 0.05s ease;
            font-weight: bold;
            -webkit-tap-highlight-color: transparent;
        }
        .game-button:hover, .bet-button:hover { background-color: var(--button-hover); }
        .game-button:active, .bet-button:active { background-color: var(--button-active); transform: scale(0.98); }
        .game-button:disabled {
             background-color: var(--button-disabled-bg);
             color: var(--button-disabled-text);
             cursor: not-allowed;
             transform: none;
        }

        .bet-input {
            width: 80px;
            background-color: var(--input-bg);
            color: var(--text-light);
            text-align: center;
            cursor: text;
            border: 1px solid var(--border-mid);
            padding: 10px;
            font-size: 1.1em;
            font-weight: bold;
             -moz-appearance: textfield;
        }
         .bet-input::-webkit-outer-spin-button,
         .bet-input::-webkit-inner-spin-button {
             -webkit-appearance: none;
             margin: 0;
        }

         /* --- Mobile Adjustments --- */
        @media (max-width: 480px) {
            body { padding-top: 0; }
             .status-bar {
                 position: static; /* Status bar scrolls with content on mobile */
                 padding: 6px 10px;
                 gap: 10px;
             }
            .back-link { font-size: 0.8em; }
            .player-info { font-size: 0.8em; gap: 10px; flex-grow: 1; justify-content: flex-end; }

            .game-area { padding: 15px 5px; gap: 12px; }
            #messages { font-size: 1.1em; min-height: 1.5em; }
            .hand-area h2 { font-size: 0.9em; }
            .cards { min-height: 80px; gap: 4px; } /* Adjusted height */
            .card {
                 width: 50px; /* Smaller width */
                 height: 75px; /* Smaller height */
                 font-size: 1em; /* Adjust base size */
                 margin: 2px;
            }
             .card::before, .card::after { font-size: 0.7em; } /* Smaller corner font */
             .card::before { top: 3px; left: 3px; }
             .card::after { bottom: 3px; right: 3px; left: auto; } /* Adjust after pseudo */


            .controls-container { gap: 12px; margin-top: 10px;}
            .game-button, .bet-input, .bet-button {
                font-size: 1em;
                padding: 10px 15px;
            }
            .bet-input { width: 70px; padding: 8px;}
        }
         @media (max-width: 360px) { /* Adjust for very narrow screens */
             .player-info { justify-content: center; gap: 8px;}
             .status-bar { justify-content: center; }
             .back-link { margin-bottom: 5px; }
             .card { width: 45px; height: 68px; font-size: 0.9em; }
             .card::before, .card::after { font-size: 0.6em; }
         }

    </style>
</head>
<body>

    <header class="status-bar">
        <a href="index.html" class="back-link" title="Return to Main Node">[&lt;&lt; BACK TO NODE]</a>
        <div class="player-info">
            <span>Coins: <span id="player-coins">1000</span></span>
            <span>High Score: <span id="high-score">1000</span></span>
        </div>
    </header>

    <main class="game-area">
        <div id="messages">Place your bet!</div>

        <div class="hand-area dealer-hand">
            <h2>Dealer (<span id="dealer-score">0</span>)</h2>
            <div id="dealer-cards" class="cards">
                </div>
        </div>

        <div class="hand-area player-hand">
            <h2>Player (<span id="player-score">0</span>)</h2>
            <div id="player-cards" class="cards">
                </div>
        </div>

        <div class="controls-container">
            <div class="betting-controls">
                <label for="bet-amount">Bet:</label>
                <input type="number" id="bet-amount" class="bet-input" value="10" min="1" step="1">
                <button id="deal-button" class="bet-button">Deal</button>
             </div>

            <div class="action-controls">
                <button id="hit-button" class="game-button" disabled>Hit</button>
                <button id="stand-button" class="game-button" disabled>Stand</button>
            </div>
        </div>
    </main>

     <script>
        try {
            document.addEventListener('DOMContentLoaded', () => {
                // --- DOM Elements ---
                const playerCoinsEl = document.getElementById('player-coins');
                const highScoreEl = document.getElementById('high-score');
                const messagesEl = document.getElementById('messages');
                const dealerScoreEl = document.getElementById('dealer-score');
                const playerScoreEl = document.getElementById('player-score');
                const dealerCardsEl = document.getElementById('dealer-cards');
                const playerCardsEl = document.getElementById('player-cards');
                const dealButton = document.getElementById('deal-button');
                const hitButton = document.getElementById('hit-button');
                const standButton = document.getElementById('stand-button');
                const betAmountInput = document.getElementById('bet-amount');

                // --- Check if elements exist (Debugging) ---
                 if (!dealButton || !hitButton || !standButton) {
                    console.error("Button elements not found!");
                    return; // Stop script if critical elements are missing
                 }
                 if (!playerCoinsEl || !highScoreEl || !messagesEl || !dealerScoreEl || !playerScoreEl || !dealerCardsEl || !playerCardsEl || !betAmountInput) {
                     console.error("One or more display/input elements not found!");
                     // Allow script to continue but log error
                 }


                // --- Game State Variables ---
                let deck = [];
                let playerCards = [];
                let dealerCards = [];
                let playerScore = 0;
                let dealerScore = 0;
                let playerCoins = 1000;
                let highScore = 1000;
                let currentBet = 0;
                let isGameOver = true; // Start game over

                // --- Game Constants ---
                const suits = ['♠', '♥', '♦', '♣'];
                const ranks = ['2', '3', '4', '5', '6', '7', '8', '9', 'T', 'J', 'Q', 'K', 'A'];

                // --- Core Functions ---

                function createDeck() {
                    deck = [];
                    for (const suit of suits) {
                        for (const rank of ranks) {
                            let value = 0;
                            let color = (suit === '♥' || suit === '♦') ? 'red' : 'black';
                            if (isNaN(parseInt(rank))) {
                                if (rank === 'A') value = 11;
                                else value = 10;
                            } else {
                                value = parseInt(rank);
                            }
                            deck.push({ rank, suit, value, color });
                        }
                    }
                }

                function shuffleDeck() {
                    for (let i = deck.length - 1; i > 0; i--) {
                        const j = Math.floor(Math.random() * (i + 1));
                        [deck[i], deck[j]] = [deck[j], deck[i]];
                    }
                }

                function getCardValue(hand) {
                    let score = 0;
                    let aceCount = 0;
                    for (const card of hand) {
                        score += card.value;
                        if (card.rank === 'A') aceCount++;
                    }
                    while (score > 21 && aceCount > 0) {
                        score -= 10;
                        aceCount--;
                    }
                    return score;
                }

                // --- UPDATED renderCard function for new CSS style ---
                function renderCard(card, targetElement, isHidden = false) {
                    const cardDiv = document.createElement('div');
                    cardDiv.classList.add('card');
                    if (isHidden) {
                        cardDiv.classList.add('hidden');
                        // No text content needed for hidden
                    } else {
                        // Set data attributes for pseudo-elements
                        cardDiv.setAttribute('data-rank', card.rank);
                        cardDiv.setAttribute('data-suit', card.suit);
                        if (card.color === 'red') {
                            cardDiv.classList.add('red');
                        }
                        // Text content is now handled by ::before and ::after
                    }
                    targetElement.appendChild(cardDiv);
                }


                function renderHands(revealDealer = false) {
                    dealerCardsEl.innerHTML = '';
                    playerCardsEl.innerHTML = '';

                    // Render Dealer Cards
                    if (dealerCards.length > 0) {
                         // Show first card hidden unless revealDealer is true
                        renderCard(dealerCards[0], dealerCardsEl, !revealDealer);
                        for (let i = 1; i < dealerCards.length; i++) {
                            renderCard(dealerCards[i], dealerCardsEl);
                        }
                    }

                    // Render Player Cards
                    playerCards.forEach(card => renderCard(card, playerCardsEl));

                    // Update Scores
                    playerScore = getCardValue(playerCards);
                    if (playerScoreEl) playerScoreEl.textContent = playerScore;

                    if (revealDealer) {
                        dealerScore = getCardValue(dealerCards);
                        if (dealerScoreEl) dealerScoreEl.textContent = dealerScore;
                    } else if (dealerCards.length > 0) {
                         // Show score of only the visible card(s)
                         let visibleDealerScore = 0;
                         if(dealerCards.length > 1) {
                              // Calculate score based only on visible cards (all except first)
                              visibleDealerScore = getCardValue(dealerCards.slice(1));
                         }
                         // Special case: if only hidden + Ace showing, score is 11
                         if(dealerCards.length === 2 && dealerCards[1].rank === 'A' && visibleDealerScore === 11){
                              // Value is already 11, so this is correct
                         }
                         if (dealerScoreEl) dealerScoreEl.textContent = visibleDealerScore;
                    } else {
                         if (dealerScoreEl) dealerScoreEl.textContent = 0; // No cards yet
                    }
                }


                function updateScoresAndCoinsDisplay() {
                    if(playerCoinsEl) playerCoinsEl.textContent = playerCoins;
                    if(highScoreEl) highScoreEl.textContent = highScore;
                }

                function setMessage(msg) {
                     if(messagesEl) messagesEl.textContent = msg;
                }

                function updateHighScore() {
                    if (playerCoins > highScore) {
                        highScore = playerCoins;
                        localStorage.setItem('blackjack_highScore', highScore.toString());
                        console.log(`New High Score: ${highScore}`); // Debugging log
                    }
                }

                function saveCoins() {
                    localStorage.setItem('blackjack_coins', playerCoins.toString());
                }

                function initializeScore() {
                    let coinsStr = localStorage.getItem('blackjack_coins');
                    let highScoreStr = localStorage.getItem('blackjack_highScore');
                    let startingCoins = 1000;

                    playerCoins = (coinsStr === null || isNaN(parseInt(coinsStr)) || parseInt(coinsStr) <= 0) ? startingCoins : parseInt(coinsStr);
                    highScore = (highScoreStr === null || isNaN(parseInt(highScoreStr))) ? playerCoins : parseInt(highScoreStr);

                     if (highScore < playerCoins) highScore = playerCoins;
                     // Also ensure high score isn't lower than starting amount if coins reset somehow
                     if (highScore < startingCoins) highScore = startingCoins;


                    saveCoins();
                    localStorage.setItem('blackjack_highScore', highScore.toString());
                    updateScoresAndCoinsDisplay();
                    console.log(`Scores Initialized - Coins: ${playerCoins}, High Score: ${highScore}`); // Debugging log
                }

                // --- Renamed from checkGameOver for clarity ---
                function checkPlayerBust() {
                    playerScore = getCardValue(playerCards); // Ensure score is current
                    if (playerScore > 21) {
                        setMessage(`Bust! (${playerScore}) You lose ${currentBet} coins.`);
                        // Player already lost bet when dealing, no coin change needed here on bust loss
                        endGame('lose'); // Pass outcome string
                        return true;
                    }
                    return false;
                }

                 function dealerTurn() {
                    console.log("Dealer's turn starts."); // Debugging log
                    renderHands(true); // Reveal dealer's hidden card and true score

                    dealerScore = getCardValue(dealerCards); // Calculate full score

                    // Use interval for slight delay between dealer hits - more natural feel? Optional.
                    // If going for MAX speed, remove interval and use while loop directly.
                    const dealerHitInterval = setInterval(() => {
                        dealerScore = getCardValue(dealerCards); // Recalculate each time inside interval
                         dealerScoreEl.textContent = dealerScore; // Update score display

                        if (dealerScore < 17) {
                            console.log(`Dealer hits on ${dealerScore}`); // Debugging log
                            const newCard = deck.pop();
                            if (!newCard) { // Safety check for empty deck
                                 console.error("Deck empty during dealer turn!");
                                 clearInterval(dealerHitInterval);
                                 determineWinner(); // Determine winner with current hands
                                 return;
                            }
                            dealerCards.push(newCard);
                            renderCard(newCard, dealerCardsEl);
                        } else {
                            console.log(`Dealer stands on ${dealerScore}`); // Debugging log
                            clearInterval(dealerHitInterval); // Stop hitting
                            determineWinner(); // Determine outcome now
                        }
                    }, 600); // Delay in ms (adjust for desired speed, 0 for instant)
                }


                function determineWinner() {
                    // Final score calculation already happened in dealerTurn or before playerStand
                    console.log(`Determining winner: Player=${playerScore}, Dealer=${dealerScore}`); // Debugging log

                    let message = "";
                    let outcome = 'lose'; // Default outcome

                     if (dealerScore > 21) {
                        message = `Dealer busts! (${dealerScore}) You win ${currentBet} coins!`;
                        playerCoins += currentBet * 2; // Win bet + original bet back
                        outcome = 'win';
                     } else if (playerScore > dealerScore) {
                        message = `You win! (${playerScore} vs ${dealerScore}) +${currentBet} coins!`;
                        playerCoins += currentBet * 2;
                        outcome = 'win';
                    } else if (playerScore < dealerScore) {
                        message = `Dealer wins! (${dealerScore} vs ${playerScore}) You lose ${currentBet} coins.`;
                         // Coins already deducted, outcome remains 'lose'
                    } else { // Push
                        message = `Push! (${playerScore} vs ${dealerScore}) Bet returned.`;
                        playerCoins += currentBet; // Return original bet
                        outcome = 'push';
                     }

                     setMessage(message);
                     endGame(outcome);
                 }

                 function handleBlackjack() {
                     playerScore = getCardValue(playerCards);
                     // Calculate initial dealer score based on BOTH cards for Blackjack check
                     dealerScore = getCardValue(dealerCards);

                     const playerHasBlackjack = playerScore === 21 && playerCards.length === 2;
                     // Check dealer BJ even if player doesn't have one
                     const dealerHasBlackjack = dealerScore === 21 && dealerCards.length === 2;

                     if (!playerHasBlackjack && !dealerHasBlackjack) {
                         return false; // No immediate Blackjack, continue game
                     }

                     // If we reach here, at least one person has Blackjack
                     console.log("Blackjack detected!"); // Debugging log
                     renderHands(true); // Reveal dealer card immediately

                     if (playerHasBlackjack && dealerHasBlackjack) {
                         setMessage("Push! Both have Blackjack!");
                         playerCoins += currentBet; // Return bet
                         endGame('push');
                         return true;
                     } else if (playerHasBlackjack) {
                         setMessage(`Blackjack! You win ${Math.floor(currentBet * 1.5)} coins!`);
                         playerCoins += currentBet + Math.floor(currentBet * 1.5); // Bet back + 3:2 payout
                         endGame('blackjack');
                         return true;
                     } else { // Only dealer has Blackjack
                         setMessage(`Dealer has Blackjack! You lose ${currentBet} coins.`);
                         // Coins already deducted
                         endGame('lose');
                         return true;
                     }
                 }


                 function startGame() {
                    console.log("Attempting to start game..."); // Debugging log
                    currentBet = parseInt(betAmountInput.value);

                    if (isNaN(currentBet) || currentBet <= 0) {
                        setMessage("Please enter a positive bet amount.");
                        return;
                    }
                    if (currentBet > playerCoins) {
                        setMessage("Bet cannot exceed your available coins!");
                        return;
                    }

                    // --- Deduct Bet & Initialize ---
                    playerCoins -= currentBet;
                    updateScoresAndCoinsDisplay();
                    saveCoins(); // Save immediately after betting

                    isGameOver = false; // Game is now active
                    createDeck();
                    shuffleDeck();
                    playerCards = [deck.pop(), deck.pop()];
                    dealerCards = [deck.pop(), deck.pop()];
                    playerScore = 0; // Reset visual scores
                    dealerScore = 0;

                    setMessage("Hit or Stand?");
                    renderHands(false); // Initial render, keep dealer card hidden

                    // --- Check for immediate Blackjacks ---
                    if (handleBlackjack()) {
                        console.log("Game ended immediately by Blackjack."); // Debugging log
                        return; // Game already ended and buttons managed by endGame
                    }

                    // --- Enable/Disable Buttons ---
                     console.log("Enabling Hit/Stand buttons."); // Debugging log
                     dealButton.disabled = true;
                     betAmountInput.disabled = true;
                     hitButton.disabled = false;
                     standButton.disabled = false;
                 }


                function playerHit() {
                    console.log("Hit button clicked."); // Debugging log
                    if (isGameOver || hitButton.disabled) {
                         console.log("Hit ignored: Game over or button disabled.");
                         return; // Don't allow hit if game is over or button disabled
                    }

                    const newCard = deck.pop();
                     if (!newCard) {
                          console.error("Deck empty during player hit!");
                          setMessage("Error: Deck empty!");
                          endGame('error'); // End game on error
                          return;
                     }
                    playerCards.push(newCard);
                    renderHands(false); // Re-render player hand, keep dealer hidden

                    if (checkPlayerBust()) { // Check if player busted
                        console.log("Player busted."); // Debugging log
                        return; // Game ended by bust
                    }

                    // If player hits 21, automatically stand (optional but common)
                     if (getCardValue(playerCards) === 21) {
                         console.log("Player has 21, automatically standing.");
                         playerStand();
                     }
                }

                function playerStand() {
                    console.log("Stand button clicked."); // Debugging log
                    if (isGameOver || standButton.disabled) {
                         console.log("Stand ignored: Game over or button disabled.");
                         return; // Don't allow stand if game is over or button disabled
                    }
                    hitButton.disabled = true;
                    standButton.disabled = true;
                    dealerTurn(); // Start dealer's logic
                }

                 function endGame(outcome) { // outcome can be 'win', 'lose', 'push', 'blackjack', 'error'
                     console.log(`Game ended with outcome: ${outcome}`); // Debugging log
                     isGameOver = true;
                     hitButton.disabled = true;
                     standButton.disabled = true;
                     dealButton.disabled = false;
                     betAmountInput.disabled = false;

                     updateHighScore();
                     saveCoins();
                     updateScoresAndCoinsDisplay();

                    // Check if player ran out of coins after the round resolution
                    if (playerCoins <= 0) {
                        // Append to existing message if possible, or set new one
                        let finalMessage = messagesEl.textContent + " You're out of coins! Restarting with 1000.";
                        setMessage(finalMessage);
                        playerCoins = 1000;
                         updateHighScore(); // Re-check high score relative to restart amount
                         saveCoins();
                         localStorage.setItem('blackjack_highScore', highScore.toString());
                        updateScoresAndCoinsDisplay();
                        // Slightly delay placing bet message after reset message
                         setTimeout(() => {
                             setMessage("Place your bet!");
                         }, 2000); // Show reset message for 2 seconds
                    } else {
                         // Optionally add Place Bet message after a short delay
                          // setTimeout(() => {
                          //    if(isGameOver) setMessage("Place your bet!");
                          // }, 1500);
                    }
                }

                // --- Event Listeners ---
                dealButton.addEventListener('click', startGame);
                hitButton.addEventListener('click', playerHit);
                standButton.addEventListener('click', playerStand);

                 betAmountInput.addEventListener('keypress', function (e) {
                     if (e.key === 'Enter' && !dealButton.disabled) {
                         e.preventDefault(); // Prevent potential form submission if it was in a form
                         startGame();
                     }
                 });

                // --- Initial Setup ---
                initializeScore();
                setMessage("Place your bet!");
                hitButton.disabled = true; // Ensure disabled initially
                standButton.disabled = true; // Ensure disabled initially
                dealButton.disabled = false;
                betAmountInput.disabled = false;


                console.log("Blackjack Game Initialized and Ready.");

            }); // End DOMContentLoaded
        } catch (error) {
            console.error("!!! BLACKJACK SIM FAULT !!!:", error);
            document.body.innerHTML = `<div style="color:#ff3333; background:#000000; padding: 20px; font-family: monospace; font-size: 14px;">SYSTEM_ERROR [MODULE::BLACKJACK_SIM]<br><br>${error.message}<br>----------------<br>${error.stack || 'NO_STACK_TRACE'}<br><br><a href="index.html" style="color:#fff;">&lt;&lt; Return to Node</a></div>`;
        }
    </script>

</body>
</html>
