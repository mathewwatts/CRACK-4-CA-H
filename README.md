
CRACK4CA$H 
![heading](docs/crack4cash.png)
# Ruby Based Terminal App
---

## Must download the folling Ruby GEMS:
![brainstorm one](docs/ruby_gems.png)
Download/install colorize:

[colorize link](https://rubygems.org/gems/colorize/versions/0.8.1)

Download/install Whirly:

[Whirly link](https://rubygems.org/gems/whirly)

Download/install paint:

[paint link](https://rubygems.org/gems/paint)


---
### PURPOSE:

CRACK4CA$H is a hidden phrase guessing game, based on 'Hangman' and 'Wheel Of Fortune'. 

---

### HOW TO PLAY 

### NOTE : Must have an audio output source to run.

Players have to reveal the hidden phrase by guessing the letters one at a time. If a letter appears more than once in a phrase, each guess will only reveal ONE instance of that letter. In the following example: 

‘H E L L O   W O R L D’,  the player would have to call ‘l’ three times.

Players commence the game with: $1000 prize money. Each correct guess increases their bank by $50, an incorrect guess results in a deduction of $200, plus – verbal abuse. 

Players win the game and a subsequent prize if they solve the puzzle with money still in their bank. They may continue to guess providing they still have money in their bank. If players run out of money before solving the puzzle they are considered ‘nil’ and must ‘step off’ (eliminated).  

--- 

### INSTRUCTIONS 

The game requires the keys [a -z] and the [enter] key, players can leave the game anytime by pressing [control "c"]. 

The game is intuitive and prompts players in regards to what they need to do start game. 

---

# App idea brainstorming sessions 
![brainstorm one](docs/IMG_4121.jpeg)
![brainstorm two](docs/IMG_4122.jpeg)
![brainstorm three](docs/IMG_4123.jpeg)
![brainstorm four](docs/IMG_4124.jpeg)
![brainstorm five](docs/IMG_4125.jpeg)
![brainstorm six](docs/IMG_4127.jpeg)


# Screenshots 
Begin Game

![screenshot 1](docs/begin_game.png)

Select Player Amount
![screenshot 4](docs/select_amount_players.png)

Select Name

![screenshot 5](docs/select_name.png)

Incorrect Guess

![screenshot 2](docs/incorrect_guess.png)

Lose Game

![screenshot 3](docs/lose_the_game.png)

Win Game

![screenshot 6](docs/win_game.png)


## Complete Source code
```ruby
require 'colorize'
require 'Whirly'
require 'paint'

print """=====================================
             CRACK4CA$H
=====================================
""".colorize(:green)
%x( say 'Welcome too CRACK 4 CASH' )
class Player  
    attr_accessor(:name, :current_bank)
    def initialize(name, player_number)   
      @name = name
      @player_number = 0
      @current_bank = 1000
    end  

    def prize
        if current_bank > 1000
            return "LIQUID LAMINGTON!"
        end
        if current_bank == 1000
            return "DATE WITH RUEGEN!"
        end
        if current_bank == 950
            return "DATE WITH RUEGEN!"
        end
        if current_bank == 900
            return "DATE WITH RUEGEN!"
        end
        if current_bank == 850
            return "SLAB OF VB!"
        end
        if current_bank == 800
            return "SLAB OF VB!"
        end
        if current_bank == 750
            return "SLAB OF VB!"
        end
        if current_bank == 700
            return "FREE UBER RIDE!"
        end
        if current_bank == 650
            return "FREE UBER RIDE!"
        end
        if current_bank == 600
            return "FREE UBER RIDE!"
        end
        if current_bank == 550
            return "24 PACK OF DONUTS!"
        end
        if current_bank == 500
            return "24 PACK OF DONUTS!"
        end
        if current_bank == 450
            return "BAKED BEANS!"
        end
        if current_bank == 400
            return "BAKED BEANS!"
        end
        if @current_bank < 400
            return "USED SOCK!"
        end
    end
end  
print """1. One Player
1. Two Player
2. Three Player
3. Four Player
Input the number players : """
%x( say 'Please input the number of players' )
player_amount = gets.chomp.to_i
system('clear')
print """=====================================
             CRACK4CA$H
=====================================
""".colorize(:green)
if player_amount == 1
    puts "You selected 'One Player'"
    %x( say 'You selected One Player' )
    print "Player 1 input your name : "
    %x( say 'Player 1 please input your name' )
    player_one_name = gets.chomp.capitalize
    %x( say "gooood luck today #{player_one_name}" )
    player_one = Player.new(player_one_name, 0)
    player_one_length = player_one_name.length
    player_one_space = " " * (18 - player_one_length)
    system('clear')
    print """=====================================
             CRACK4CA$H
=====================================
""".colorize(:green)
    puts """    Player:             Winnings:
-------------------------------------
    #{player_one_name} #{player_one_space} $ #{player_one.current_bank}
-------------------------------------"""
%x( say '#{player_one_name} you start with one thousand dollars' )
%x( say 'for every incorrect guess you lose two hundred dollars' )
%x( say 'but for every correct guess you win fifty dollars' )
%x( say 'let us begin' )
end
if player_amount == 2
    puts "You selected 'Two Player'"
    %x( say 'You selected Two Player' )
    print "Player 1 input your name : "
    %x( say 'Player one please input your name' )
    player_one_name = gets.chomp.capitalize
    player_one = Player.new(player_one_name, 0)
    print "Player 2 input your name : "
    %x( say 'and Player two please input your name' )
    player_two_name = gets.chomp.capitalize
    player_two = Player.new(player_two_name, 1)
    player_one_length = player_one_name.length
    player_two_length = player_two_name.length
    player_one_space = " " * (18 - player_one_length)
    player_two_space = " " * (18 - player_two_length)
    # system('clear')
    print """=====================================
             CRACK4CA$H
=====================================
""".colorize(:green)
puts "=====================================".colorize(:yellow)
puts """    Player:             Winnings:
-------------------------------------
    #{player_one_name} #{player_one_space} $ #{player_one.current_bank}
    #{player_two_name} #{player_two_space} $ #{player_two.current_bank}
-------------------------------------"""
    puts "===================================".colorize(:yellow)
end
if player_amount == 3
    puts "You selected 'Three Player'"
    %x( say 'You selected Three Player' )
    print "Player 1 input your name : "
    %x( say 'Player one please input your name' )
    player_one_name = gets.chomp.capitalize
    player_one = Player.new(player_one_name, 0)
    print "Player 2 input your name : "
    %x( say 'Player two please input your name' )
    player_two_name = gets.chomp.capitalize
    player_two = Player.new(player_two_name, 1)
    print "Player 3 input your name : "
    %x( say 'and Player three please input your name' )
    player_three_name = gets.chomp.capitalize
    player_three = Player.new(player_three_name, 2)
    player_one_length = player_one_name.length
    player_two_length = player_two_name.length
    player_three_length = player_three_name.length
    player_one_space = " " * (18 - player_one_length)
    player_two_space = " " * (18 - player_two_length)
    player_three_space = " " * (18 - player_three_length)
    # system('clear')
    print """=====================================
             CRACK4CA$H
=====================================
""".colorize(:green)
puts "=====================================".colorize(:yellow)
puts """    Player:             Winnings:
-------------------------------------
    #{player_one_name} #{player_one_space} $ #{player_one.current_bank}
    #{player_two_name} #{player_two_space} $ #{player_two.current_bank}
    #{player_three_name} #{player_three_space} $ #{player_three.current_bank}
-------------------------------------"""
puts "===================================".colorize(:yellow)
end
if player_amount == 4
    puts "You selected 'Four Player'"
    %x( say 'You selected Four Player' )
    print "Player 1 input your name : "
    %x( say 'Player one please input your name' )
    player_one_name = gets.chomp.capitalize
    player_one = Player.new(player_one_name, 0)
    print "Player 2 input your name : "
    %x( say 'Player two please input your name' )
    player_two_name = gets.chomp.capitalize
    player_two = Player.new(player_two_name, 1)
    print "Player 3 input your name : "
    %x( say 'Player three please input your name' )
    player_three_name = gets.chomp.capitalize
    player_three = Player.new(player_three_name, 2)
    print "Player 4 input your name : "
    %x( say 'and Player four please input your name' )
    player_four_name = gets.chomp.capitalize
    player_four = Player.new(player_four_name, 3)
    player_one_length = player_one_name.length
    player_two_length = player_two_name.length
    player_three_length = player_three_name.length
    player_four_length = player_four_name.length
    player_one_space = " " * (18 - player_one_length)
    player_two_space = " " * (18 - player_two_length)
    player_three_space = " " * (18 - player_three_length)
    player_four_space = " " * (18 - player_four_length)
    # system('clear')
    print """=====================================
             CRACK4CA$H
=====================================
""".colorize(:green)
puts "=====================================".colorize(:yellow)
puts """    Player:             Winnings:
-------------------------------------
    #{player_one_name} #{player_one_space} $ #{player_one.current_bank}
    #{player_two_name} #{player_two_space} $ #{player_two.current_bank}
    #{player_three_name} #{player_three_space} $ #{player_three.current_bank}
    #{player_four_name} #{player_four_space} $ #{player_four.current_bank}
-------------------------------------"""
puts "=====================================".colorize(:yellow)
end
phrase_list = [ 
    "crack a tinnie",
    "Every cloud has a silver lining",
    "Bite the bullet",
    "It's not rocket science",
    "No pain, no gain",
    "The best of both worlds",
    "A penny for your thoughts",
    "By the skin of your teeth",
    "Don't cry over spilt milk",
    "Go on a wild goose chase",
    "It's raining cats and dogs",
    "Let the cat out of the bag",
    "Play devil's advocate",
    "Throw caution to the wind",
    "Calm before the storm",
    "Go down in flames",
    "maccas run"
]

starting_phrase = phrase_list.sample(1)
random_phrase = starting_phrase.to_s.delete '["\]'
phrase_array = random_phrase.split("").map(&:downcase)
phrase_count = phrase_array - [" "]
final_phrase = random_phrase.gsub(/[a-zA-z]/, "$").split("")
ph_arr_count = phrase_array.count("")
ph_count_count = phrase_count.count



while player_one.current_bank >= 50 
    system('clear')
    print """=====================================
             CRACK4CA$H
=====================================
""".colorize(:green)
    puts """    Player:             Winnings:
-------------------------------------
    #{player_one_name} #{player_one_space} $ #{player_one.current_bank}
-------------------------------------"""
    if phrase_array.count("") == phrase_count.count
        puts """-------------------------------------""".colorize(:magenta)
puts"""YOU GUESSED THE PHRASE :
#{final_phrase.join}""".colorize(:green)
puts "-------------------------------------".colorize(:magenta)
        puts "You have a total of $#{player_one.current_bank}"
        %x( say "O M GEE #{player_one_name} you actually guessed the phrase" )
        sleep 0.2
        %x( say "your prize is about to be revealed" )
        Whirly.start spinner: "arrow3", color: true, status: "REVEALING PRIZE!!!".colorize(:magenta) do
            sleep 5
          end
        puts """
YOU HAVE WON A...
"""
        sleep 2
        puts"""
        #{player_one.prize.upcase}!

        """.colorize(:magenta)
        %x( say "What a great prize" )
        sleep 0.5
        %x( say "dot dot dot" )
        sleep 3
        %x( say "please leave now" )
        puts """HOPE YOU ENJOYED THE GAME! BYE!!!
""".colorize(:green)
        sleep 2
        puts "Fin."
        sleep 3
        break
    end
        puts """-------------------------------------
THE PHRASE IS : 
#{final_phrase.join}
-------------------------------------""".colorize(:yellow)
        print "Pick a letter : "
        guess = gets.downcase.chomp
    if !phrase_array.include?(guess)
        puts "THAT GUESS WAS INCORRECT! YOU LOSE $200".colorize(:red)
        %x( say 'HAR HAR THAT WAS A BAD GUESS' )
        sleep 0.2
        player_one.current_bank -= 200

    else 
        letter_index = phrase_array.find_index(guess)
        phrase_array[letter_index] = ""
        final_phrase[letter_index] = guess
        puts "THAT GUESS WAS CORRECT! YOU WIN $50".colorize(:green)
        %x( say 'NICE GUESS' )
        sleep 0.2
        player_one.current_bank += 50
    end
end
if player_one.current_bank <= 0
    %x( say 'You R now broke #{player_one_name} please step off' )
    puts """
YOU HAVE RUN OUT OF MONEY.. TIME TO GO HOME!
    """.colorize(:red)
    %x( say "please leave now" )
        puts """
HOPE YOU ENJOYED THE GAME! BYE!!!
""".colorize(:green)
        sleep 2
        puts "Fin."
        sleep 3
end
```

