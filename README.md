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
