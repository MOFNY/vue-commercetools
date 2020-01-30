# vue-commercetools

## Introduction
This simple app was created using Vue.
I started using Vue last year and I love it.
It felt like the natural choice for this project.

## Challenges
I am still a novice with Vue, so I had to figure out how best to structure the project.
I'm still not sold on scoped CSS, so I use a small stylesheet and some scoped.
If I was to refactor this, I would start with the images.
I would demand more consistency and establish guidelines.
Many of the images are poorly cropped with a ton of whitespace.
Plus I would love to see multiple sizes so I can use `srcset`.

## Code I am most proud of
I wanted to focus on the UI as much as possible.
It has a simple layout and styles but it works fairly well.
The code is also pretty readable and organized relatively well.
I'm a big fan of a "skeleton" loading view, so I attempted a simple component.
Refresh the page a few times to check it out.

## Code I am least proud of
I couldn't figure out how to properly filter the products (the FIXME).
I would like to bring in state management as it grows in complexity.
Creating a product detail view also would have been valuable, but that would have diminished my focus on the Products view.
I would have liked to break up the Products component more.
There could be a Product child component, and a component for the filtering.

## Tradeoffs
I didn't test in IE11...
It would have been awesome to dive into the API more, but I didn't want to get that far in the weeds.
In the same vein, I didn't use that much data. I should have added at least a price on the card.
I love pagination, so creating some dynamic routes with the total products count would have been fun.
Writing at least a few unit tests...

## Additional Notes
This was one of the better front end exercises I've done.
It was more open-ended and is similar to what I actually do every day.
Overall, so much better than a HackerRank challenge that doesn't apply to real life.

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
