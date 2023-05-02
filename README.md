Download Link: https://assignmentchef.com/product/solved-comp2396-object-oriented-programming-and-java-assignment-3
<br>
<h1>Overview</h1>

This assignment tests your understanding of inheritance and polymorphism, and their implementations in Java. You are going to implement a card game called Big Two. A number of classes will be provided to aid your implementation. These include a Card class which models a card, a CardList class which models a list of cards, a Deck class which models a deck of cards, a CardGamePlayer class which models a card game player, and a

BigTwoConsole class which models a user interface for the Big Two card game, respectively. You may refer to their Javadoc for details of these classes. You should <strong>NOT</strong> modify any of these classes in completing your assignment.

As a minimum requirement, you are required to implement the following classes: BigTwo,

BigTwoCard, BigTwoDeck, Hand, Single, Pair, Triple, Straight, Flush, FullHouse, Quad and StraightFlush. The BigTwo class models the Big Two card game logics. The BigTwoCard class and the BigTwoDeck class model a card and a deck of cards used in a Big Two card game, respectively. The Hand class models a hand of cards in general card games. The Single, Pair, Triple, Straight, Flush, FullHouse, Quad and StraighFlush classes model hands of legal combinations of cards in a Big Two card game. You are free to introduce new instance variables and methods to these classes. Besides, you are also free to design and introduce new classes in the inheritance trees as appropriate. You are required to write Javadoc for all public classes and their public class members. <strong><em>Specifications </em></strong>

<h2>General game rules</h2>

Please refer to <u>https://www.pagat.com/climbing/bigtwo.html</u> for a detailed description of the Big Two card game. To simplify your implementation, we will adopt the following rules:

<ul>

 <li>A standard 52 card pack is used.</li>

 <li>The order of ranks from high to low is 2, A, K, Q, J, 10, 9, 8, 7, 6, 5, 4, 3.</li>

 <li>The order of suits from high to low is Spades, Hearts, Clubs, Diamonds.</li>

 <li>There are always four players in a game.</li>

 <li>Each player holds 13 (randomly assigned) cards at the beginning of the game.</li>

 <li>The player holding the Three of Diamonds will begin the game by playing a hand of legal combination of cards <strong>that includes the Three of Diamonds</strong>.</li>

 <li>Players take turns to play by either playing a hand of legal combination of cards that beats the last hand of cards played on the table, or by passing his turn to the next player.</li>

 <li>A hand of legal combination of cards can only be beaten by another better hand of legal combination of cards <strong>with the same number of cards</strong>.</li>

 <li>A player cannot pass his turn to the next player if he is the one who played the last hand of cards on the table. In this case, he can play a hand of any legal combination of cards regardless of the last hand he played on the table.</li>

 <li>The game ends when any of the players has no more cards in his hand. <strong>Legal combinations of Cards </strong></li>

 <li><strong>Single</strong>. This hand consists of only one single card. The only card in a single is referred to as the top card of this single. A single with a higher rank beats a single with a lower rank. For singles with the same rank, the one with a higher suit beats the one with a lower suit.</li>

 <li><strong>Pair</strong>. This hand consists of two cards with the same rank. The card with a higher suit in a pair is referred to as the top card of this pair. A pair with a higher rank beats a pair with a lower rank. For pairs with the same rank, the one containing the highest suit beats the other.</li>

 <li><strong>Triple</strong>. This hand consists of three cards with the same rank. The card with the highest suit in a triple is referred to as the top card of this triple. A triple with a higher rank beats a triple with a lower rank.</li>

 <li><strong>Straight</strong>. This hand consists of five cards with consecutive ranks. For the sake of simplicity, 2 and A can only form a straight with K but not with 3. The card with the highest rank in a straight is referred to as the top card of this straight. A straight having a top card with a higher rank beats a straight having a top card with a lower rank. For straights having top cards with the same rank, the one having a top card with a higher suit beats the one having a top card with a lower suit.</li>

 <li><strong>Flush</strong>. This hand consists of five cards with the same suit. The card with the highest rank in a flush is referred to as the top card of this flush. A flush always beats any straights. A flush with a higher suit beats a flush with a lower suit. For flushes with the same suit, the one having a top card with a higher rank beats the one having a top card with a lower rank.</li>

 <li><strong>Full House</strong>. This hand consists of five cards, with two having the same rank and three having another same rank. The card in the triplet with the highest suit in a full house is referred to as the top card of this full house. A full house always beats any straights and flushes. A full house having a top card with a higher rank beats a full house having a top card with a lower rank.</li>

 <li><strong>Quad</strong>. This hand consists of five cards, with four having the same rank. The card in the quadruplet with the highest suit in a quad is referred to as the top card of this quad. A quad always beats any straights, flushes and full houses. A quad having a top card with a higher rank beats a quad having a top card with a lower rank.</li>

 <li><strong>Straight Flush</strong>. This hand consists of five cards with consecutive ranks and the same suit. For the sake of simplicity, 2 and A can only form a straight flush with K but not with 3. The card with the highest rank in a straight flush is referred to as the top card of this straight flush. A straight flush always beats any straights, flushes, full houses and quads. A straight flush having a top card with a higher rank beats a straight flush having a top card with a lower rank. For straight flushes having top cards with the same rank, the one having a top card with a higher suit beats one having a top card with a lower suit.</li>

</ul>

<h2>The BigTwo class</h2>

The BigTwo class is used to model a Big Two card game. It has private instance variables for storing a deck of cards, a list of players, a list of hands played on the table, an index of the current player, and a console for providing the user interface. Below is a detailed description for the BigTwo class.




Specification of the BigTwo class:

<em>public constructor: </em>

BigTwo() – a constructor for creating a Big Two card game. You should create 4 players and add them to the player list. You should also create a ‘console’ (i.e., a

BigTwoConsole object) for providing the user interface.

<em>private instance variables: </em>

Deck deck – a deck of cards.

<sub>ArrayList&lt;CardGamePLayer&gt; playerList</sub> – a list of players. ArrayList&lt;Hand&gt; handsOnTable – a list of hands played on the table. int currentIdx – an integer specifying the index of the current player.

BigTwoConsole bigTwoConsole – a BigTwoConsole object for providing the user interface.

<em>public methods: </em>

Deck getDeck() – a method for retrieving the deck of cards being used.

ArrayList&lt;CardGamePlayer&gt; getPlayerList() – a method for retrieving the list of players.

ArrayList&lt;Hand&gt; getHandsOnTable() – a method for retrieving the list of hands played on the table.

int getCurrentIdx() – a method for retrieving the index of the current player. void start(BigTwoDeck deck) – a method for starting the game with a (shuffled) deck of cards supplied as the argument. It implements the Big Two game logics. <em>public static methods: </em>

void main(String[] args) – a method for starting a Big Two card game. It should create a Big Two card game, create and shuffle a deck of cards, and start the game with the deck of cards.

Hand composeHand(CardGamePlayer player, CardList cards) – a method for returning a valid hand from the specified list of cards of the player. Returns null is no valid hand can be composed from the specified list of cards.

<h2>The BigTwoCard class</h2>

The BigTwoCard class is a subclass of the Card class, and is used to model a card used in a

Big Two card game. It should override the compareTo() method it inherited from the Card class to reflect the ordering of cards used in a Big Two card game. Below is a detailed description for the BigTwoCard class.

Specification of the BigTwoCard class:

<em>public constructor: </em>

BigTwoCard(int suit, int rank) – a constructor for building a card with the specified suit and rank. suit is an integer between 0 and 3, and rank is an integer between 0 and 12.

<em>             </em>

<em>overriding method: </em>

int compareTo(Card card) – a method for comparing the order of this card with the specified card. Returns a negative integer, zero, or a positive integer as this card is less than, equal to, or greater than the specified card.

<h2>The BigTwoDeck class</h2>

The BigTwoDeck class is a subclass of the Deck class, and is used to model a deck of cards used in a Big Two card game. It should override the initialize() method it inherited from the Deck class to create a deck of Big Two cards. Below is a detailed description for the BigTwoDeck class.

Specification of the BigTwoDeck class:

<em>overriding method: </em>

void initialize() – a method for initializing a deck of Big Two cards. It should remove all cards from the deck, create 52 Big Two cards and add them to the deck.

<h2>The Hand class</h2>

The Hand class is a subclass of the CardList class, and is used to model a hand of cards. It has a private instance variable for storing the player who plays this hand. It also has methods for getting the player of this hand, checking if it is a valid hand, getting the type of this hand, getting the top card of this hand, and checking if it beats a specified hand. Below is a detailed description for the Hand class.

Specification of the Hand class:

<em>public constructor: </em>

<sub>Hand(CardGamePlayer player, CardList cards)</sub> – a constructor for building a hand with the specified player and list of cards.

<em>private instance variable: </em>

<em> </em>CardGamePlayer player – the player who plays this hand. <em>public methods: </em>

CardGamePlayer getPlayer() – a method for retrieving the player of this hand.

Card getTopCard() – a method for retrieving the top card of this hand.

boolean beats(Hand hand) – a method for checking if this hand beats a specified hand.

<em>abstract methods: </em>

boolean isValid() – a method for checking if this is a valid hand.

String getType() – a method for returning a string specifying the type of this hand.

<h2>The Single, Pair, Triple, Straight, Flush, FullHouse, Quad, StraightFlush classes</h2>

These classes are a subclass of the Hand class, and are used to model a hand of single, pair, triple, straight, flush, full house, quad and straight flush in a Big Two card game, respectively. They should override methods of the Hand class as appropriate. In particular, the getType() method should return the name of the class as a String object in these classes modelling legal hands in a Big Two card game. For examples, calling the getType() method on a Triple object should return “Triple”, while calling the getType() method on a FullHouse object should return “FullHouse”.

<h1>Sample output</h1>

<h2>Showing cards on the table</h2>

At each player’s turn, your program should print out the cards held by each player as well as the last hand played on the table (see figure 1). You can achieve this by calling the repaint() method of the BigTwoConsole object.

&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] 12 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] 12 [  ]

&lt;Player 2&gt;

==&gt; 0 [&#x2666;3] 1 [&#x2660;3] 2 [&#x2666;5] 3 [&#x2666;6] 4 [&#x2663;7] 5 [&#x2665;7] 6 [&#x2660;8] 7 [&#x2663;0] 8 [&#x2665;0] 9 [&#x2666;Q] 10 [&#x2660;Q] 11 [&#x2665;A] 12 [&#x2666;2]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] 12 [  ] &lt;Table&gt;

[Empty]




<strong>Figure 1. Showing cards on the table. </strong>

<h2>Getting user input</h2>

At each player’s turn, your program should read from the keyboard a space-separated list of indices that represent the list of cards played by the player. You can achieve this by calling the getSelected() method of the BigTwoConsole object.

<h2>Showing the hand played by a player</h2>

After the current player has selected a list of cards to play, your program should produce the followings to the console (see figure 2):

<ul>

 <li>Print “Not a legal move!!!” to the console if the cards selected do not compose a valid hand or the move is not legal, and prompt the player to select again.</li>

 <li>Print to the console the type of the hand followed by the cards in the hand if the cards selected do compose a valid hand and is a legal move.</li>

 <li>Print “{pass}” to the console if the player enters an empty list and {pass} is a legal move.</li>

</ul>

&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] 12 [  ]

&lt;Player 1&gt;

==&gt; 0 [&#x2666;3] 1 [&#x2663;4] 2 [&#x2666;5] 3 [&#x2663;5] 4 [&#x2660;5] 5 [&#x2666;6] 6 [&#x2660;8] 7 [&#x2665;9] 8 [&#x2660;J] 9 [&#x2663;K] 10 [&#x2663;A] 11 [&#x2665;A] 12 [&#x2663;2]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] 12 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] 12 [  ] &lt;Table&gt;

[Empty]

Player 1’s turn: 0 1 2

Not a legal move!!!

Player 1’s turn: 0 {Single} [&#x2666;3]




<strong>Figure 2. Sample output after the current player has selected a list of cards to play. </strong>

The game ends when any of the players has no more cards in his hand. Your program should then print out the number of cards held by each player (see figure 3).

Game ends

Player 0 has 2 cards in hand.

Player 1 has 8 cards in hand. Player 2 wins the game. Player 3 has 5 cards in hand.




<strong>Figure 3. Sample output when the game ends. </strong>

You may refer to the Appendix for an example game play.

<h1>Marking Scheme</h1>

Marks are distributed as follows:

<ul>

 <li>Implementation of the BigTwo class (15%)</li>

 <li>Implementation of the BigTwoCard and BigTwoDeck classes (5% each)</li>

 <li>Implementation of the Hand class and its subclasses (5% each)</li>

 <li>Proper design using OOP approach (20%)</li>

 <li>Javadoc and comments (10%)</li>

</ul>

<h1>Submission</h1>

Please pack the source code (*.java) of your application into a single zip file, and submit it to the course Moodle page.

A few points to note:

<ul>

 <li>Always remember to write Javadoc for all public classes and their public class members.</li>

 <li>Always remember to submit the source code files (<strong>*.java</strong>) but <strong>NOT</strong> the bytecode files (*.class).</li>

 <li>Always double check after your submission to ensure that you have submitted the most up-to-date source code files.</li>

 <li>Your assignment will not be marked if you have only submitted the bytecode files</li>

</ul>

(*.class). You will get zero mark for the assignment.

<ul>

 <li>Please submit your assignment on time. Late submission will not be accepted.</li>

</ul>

~ End ~

<strong>Appendix </strong>

<h2>Example game play</h2>

&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] 12 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] 12 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] 12 [  ]

&lt;Player 3&gt;

==&gt; 0 [&#x2666;3] 1 [&#x2663;4] 2 [&#x2666;6] 3 [&#x2666;7] 4 [&#x2663;7] 5 [&#x2663;8] 6 [&#x2660;8] 7 [&#x2663;9] 8 [&#x2660;9] 9 [&#x2665;Q] 10 [&#x2665;A] 11 [&#x2663;2] 12 [&#x2665;2] &lt;Table&gt;

[Empty]

Player 3’s turn: 0

{Single} [&#x2666;3]




&lt;Player 0&gt;

==&gt; 0 [&#x2665;4] 1 [&#x2666;5] 2 [&#x2663;5] 3 [&#x2665;5] 4 [&#x2660;5] 5 [&#x2660;6] 6 [&#x2666;8] 7 [&#x2660;0] 8 [&#x2663;J] 9 [&#x2666;Q] 10 [&#x2660;Q] 11 [&#x2666;A] 12 [&#x2666;2]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] 12 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] 12 [  ] &lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] &lt;Table&gt;

&lt;Player 3&gt; {Single} [&#x2666;3]

Player 0’s turn: 0

{Single} [&#x2665;4]




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] &lt;Player 1&gt;

==&gt; 0 [&#x2663;3] 1 [&#x2666;4] 2 [&#x2660;4] 3 [&#x2660;7] 4 [&#x2665;8] 5 [&#x2666;9] 6 [&#x2665;9] 7 [&#x2663;0] 8 [&#x2665;0] 9 [&#x2666;J] 10 [&#x2663;Q] 11 [&#x2663;K] 12 [&#x2660;A]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] 12 [  ] &lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] &lt;Table&gt;

&lt;Player 0&gt; {Single} [&#x2665;4]

Player 1’s turn: 3

{Single} [&#x2660;7]




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] &lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] &lt;Player 2&gt;

==&gt; 0 [&#x2665;3] 1 [&#x2660;3] 2 [&#x2663;6] 3 [&#x2665;6] 4 [&#x2665;7] 5 [&#x2666;0] 6 [&#x2665;J] 7 [&#x2660;J] 8 [&#x2666;K] 9 [&#x2665;K] 10 [&#x2660;K] 11 [&#x2663;A] 12 [&#x2660;2] &lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] &lt;Table&gt;

&lt;Player 1&gt; {Single} [&#x2660;7] Player 2’s turn: 0 1

Not a legal move!!!

Player 2’s turn: 5

{Single} [&#x2666;0]




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] &lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] &lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] &lt;Player 3&gt;

==&gt; 0 [&#x2663;4] 1 [&#x2666;6] 2 [&#x2666;7] 3 [&#x2663;7] 4 [&#x2663;8] 5 [&#x2660;8] 6 [&#x2663;9] 7 [&#x2660;9] 8 [&#x2665;Q] 9 [&#x2665;A] 10 [&#x2663;2] 11 [&#x2665;2] &lt;Table&gt;

&lt;Player 2&gt; {Single} [&#x2666;0]

Player 3’s turn: 8

{Single} [&#x2665;Q]




&lt;Player 0&gt;

==&gt; 0 [&#x2666;5] 1 [&#x2663;5] 2 [&#x2665;5] 3 [&#x2660;5] 4 [&#x2660;6] 5 [&#x2666;8] 6 [&#x2660;0] 7 [&#x2663;J] 8 [&#x2666;Q] 9 [&#x2660;Q] 10 [&#x2666;A] 11 [&#x2666;2] &lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ] &lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Table&gt;

&lt;Player 3&gt; {Single} [&#x2665;Q]

Player 0’s turn: 6 Not a legal move!!!

Player 0’s turn: 10

{Single} [&#x2666;A]




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Player 1&gt;

==&gt; 0 [&#x2663;3] 1 [&#x2666;4] 2 [&#x2660;4] 3 [&#x2665;8] 4 [&#x2666;9] 5 [&#x2665;9] 6 [&#x2663;0] 7 [&#x2665;0] 8 [&#x2666;J] 9 [&#x2663;Q] 10 [&#x2663;K] 11 [&#x2660;A] &lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] 11 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Table&gt;

&lt;Player 0&gt; {Single} [&#x2666;A]

Player 1’s turn: 11

{Single} [&#x2660;A]




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] &lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Player 2&gt;

==&gt; 0 [&#x2665;3] 1 [&#x2660;3] 2 [&#x2663;6] 3 [&#x2665;6] 4 [&#x2665;7] 5 [&#x2665;J] 6 [&#x2660;J] 7 [&#x2666;K] 8 [&#x2665;K] 9 [&#x2660;K] 10 [&#x2663;A] 11 [&#x2660;2]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Table&gt;

&lt;Player 1&gt; {Single} [&#x2660;A]

Player 2’s turn: 11

{Single} [&#x2660;2]




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] &lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] &lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] &lt;Player 3&gt;

==&gt; 0 [&#x2663;4] 1 [&#x2666;6] 2 [&#x2666;7] 3 [&#x2663;7] 4 [&#x2663;8] 5 [&#x2660;8] 6 [&#x2663;9] 7 [&#x2660;9] 8 [&#x2665;A] 9 [&#x2663;2] 10 [&#x2665;2] &lt;Table&gt;

&lt;Player 2&gt; {Single} [&#x2660;2] Player 3’s turn:

{Pass}




&lt;Player 0&gt;

==&gt; 0 [&#x2666;5] 1 [&#x2663;5] 2 [&#x2665;5] 3 [&#x2660;5] 4 [&#x2660;6] 5 [&#x2666;8] 6 [&#x2660;0] 7 [&#x2663;J] 8 [&#x2666;Q] 9 [&#x2660;Q] 10 [&#x2666;2] &lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] &lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] &lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Table&gt;

&lt;Player 2&gt; {Single} [&#x2660;2] Player 0’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] &lt;Player 1&gt;

==&gt; 0 [&#x2663;3] 1 [&#x2666;4] 2 [&#x2660;4] 3 [&#x2665;8] 4 [&#x2666;9] 5 [&#x2665;9] 6 [&#x2663;0] 7 [&#x2665;0] 8 [&#x2666;J] 9 [&#x2663;Q] 10 [&#x2663;K] &lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] &lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Table&gt;

&lt;Player 2&gt; {Single} [&#x2660;2] Player 1’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] &lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] &lt;Player 2&gt;

==&gt; 0 [&#x2665;3] 1 [&#x2660;3] 2 [&#x2663;6] 3 [&#x2665;6] 4 [&#x2665;7] 5 [&#x2665;J] 6 [&#x2660;J] 7 [&#x2666;K] 8 [&#x2665;K] 9 [&#x2660;K] 10 [&#x2663;A] &lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Table&gt;

&lt;Player 2&gt; {Single} [&#x2660;2]

Player 2’s turn: 0 1

{Pair} [&#x2665;3] [&#x2660;3]




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] &lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Player 3&gt;

==&gt; 0 [&#x2663;4] 1 [&#x2666;6] 2 [&#x2666;7] 3 [&#x2663;7] 4 [&#x2663;8] 5 [&#x2660;8] 6 [&#x2663;9] 7 [&#x2660;9] 8 [&#x2665;A] 9 [&#x2663;2] 10 [&#x2665;2]

&lt;Table&gt;

&lt;Player 2&gt; {Pair} [&#x2665;3] [&#x2660;3] Player 3’s turn: 1 2

Not a legal move!!!

Player 3’s turn: 2 3

{Pair} [&#x2666;7] [&#x2663;7]




&lt;Player 0&gt;

==&gt; 0 [&#x2666;5] 1 [&#x2663;5] 2 [&#x2665;5] 3 [&#x2660;5] 4 [&#x2660;6] 5 [&#x2666;8] 6 [&#x2660;0] 7 [&#x2663;J] 8 [&#x2666;Q] 9 [&#x2660;Q] 10 [&#x2666;2] &lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Table&gt;

&lt;Player 3&gt; {Pair} [&#x2666;7] [&#x2663;7]

Player 0’s turn: 8 9

{Pair} [&#x2666;Q] [&#x2660;Q]




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] &lt;Player 1&gt;

==&gt; 0 [&#x2663;3] 1 [&#x2666;4] 2 [&#x2660;4] 3 [&#x2665;8] 4 [&#x2666;9] 5 [&#x2665;9] 6 [&#x2663;0] 7 [&#x2665;0] 8 [&#x2666;J] 9 [&#x2663;Q] 10 [&#x2663;K] &lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Table&gt;

&lt;Player 0&gt; {Pair} [&#x2666;Q] [&#x2660;Q] Player 1’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Player 2&gt;

==&gt; 0 [&#x2663;6] 1 [&#x2665;6] 2 [&#x2665;7] 3 [&#x2665;J] 4 [&#x2660;J] 5 [&#x2666;K] 6 [&#x2665;K] 7 [&#x2660;K] 8 [&#x2663;A]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] &lt;Table&gt;

&lt;Player 0&gt; {Pair} [&#x2666;Q] [&#x2660;Q] Player 2’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Player 3&gt;

==&gt; 0 [&#x2663;4] 1 [&#x2666;6] 2 [&#x2663;8] 3 [&#x2660;8] 4 [&#x2663;9] 5 [&#x2660;9] 6 [&#x2665;A] 7 [&#x2663;2] 8 [&#x2665;2]

&lt;Table&gt;

&lt;Player 0&gt; {Pair} [&#x2666;Q] [&#x2660;Q] Player 3’s turn:

{Pass}




&lt;Player 0&gt;

==&gt; 0 [&#x2666;5] 1 [&#x2663;5] 2 [&#x2665;5] 3 [&#x2660;5] 4 [&#x2660;6] 5 [&#x2666;8] 6 [&#x2660;0] 7 [&#x2663;J] 8 [&#x2666;2]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Table&gt;

&lt;Player 0&gt; {Pair} [&#x2666;Q] [&#x2660;Q] Player 0’s turn: 0 1 2 3 4

{Quad} [&#x2666;5] [&#x2663;5] [&#x2665;5] [&#x2660;5] [&#x2660;6]




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ]

&lt;Player 1&gt;

==&gt; 0 [&#x2663;3] 1 [&#x2666;4] 2 [&#x2660;4] 3 [&#x2665;8] 4 [&#x2666;9] 5 [&#x2665;9] 6 [&#x2663;0] 7 [&#x2665;0] 8 [&#x2666;J] 9 [&#x2663;Q] 10 [&#x2663;K]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Table&gt;

&lt;Player 0&gt; {Quad} [&#x2666;5] [&#x2663;5] [&#x2665;5] [&#x2660;5] [&#x2660;6] Player 1’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Player 2&gt;

==&gt; 0 [&#x2663;6] 1 [&#x2665;6] 2 [&#x2665;7] 3 [&#x2665;J] 4 [&#x2660;J] 5 [&#x2666;K] 6 [&#x2665;K] 7 [&#x2660;K] 8 [&#x2663;A]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Table&gt;

&lt;Player 0&gt; {Quad} [&#x2666;5] [&#x2663;5] [&#x2665;5] [&#x2660;5] [&#x2660;6] Player 2’s turn: 5 6 7 0 1 Not a legal move!!!

Player 2’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ] &lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Player 3&gt;

==&gt; 0 [&#x2663;4] 1 [&#x2666;6] 2 [&#x2663;8] 3 [&#x2660;8] 4 [&#x2663;9] 5 [&#x2660;9] 6 [&#x2665;A] 7 [&#x2663;2] 8 [&#x2665;2]

&lt;Table&gt;

&lt;Player 0&gt; {Quad} [&#x2666;5] [&#x2663;5] [&#x2665;5] [&#x2660;5] [&#x2660;6] Player 3’s turn:

{Pass}




&lt;Player 0&gt;

==&gt; 0 [&#x2666;8] 1 [&#x2660;0] 2 [&#x2663;J] 3 [&#x2666;2]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] 10 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Table&gt;

&lt;Player 0&gt; {Quad} [&#x2666;5] [&#x2663;5] [&#x2665;5] [&#x2660;5] [&#x2660;6]

Player 0’s turn: 0

{Single} [&#x2666;8]




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ]

&lt;Player 1&gt;

==&gt; 0 [&#x2663;3] 1 [&#x2666;4] 2 [&#x2660;4] 3 [&#x2665;8] 4 [&#x2666;9] 5 [&#x2665;9] 6 [&#x2663;0] 7 [&#x2665;0] 8 [&#x2666;J] 9 [&#x2663;Q] 10 [&#x2663;K]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Table&gt;

&lt;Player 0&gt; {Single} [&#x2666;8]

Player 1’s turn: 3

{Single} [&#x2665;8]




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ]

&lt;Player 2&gt;

==&gt; 0 [&#x2663;6] 1 [&#x2665;6] 2 [&#x2665;7] 3 [&#x2665;J] 4 [&#x2660;J] 5 [&#x2666;K] 6 [&#x2665;K] 7 [&#x2660;K] 8 [&#x2663;A]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ]

&lt;Table&gt;

&lt;Player 1&gt; {Single} [&#x2665;8]

Player 2’s turn: 8

{Single} [&#x2663;A]




&lt;Player 0&gt;

0 [  ] 1 [  ] 2 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ]

&lt;Player 3&gt;

==&gt; 0 [&#x2663;4] 1 [&#x2666;6] 2 [&#x2663;8] 3 [&#x2660;8] 4 [&#x2663;9] 5 [&#x2660;9] 6 [&#x2665;A] 7 [&#x2663;2] 8 [&#x2665;2]

&lt;Table&gt;

&lt;Player 2&gt; {Single} [&#x2663;A]

Player 3’s turn: 6

{Single} [&#x2665;A]




&lt;Player 0&gt;

==&gt; 0 [&#x2660;0] 1 [&#x2663;J] 2 [&#x2666;2]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] &lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] &lt;Table&gt;

&lt;Player 3&gt; {Single} [&#x2665;A]

Player 0’s turn: 2

{Single} [&#x2666;2]




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

==&gt; 0 [&#x2663;3] 1 [&#x2666;4] 2 [&#x2660;4] 3 [&#x2666;9] 4 [&#x2665;9] 5 [&#x2663;0] 6 [&#x2665;0] 7 [&#x2666;J] 8 [&#x2663;Q] 9 [&#x2663;K]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] &lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] &lt;Table&gt;

&lt;Player 0&gt; {Single} [&#x2666;2] Player 1’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ]

&lt;Player 2&gt;

==&gt; 0 [&#x2663;6] 1 [&#x2665;6] 2 [&#x2665;7] 3 [&#x2665;J] 4 [&#x2660;J] 5 [&#x2666;K] 6 [&#x2665;K] 7 [&#x2660;K] &lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ]

&lt;Table&gt;

&lt;Player 0&gt; {Single} [&#x2666;2] Player 2’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] &lt;Player 3&gt;

==&gt; 0 [&#x2663;4] 1 [&#x2666;6] 2 [&#x2663;8] 3 [&#x2660;8] 4 [&#x2663;9] 5 [&#x2660;9] 6 [&#x2663;2] 7 [&#x2665;2]

&lt;Table&gt;

&lt;Player 0&gt; {Single} [&#x2666;2]

Player 3’s turn: 6

{Single} [&#x2663;2]




&lt;Player 0&gt;

==&gt; 0 [&#x2660;0] 1 [&#x2663;J]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ]

&lt;Table&gt;

&lt;Player 3&gt; {Single} [&#x2663;2] Player 0’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

==&gt; 0 [&#x2663;3] 1 [&#x2666;4] 2 [&#x2660;4] 3 [&#x2666;9] 4 [&#x2665;9] 5 [&#x2663;0] 6 [&#x2665;0] 7 [&#x2666;J] 8 [&#x2663;Q] 9 [&#x2663;K]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ]

&lt;Table&gt;

&lt;Player 3&gt; {Single} [&#x2663;2] Player 1’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] &lt;Player 2&gt;

==&gt; 0 [&#x2663;6] 1 [&#x2665;6] 2 [&#x2665;7] 3 [&#x2665;J] 4 [&#x2660;J] 5 [&#x2666;K] 6 [&#x2665;K] 7 [&#x2660;K]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ]

&lt;Table&gt;

&lt;Player 3&gt; {Single} [&#x2663;2] Player 2’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ] &lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ]

&lt;Player 3&gt;

==&gt; 0 [&#x2663;4] 1 [&#x2666;6] 2 [&#x2663;8] 3 [&#x2660;8] 4 [&#x2663;9] 5 [&#x2660;9] 6 [&#x2665;2]

&lt;Table&gt;

&lt;Player 3&gt; {Single} [&#x2663;2]

Player 3’s turn: 2 3

{Pair} [&#x2663;8] [&#x2660;8]




&lt;Player 0&gt;

==&gt; 0 [&#x2660;0] 1 [&#x2663;J]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] 8 [  ] 9 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ]

&lt;Table&gt;

&lt;Player 3&gt; {Pair} [&#x2663;8] [&#x2660;8] Player 0’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

==&gt; 0 [&#x2663;3] 1 [&#x2666;4] 2 [&#x2660;4] 3 [&#x2666;9] 4 [&#x2665;9] 5 [&#x2663;0] 6 [&#x2665;0] 7 [&#x2666;J] 8 [&#x2663;Q] 9 [&#x2663;K]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ]

&lt;Table&gt;

&lt;Player 3&gt; {Pair} [&#x2663;8] [&#x2660;8]

Player 1’s turn: 3 4

{Pair} [&#x2666;9] [&#x2665;9]




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ] &lt;Player 2&gt;

==&gt; 0 [&#x2663;6] 1 [&#x2665;6] 2 [&#x2665;7] 3 [&#x2665;J] 4 [&#x2660;J] 5 [&#x2666;K] 6 [&#x2665;K] 7 [&#x2660;K]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ]

&lt;Table&gt;

&lt;Player 1&gt; {Pair} [&#x2666;9] [&#x2665;9]

Player 2’s turn: 3 4

{Pair} [&#x2665;J] [&#x2660;J]




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ]

&lt;Player 3&gt;

==&gt; 0 [&#x2663;4] 1 [&#x2666;6] 2 [&#x2663;9] 3 [&#x2660;9] 4 [&#x2665;2]

&lt;Table&gt;

&lt;Player 2&gt; {Pair} [&#x2665;J] [&#x2660;J] Player 3’s turn:

{Pass}




&lt;Player 0&gt;

==&gt; 0 [&#x2660;0] 1 [&#x2663;J]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ]

&lt;Table&gt;

&lt;Player 2&gt; {Pair} [&#x2665;J] [&#x2660;J] Player 0’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

==&gt; 0 [&#x2663;3] 1 [&#x2666;4] 2 [&#x2660;4] 3 [&#x2663;0] 4 [&#x2665;0] 5 [&#x2666;J] 6 [&#x2663;Q] 7 [&#x2663;K]

&lt;Player 2&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ]

&lt;Table&gt;

&lt;Player 2&gt; {Pair} [&#x2665;J] [&#x2660;J]

Player 1’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ]

&lt;Player 2&gt;

==&gt; 0 [&#x2663;6] 1 [&#x2665;6] 2 [&#x2665;7] 3 [&#x2666;K] 4 [&#x2665;K] 5 [&#x2660;K]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ]

&lt;Table&gt;

&lt;Player 2&gt; {Pair} [&#x2665;J] [&#x2660;J] Player 2’s turn:

Not a legal move!!!

Player 2’s turn: 0 1 3 5 4

{FullHouse} [&#x2663;6] [&#x2665;6] [&#x2666;K] [&#x2665;K] [&#x2660;K]




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ]

&lt;Player 2&gt;

0 [  ]

&lt;Player 3&gt;

==&gt; 0 [&#x2663;4] 1 [&#x2666;6] 2 [&#x2663;9] 3 [&#x2660;9] 4 [&#x2665;2]

&lt;Table&gt;

&lt;Player 2&gt; {FullHouse} [&#x2663;6] [&#x2665;6] [&#x2666;K] [&#x2665;K] [&#x2660;K] Player 3’s turn:

{Pass}




&lt;Player 0&gt;

==&gt; 0 [&#x2660;0] 1 [&#x2663;J]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ]

&lt;Player 2&gt;

0 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ]

&lt;Table&gt;

&lt;Player 2&gt; {FullHouse} [&#x2663;6] [&#x2665;6] [&#x2666;K] [&#x2665;K] [&#x2660;K] Player 0’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

==&gt; 0 [&#x2663;3] 1 [&#x2666;4] 2 [&#x2660;4] 3 [&#x2663;0] 4 [&#x2665;0] 5 [&#x2666;J] 6 [&#x2663;Q] 7 [&#x2663;K]

&lt;Player 2&gt;

0 [  ]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ]

&lt;Table&gt;

&lt;Player 2&gt; {FullHouse} [&#x2663;6] [&#x2665;6] [&#x2666;K] [&#x2665;K] [&#x2660;K] Player 1’s turn:

{Pass}




&lt;Player 0&gt;

0 [  ] 1 [  ]

&lt;Player 1&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ] 5 [  ] 6 [  ] 7 [  ]

&lt;Player 2&gt;

==&gt; 0 [&#x2665;7]

&lt;Player 3&gt;

0 [  ] 1 [  ] 2 [  ] 3 [  ] 4 [  ]

&lt;Table&gt;

&lt;Player 2&gt; {FullHouse} [&#x2663;6] [&#x2665;6] [&#x2666;K] [&#x2665;K] [&#x2660;K]

Player 2’s turn: 0

{Single} [&#x2665;7]




&lt;Player 0&gt;

0 [&#x2660;0] 1 [&#x2663;J]

&lt;Player 1&gt;

0 [&#x2663;3] 1 [&#x2666;4] 2 [&#x2660;4] 3 [&#x2663;0] 4 [&#x2665;0] 5 [&#x2666;J] 6 [&#x2663;Q] 7 [&#x2663;K] &lt;Player 2&gt;

[Empty]

&lt;Player 3&gt;

0 [&#x2663;4] 1 [&#x2666;6] 2 [&#x2663;9] 3 [&#x2660;9] 4 [&#x2665;2]

&lt;Table&gt;

&lt;Player 2&gt; {Single} [&#x2665;7]




Game ends

Player 0 has 2 cards in hand.

Player 1 has 8 cards in hand. Player 2 wins the game.

Player 3 has 5 cards in hand.


