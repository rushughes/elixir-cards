# Cards

Elixir tutorial from <https://www.udemy.com/the-complete-elixir-and-phoenix-bootcamp-and-tutorial/learn/v4/t/lecture/5427954?start=0>

## compile project and make it available in a shell
`iex -S mix`

    akira:elixir-cards rus$ iex -S mix
    Erlang/OTP 21 [erts-10.1.1] [source] [64-bit] [smp:8:8] [ds:8:8:10] [async-threads:1] [hipe] [dtrace]

    Compiling 1 file (.ex)
    Generated cards app
    Interactive Elixir (1.7.4) - press Ctrl+C to exit (type h() ENTER for help)
    iex(1)> Cards
    Cards
    iex(2)> Cards.hello
    "hello world!"
    iex(3)>

## compile project in the shell
`compile`

## examples
    iex(11)> deck = Cards.create_deck
    ["Ace", "Two", "Three"]
    iex(12)> deck2 = Cards.shuffle(deck)
    ["Ace", "Three", "Two"]
    iex(13)> deck2
    ["Ace", "Three", "Two"]
    iex(14)> deck
    ["Ace", "Two", "Three"]


    iex(1)> deck = Cards.create_deck
    ["Ace", "Two", "Three"]
    iex(2)> Cards.contains?(deck, "King")
    false

    iex(40)> {hand, deck} = Cards.deal(deck, 20)
    {["Four of Diamonds", "Three of Diamonds", "Ace of Spades", "Two of Diamonds",
      "Jack of Diamonds", "Jack of Hearts", "Seven of Clubs", "King of Clubs",
      "Three of Hearts", "King of Hearts", "Two of Clubs", "Nine of Spades",
      "Eight of Diamonds", "Six of Hearts", "Queen of Diamonds", "Five of Spades",
      "Seven of Hearts", "Six of Spades", "Seven of Spades", "Five of Diamonds"],
     ["Eight of Clubs", "Three of Clubs", "Nine of Diamonds", "Nine of Hearts",
      "King of Spades", "Three of Spades", "Ace of Hearts", "Ace of Clubs",
      "Two of Spades", "Queen of Spades", "Two of Hearts", "Nine of Clubs",
      "Jack of Spades", "Jack of Clubs", "Four of Hearts", "Queen of Clubs",
      "Ten of Hearts", "Ten of Clubs", "King of Diamonds", "Ten of Spades",
      "Four of Spades", "Eight of Spades", "Ten of Diamonds", "Seven of Diamonds",
      "Ace of Diamonds", "Six of Clubs", "Queen of Hearts", "Six of Diamonds",
      "Five of Clubs", "Eight of Hearts", "Four of Clubs", "Five of Hearts"]}
    iex(41)> hand
    ["Four of Diamonds", "Three of Diamonds", "Ace of Spades", "Two of Diamonds",
     "Jack of Diamonds", "Jack of Hearts", "Seven of Clubs", "King of Clubs",
     "Three of Hearts", "King of Hearts", "Two of Clubs", "Nine of Spades",
     "Eight of Diamonds", "Six of Hearts", "Queen of Diamonds", "Five of Spades",
     "Seven of Hearts", "Six of Spades", "Seven of Spades", "Five of Diamonds"]
    iex(42)> deck
    ["Eight of Clubs", "Three of Clubs", "Nine of Diamonds", "Nine of Hearts",
     "King of Spades", "Three of Spades", "Ace of Hearts", "Ace of Clubs",
     "Two of Spades", "Queen of Spades", "Two of Hearts", "Nine of Clubs",
     "Jack of Spades", "Jack of Clubs", "Four of Hearts", "Queen of Clubs",
     "Ten of Hearts", "Ten of Clubs", "King of Diamonds", "Ten of Spades",
     "Four of Spades", "Eight of Spades", "Ten of Diamonds", "Seven of Diamonds",
     "Ace of Diamonds", "Six of Clubs", "Queen of Hearts", "Six of Diamonds",
     "Five of Clubs", "Eight of Hearts", "Four of Clubs", "Five of Hearts"]
    iex(43)>

    iex(2)> deck = Cards.create_deck
["Ace of Spades", "Two of Spades", "Three of Spades", "Four of Spades",
 "Five of Spades", "Six of Spades", "Seven of Spades", "Eight of Spades",
 "Nine of Spades", "Ten of Spades", "Jack of Spades", "Queen of Spades",
 "King of Spades", "Ace of Clubs", "Two of Clubs", "Three of Clubs",
 "Four of Clubs", "Five of Clubs", "Six of Clubs", "Seven of Clubs",
 "Eight of Clubs", "Nine of Clubs", "Ten of Clubs", "Jack of Clubs",
 "Queen of Clubs", "King of Clubs", "Ace of Hearts", "Two of Hearts",
 "Three of Hearts", "Four of Hearts", "Five of Hearts", "Six of Hearts",
 "Seven of Hearts", "Eight of Hearts", "Nine of Hearts", "Ten of Hearts",
 "Jack of Hearts", "Queen of Hearts", "King of Hearts", "Ace of Diamonds",
 "Two of Diamonds", "Three of Diamonds", "Four of Diamonds", "Five of Diamonds",
 "Six of Diamonds", "Seven of Diamonds", "Eight of Diamonds",
 "Nine of Diamonds", "Ten of Diamonds", "Jack of Diamonds", ...]
iex(3)> deck = Cards.shuffle(deck)
["Ace of Hearts", "Four of Hearts", "Queen of Diamonds", "King of Spades",
 "Two of Hearts", "King of Hearts", "Ten of Diamonds", "Ace of Diamonds",
 "Jack of Clubs", "Five of Clubs", "Ace of Clubs", "Eight of Spades",
 "Six of Diamonds", "Jack of Spades", "Four of Diamonds", "Three of Clubs",
 "Ace of Spades", "Eight of Hearts", "Six of Clubs", "Nine of Clubs",
 "Four of Spades", "Seven of Diamonds", "King of Diamonds", "Queen of Clubs",
 "Three of Spades", "Ten of Clubs", "Six of Hearts", "Two of Spades",
 "Four of Clubs", "Ten of Spades", "Two of Diamonds", "Queen of Spades",
 "Jack of Hearts", "Jack of Diamonds", "Ten of Hearts", "Seven of Spades",
 "Eight of Clubs", "Three of Hearts", "Two of Clubs", "Three of Diamonds",
 "King of Clubs", "Nine of Diamonds", "Six of Spades", "Queen of Hearts",
 "Five of Spades", "Seven of Clubs", "Nine of Hearts", "Eight of Diamonds",
 "Five of Hearts", "Seven of Hearts", ...]
iex(4)> Cards.save(deck, "deck.cards")
:ok
iex(5)> deck2 = Cards.load("deck.cards")
["Ace of Hearts", "Four of Hearts", "Queen of Diamonds", "King of Spades",
 "Two of Hearts", "King of Hearts", "Ten of Diamonds", "Ace of Diamonds",
 "Jack of Clubs", "Five of Clubs", "Ace of Clubs", "Eight of Spades",
 "Six of Diamonds", "Jack of Spades", "Four of Diamonds", "Three of Clubs",
 "Ace of Spades", "Eight of Hearts", "Six of Clubs", "Nine of Clubs",
 "Four of Spades", "Seven of Diamonds", "King of Diamonds", "Queen of Clubs",
 "Three of Spades", "Ten of Clubs", "Six of Hearts", "Two of Spades",
 "Four of Clubs", "Ten of Spades", "Two of Diamonds", "Queen of Spades",
 "Jack of Hearts", "Jack of Diamonds", "Ten of Hearts", "Seven of Spades",
 "Eight of Clubs", "Three of Hearts", "Two of Clubs", "Three of Diamonds",
 "King of Clubs", "Nine of Diamonds", "Six of Spades", "Queen of Hearts",
 "Five of Spades", "Seven of Clubs", "Nine of Hearts", "Eight of Diamonds",
 "Five of Hearts", "Seven of Hearts", ...]
iex(6)> deck
["Ace of Hearts", "Four of Hearts", "Queen of Diamonds", "King of Spades",
 "Two of Hearts", "King of Hearts", "Ten of Diamonds", "Ace of Diamonds",
 "Jack of Clubs", "Five of Clubs", "Ace of Clubs", "Eight of Spades",
 "Six of Diamonds", "Jack of Spades", "Four of Diamonds", "Three of Clubs",
 "Ace of Spades", "Eight of Hearts", "Six of Clubs", "Nine of Clubs",
 "Four of Spades", "Seven of Diamonds", "King of Diamonds", "Queen of Clubs",
 "Three of Spades", "Ten of Clubs", "Six of Hearts", "Two of Spades",
 "Four of Clubs", "Ten of Spades", "Two of Diamonds", "Queen of Spades",
 "Jack of Hearts", "Jack of Diamonds", "Ten of Hearts", "Seven of Spades",
 "Eight of Clubs", "Three of Hearts", "Two of Clubs", "Three of Diamonds",
 "King of Clubs", "Nine of Diamonds", "Six of Spades", "Queen of Hearts",
 "Five of Spades", "Seven of Clubs", "Nine of Hearts", "Eight of Diamonds",
 "Five of Hearts", "Seven of Hearts", ...]
iex(7)> deck2
["Ace of Hearts", "Four of Hearts", "Queen of Diamonds", "King of Spades",
 "Two of Hearts", "King of Hearts", "Ten of Diamonds", "Ace of Diamonds",
 "Jack of Clubs", "Five of Clubs", "Ace of Clubs", "Eight of Spades",
 "Six of Diamonds", "Jack of Spades", "Four of Diamonds", "Three of Clubs",
 "Ace of Spades", "Eight of Hearts", "Six of Clubs", "Nine of Clubs",
 "Four of Spades", "Seven of Diamonds", "King of Diamonds", "Queen of Clubs",
 "Three of Spades", "Ten of Clubs", "Six of Hearts", "Two of Spades",
 "Four of Clubs", "Ten of Spades", "Two of Diamonds", "Queen of Spades",
 "Jack of Hearts", "Jack of Diamonds", "Ten of Hearts", "Seven of Spades",
 "Eight of Clubs", "Three of Hearts", "Two of Clubs", "Three of Diamonds",
 "King of Clubs", "Nine of Diamonds", "Six of Spades", "Queen of Hearts",
 "Five of Spades", "Seven of Clubs", "Nine of Hearts", "Eight of Diamonds",
 "Five of Hearts", "Seven of Hearts", ...]
iex(8)>
