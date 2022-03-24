# `@media (prefers-reduced-data)`

## Authors:
- [@argyleink](https://github.com/argyleink)

## Participate
- https://github.com/w3c/csswg-drafts/pull/4575
- https://github.com/w3c/csswg-drafts/issues/2370

## Introduction

This feature indicates explicit user opt-in for a reduced data experience 
that when communicated to origins allows them to deliver alternate content honoring such preference: 
- smaller or no images
- less/no web fonts
- smaller video resources
- display swapping on lazy content
- alternate markup
- less/no promotions

## Motivating Use Cases

Users paying per megabyte become very aware of heavy URLs, avoiding them 
to save money.

Consider [this media browsing demo experience](https://gui-challenges.web.app/media-scroller/dist/). 

> Comparisons from Chrome Canary, experiment enabled, within a viewport of 1920x1280. 

#### Before reduced data and CSS
`55` requests total `949kb`, 
with additional requests made for each image on scroll (loading is lazy).

![Screen Shot 2022-03-24 at 11 13 15 AM](https://user-images.githubusercontent.com/1134620/159983004-b138ba4e-44de-4fb3-a6bd-76b91df4d347.png)

#### After reduced data and CSS

`7` requests total `104kb`, 
with **no additional requests made on scroll**.

```css
@media (prefers-reduced-data: reduce) {
    figure > picture {
        display: none
    }
}
```

![Screen Shot 2022-03-24 at 11 15 29 AM](https://user-images.githubusercontent.com/1134620/159983663-c8bfbd39-23cd-49ba-96f9-f532a7fde781.png)


## Non-goals
N/A

## User research
https://simonhearne.com/2020/save-data/

## `prefers-reduced-data`

https://www.w3.org/TR/mediaqueries-5/#prefers-reduced-data

```css
.image {
  background-image: url("images/heavy.jpg");
}

@media (prefers-reduced-data: reduce) {
  /* Save-Data: On */
  .image {
    background-image: url("images/light.jpg");
  }
}
```

## Key scenarios

### Scenario 1

A user in a data-saver mode wants to browse a webpage about books. 
The site uses the `prefers-reduced-data` media to remove book images from the layout, 
and the user is able to have low-bandwidth access to the full collection.

```js
.book img {
  display: none;
}
```

### Scenario 2

A website leans on fallback fonts by default, and if the user is visiting not in a reduced data state, 
they load their web fonts. 

https://www.smashingmagazine.com/2021/12/core-web-vitals-case-study-smashing-magazine/#savedata-and-prefers-reduced-data

## Detailed design discussion

### Tricky design choice #1

A user's operating system may offer the data-saver (perhaps alternate verbiage but same intent) 
option OR a browser may offer it within the settings and scope of the application. 
The choice was made to respect both, flagging `prefers-reduced-data` to true 
if the system or the browser have the setting enabled.

## Stakeholder Feedback / Opposition

- Adam Argyle (implementor) : Positive
- CSSWG: Positive

## References & acknowledgements

Many thanks for valuable feedback and advice from:

- Chen Hui Jing ([@huijing](https://github.com/huijing))
- Yoav Weiss ([@yoavweiss](https://github.com/yoavweiss))
- CSSWG Proposal https://github.com/w3c/csswg-drafts/issues/2370
