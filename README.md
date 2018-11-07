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

## installing packages
`mix deps.get`

    akira:elixir-cards rus$ mix deps.get
    Could not find Hex, which is needed to build dependency :ex_doc
    Shall I install Hex? (if running non-interactively, use "mix local.hex --force") [Yn] y
    * creating /Users/rus/.mix/archives/hex-0.18.1
    Resolving Hex dependencies...
    Dependency resolution completed:
    New:
      earmark 1.2.6
      ex_doc 0.19.1
      makeup 0.5.5
      makeup_elixir 0.10.0
      nimble_parsec 0.4.0
    * Getting ex_doc (Hex package)
    * Getting earmark (Hex package)
    * Getting makeup_elixir (Hex package)
    * Getting makeup (Hex package)
    * Getting nimble_parsec (Hex package)

## generate docs
`mix docs`

## run tests
`mix tests`

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

## maps

    {primary: "red", secondary: "blue"}
    iex(2)> colors
    %{primary: "red", secondary: "blue"}
    iex(3)> colors.primary
    "red"
    iex(4)> colors.secondary
    "blue"
    iex(5)> sec_col = colors.secondary
    "blue"
    iex(6)> sec_col
    "blue"
    iex(7)> %{secondary: sec_color} = colors
    %{primary: "red", secondary: "blue"}
    iex(8)> sec_color
    "blue"
    iex(9)> colors.red = "orange"
    ** (CompileError) iex:9: cannot invoke remote function colors.red/0 inside match
    iex(9)> Map.put(colors, :primary, "orange")
    %{primary: "orange", secondary: "blue"}
    iex(10)> colors
    %{primary: "red", secondary: "blue"}
    iex(11)> %{ colors | primary: "orange" }
    %{primary: "orange", secondary: "blue"}
    iex(12)> $: colors | thirdary: "green" }
    ** (SyntaxError) iex:12: unexpected token: "$" (column 1, codepoint U+0024)
    iex(12)> Map.put(colors, :thirdary, "green")
    %{primary: "red", secondary: "blue", thirdary: "green"}

    # lists
    iex(1)> colors = [{:primary, "red"}, {:secondary, "green"}]
    [primary: "red", secondary: "green"]
    iex(2)> colors[:primary]
    "red"
    iex(3)> colors[:secondary]
    "green"
