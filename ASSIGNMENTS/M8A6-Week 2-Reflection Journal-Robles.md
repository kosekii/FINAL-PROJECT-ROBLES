## Week of: September 27, 2026

## My goal this week
My main job this week was to clean up the mess in our `main.dart` file since it was getting way too long to read. Aside from that, I really needed to figure out a bug with our bottom menu that kept erasing our progress whenever we changed tabs.

## What I did
I set up some actual folders (`screens`, `widgets`, and `models`) and moved our code out of the main file. It looks so much cleaner now. I also typed up a `sample_data.dart` file full of fake classes and homework so Robyn had something to work with for the UI. The biggest thing I did, though, was completely rewriting how our navigation bar works using something called an `IndexedStack`.

## What blocked me
The biggest headache was figuring out why our app kept "forgetting" everything. If we checked a homework box, went to the Home tab, and came back, the box was empty again. I was super stuck on this and spent hours reading up on Flutter routing before I realized the default navigation just deletes the screen when you leave it.

## What I learned
I finally understand how `IndexedStack` works. Instead of throwing the screen away when you switch tabs, it basically keeps them all running in the background—kind of like tabs on a web browser. Finding that out was a huge relief because it instantly solved our bug and kept our checkboxes from resetting.