## Week of: September 27, 2026

## What changed this week
- **Cleaned up our files:** We finally split our giant `main.dart` file from week 1 into a proper folder structure (`lib/screens/`, `lib/widgets/`, and `lib/models/`).
- **Fixed the navigation bar:** We changed how our bottom menu works. We are now using a widget called `IndexedStack` instead of just swapping out the pages.
- **Added mock data:** We created a `sample_data.dart` file with a fake list of homework and classes so we actually have something to show on the screen.
- **Built the cards and lists:** We created reusable design cards (like `assignment_card.dart`) and used `ListView.builder` to show them as a scrolling list on the screen.
- **Working checkboxes:** We made the assignment cards interactive. You can now click the checkbox to cross out a homework task.

## Why
We had to move our code out of `main.dart` because it was getting way too long and confusing to read. We switched our menu to use `IndexedStack` because before, every time we clicked the "Home" tab and went back to the "Tasks" tab, the app would delete our progress and un-check all our boxes. The new lists and cards were needed so we didn't have to hard-code every single piece of homework onto the screen.

## What broke or what I got stuck on

**For Gonzales, Robyn:** I got completely stuck on a giant red error screen that said `RenderBox was not laid out`. I was trying to put my scrolling list of homework directly inside a `Column` so I could put a title text above it. I learned the hard way that putting a list that wants to scroll forever inside a column that wants to be as tall as possible crashes Flutter. I had to learn how to use the `Expanded` widget to fix it.

**For Robles, John:** I got stuck on a major bug where our app was "forgetting" everything. If we checked a box on the Tasks tab, clicked over to the Home tab, and then clicked back, the box was unchecked again. I spent hours reading about routing and trying to pass variables back and forth before I realized that standard bottom navigation completely deletes the old screen. I finally figured out how to fix it using `IndexedStack`.

## What is left
- We need to hook up local storage (`shared_preferences`) so the app actually saves your data when you close the browser.
- We need to build the "Add Task" pop-up form so users can type in their own homework.
- Final testing and taking our final screenshots for the documentation.