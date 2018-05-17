---
title: Real world Haskell
author: Jan Šipr <br/>[github.com/siprj](https://github.com/siprj)
date: 17 May 2018
---

# Something about me

* C++ - 4 years
* Haskell - 2 years
* No formal education in abstract mathematics ;)
* Work on some haskell packages (hsua, hlint-test, freer-effects)

# Why functional programming matters

* Functions are first class citizens
* Partial application
* Immutability
* Sum types
* Laziness
* Pattern matching
* Mostly strongly typed
* [Reference to a great talk](https://www.youtube.com/watch?v=oB8jN68KGcU)

# Academic haskell vs real world haskell

* There is not much deference

# Examples of some haskell projects

* Universal document converter [pandoc](https://pandoc.org/)
    * 56000 loc
* Distributed file synchronization system [git-annex](https://git-annex.branchable.com/)
    * 58000 loc
* Quake like game [Frag](https://github.com/rainbyte/frag)
    * only 5582 loc
* Whole haskell infrastructure
    * Hackage
    * Hoogle
    * Stackage
    * GHC

# Ixcom - Story of our first product

* Telephony exchange
* 70000 loc
* Bunch of APIs: REST API, Json RPC
* DLS for phone number description
* Build on top of asterisk
* The core never crashed

# Vision - Story of our second product

* Image processing
* Extremely fast developement
* Zero tests
* We are still waiting for first bug to arrive

# Functional jobs

* Functional job in general is obtainable
* Haskell job in Czech Republic (not so much)
* Haskell job in the world (lot of opportunities)

# Hiring haskellers

* Easy to find
* People are over qualified
* People accept to lower salary

# Great books

* [Haskell Programming from first principles](http://haskellbook.com/)
* [Real World Haskell](http://book.realworldhaskell.org/)
* [Learn You a Haskell for Great Good!](http://learnyouahaskell.com/)
* [List of some free haskell books](https://github.com/TechBookHunter/Free-Haskell-Books)

# News and connections

* [r/haskell](https://www.reddit.com/r/haskell/)
* IRC channels on freenode
    * #haskell
    * #haskell-embedded
* [https://fpchat-invite.herokuapp.com/](https://fpchat-invite.herokuapp.com/)
* [pair-programming](https://github.com/Wizek/haskell-pair-programming)

# Invitation to FPBrno

* [meetup.com/fpbrno/](https://www.meetup.com/fpbrno/)
* Next talk
    * Topic: Reason ML & Benchmarking in Elixir
    * Date: Tuesday, May 22, 2018

# Other areas where haskell can be used

* [clash](http://www.clash-lang.org/) - compilation haskell on FPGA
* [ivory-tower](https://ivorylang.org/ivory-introduction.html) - EDSL for C -> embedded devices
* quantum computers

# Some useful libraries

* acid
* aeson
* containers
* lenses
* megaparsec
* monad-logger
* mtl
* persistent
* servant
* template-haskell

# Servant example

~~~ { .haskell file=Fruit1.hs }
type ItemApi =
    -- GET /item
    "item" :> Get '[JSON] [Item] :<|>
    -- GET /item/:itemId
    "item" :> Capture "itemId" Integer :> Get '[JSON] Item

getItems :: Handler [Item]
getItems = return [exampleItem]

getItemById :: Integer -> Handler Item
getItemById = \case
    0 -> return exampleItem
    _ -> throwE err404

server :: Server ItemApi
server = getItems :<|> getItemById
~~~

Taken form [example-servant-minimal](https://github.com/haskell-servant/example-servant-minimal).

# freer-effects example

[example](https://github.com/IxpertaSolutions/freer-effects)

# Questions?

* Thank you for your attention.
* Slides will be available at [github.com/siprj/haskell-seminar-presentation-spring-2018](https://github.com/siprj/haskell-seminar-presentation-spring-2018)
