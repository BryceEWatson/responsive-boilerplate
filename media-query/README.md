CSS Media Query Boilerplate
===========================

For responsive design, we need to use CSS media query. There are many ways to write media queries, which can lead to inconsistencies in code and the resulting UI experience. When the entire team sticks to the same set of media queries, the resulting css is more likely to work as expected and is more maintainable. This is where CSS Media Query Boilerplate comes in.



How to use the boilerplate
--------------------------
- Decide whether the default page will be used in a small screen (mobile first) or a large screen (non-mobile first).
- Copy the appropriate boilerplate from [media-query-boilerplate.less](./media-query-boilerplate.less) to the bottom of your LESS file.
- Do not change the order of the media queries - order matters for cascading!
- If a specific media query does not apply, leave it. Although removing it will save a few bytes, this is a likelihood that people will use non-standard widths later when they need to add breakpoints back.
- We can discuss the breakpoints, but we should agree on them and stick to them.
- You should not need to use any other media queries for responsive design, which is mostly width-dictated. If you think you need other media queries, let's discuss.



Tips on media queries
---------------------
- Do not use orientation in your media query. Orientation support can be surprising across devices (especially older devices). Besides, we should care only about width.
- Use min-width/max-width. Do not use min-device-width/max-device-width. See https://developers.google.com/web/fundamentals/layouts/rwd-fundamentals/use-media-queries?hl=en#a-note-on-min-device-width
- Media query should be top-level css. Do not put media query inside CSS rules. Keep all media queries at the bottom of the file because media queries are supposed to override CSS rules.
- Rules inside media query follow the same cascading rules. If you have nested classes in the default CSS rules, use the same set of nested classes in the media queries. Otherwise, your media queries will be ignored.
- Use body background-color or body border to test your media query. This is the simplest way to verify that your media queries are working as expected. Remember to remove them when you check in.
- Combination width media queries, e.g., "(min-width: XXXpx) and (max-width: YYYpx)", are not necessary. With the proper set (order matters!) of media queries, the cascading will take care of that for you.
