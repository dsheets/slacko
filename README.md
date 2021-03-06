Slacko
======

![Slacko logo](slacko.png) A neat interface for [Slack](https://slack.com/)

Your company got you Slack and you're all like "yeah, and now I am forced to
use a browser or what?". Fear no more, because as it turns out Slack has a REST
API that can be accessed.

Yeah, scripting Slack via `curl` sucks, so let's do something that sucks less.
Maybe a bit? How about using an existing
[integration](https://api.slack.com/community)? They are incomplete or for
sucky languages? Glad you asked, because I have *just the right thing* for you:
a neat interface to Slack via [OCaml](https://ocaml.org/)!

What do you need? OCaml, OPAM and a Slack token. All for free, no asterisks, no
hidden clauses. Life can be so easy.

Install that cow!
-----------------

Huzzah, I got you interested? Lucky you, Slacko can easily be installed via
[OCaml Package Manager (OPAM)](https://opam.ocaml.org/), so you just write

```sh
$ opam install slacko
```

Now wasn't this easy? Bet your ass it was! And you know what? It even gets
better: it also installed you a nifty little executable called `slack-notify`
which you can use to post directly to Slack *from your shell*, no programming
required at all. Actually, once compiled, not even OCaml is required anymore,
everything is self-contained.

In case you want to manually install it, you can, too. There's a number of
dependencies that you have to take care of yourself:

  * [OCaml](http://ocaml.org/), >= 4.02.0 (no kidding)
  * [Lwt](https://ocsigen.org/lwt/) >= 2.4.6 (for ppx support)
  * [Cmdliner](http://erratique.ch/software/cmdliner)
  * [Yojson](http://mjambon.com/yojson.html)

Then you can build Slacko by yourself:

```sh
$ ocaml setup.ml -configure
$ ocaml setup.ml -build
$ ocaml setup.ml -install
```

Ready, set, go!
---------------

Not convinced yet? Check out this neat documentation from `slack-notify` to
help you out.

```
NAME
       slack-notify - Writes messages to slack

SYNOPSIS
       slack-notify [OPTION]... CHANNEL MSG

ARGUMENTS
       CHANNEL
           Name of the channel to post to

       MSG Message to send

OPTIONS
       --help[=FMT] (default=pager)
           Show this help in format FMT (pager, plain or groff).

       --icon-emoji=EMOJI
           emoji to use as the icon for this message. Overrides icon-url

       --icon-url=URL
           URL to an image to use as the icon for this message

       -t TOKEN, --token=TOKEN
           The Slack API access token

       -u USERNAME, --username=USERNAME
           Name of the bot in the chat
```

So what is this token thing? Once you signed up for Slack, you can get a token
for every team you are in from [the Slack API docs](https://api.slack.com/).
Click on the "get token" link and you're all set.

But I do want to code my own stuff!
-----------------------------------

You know, Slacko is a nice gal/guy. So you can just plug together whatever you
want with it, since it currently implements 
[100% of the Slack API](https://api.slack.com/methods)! How neat is this? And
you can use it in your own code without worrying about the license one bit,
since the [LGPL 3.0](https://www.gnu.org/licenses/lgpl.html) is liberal for
re-use, coupled with the
[OCaml linking exception](http://caml.inria.fr/pub/old_caml_site/ocaml/LICENSE.html).
For realz!

Something's amiss?
------------------

I know, I know, it is hardly believable that something could possibly be
missing from this library. But wonders happen, and if you run into one of these
cases, just shoot me a pull request.

Credit where credit's due
-------------------------

Thanks go to all the people who wrote
[CoHTTP](https://github.com/mirage/ocaml-cohttp), a real-world HTTP library
that doesn't suck and [Lwt](http://ocsigen.org/lwt/), an oddball library that
subconsciously *makes sense*. Also, the fine folks in
[#ocaml](http://irclog.whitequark.org/ocaml/) on
[freenode](https://freenode.net/).
