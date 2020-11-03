Strategy basically involves creating a boolean ref that gets switched from `false` to `true` on initial render, making the first effect call a noop.

https://www.thearmchaircritic.org/tech-journals/prevent-useeffects-callback-firing-during-initial-render