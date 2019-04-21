# pixi-spine

[![Build Status](https://travis-ci.org/pixijs/pixi-spine.svg?branch=master)](https://travis-ci.org/pixijs/pixi-spine)

Spine implementation for PixiJS v5.

For v4 please see [v4.x branch](https://github.com/pixijs/pixi-spine/tree/v4.x) and use npm version `1.5.21` 

## Usage

### Prebuilt Files

If you are just including the built files, pixi spine adds itself to a `PIXI` namespace:

```js
new PIXI.spine.Spine();
```

### Basic example

```js
var app = new PIXI.Application();

document.body.appendChild(app.view);

app.loader
    .add('spineCharacter', 'spine-data-1/HERO.json')
    .load(function (loader, resources) {
        var animation = new PIXI.spine.Spine(resources.spineCharacter.spineData);

        // add the animation to the scene and render...
        app.stage.addChild(animation);
        
        // run 
        var animation = new PIXI.spine.Spine(spineBoyData);
        if (animation.state.hasAnimation('run')) {
            // run forever, little boy!
            animation.state.setAnimation(0, 'run', true);
            // dont run too fast
            animation.state.timeScale = 0.1;
        }
        
        app.start();
    });
```

## Want to go advanced?

Read our [docs](examples/index.md).

## Using webpack or browserify?

Our library is tested for integration with webpack and browserify,
check [our travis config](.travis.yml) and [checkpack](http://github.com/cursedcoder/checkpack).

## Typescript

There's "bin/pixi-spine.d.ts" file, you can use it.

## Spine version

We aim to support the latest stable version of spine. 

If you are below Spine 3.5, please please enable "beta updates" and re-export everything from the spine editor.

According to spine runtime license, you can use runtime only if you have bought the editor, so exporting latest versions of animations shouldn't be a problem for you.

## Building

You will need to have [node][node] setup on your machine.

Make sure you have [yarn][yarn] installed:

    npm install -g yarn

Then you can install dependencies and build:

```bash
yarn
yarn build
```

That will output the built distributables to `./bin`.

[node]:             https://nodejs.org/
[typescript]:       https://www.typescriptlang.org/
[yarn]:             https://yarnpkg.com
