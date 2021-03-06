# moirai
[![Dependency Status](https://david-dm.org/freezedev/moirai.svg)](https://david-dm.org/freezedev/moirai)
[![devDependency Status](https://david-dm.org/freezedev/moirai/dev-status.svg)](https://david-dm.org/freezedev/moirai#info=devDependencies)

React.js game engine. Exciting, experimental and unstable.

`moirai` borrows a lot of ideas from [Lyria](http://github.com/freezedev/lyria).

## What does it look like?

Let's create a game:
```javascript
import React, {Component} from 'react';
import ReactDOM from 'react-dom';

import {Viewport, SceneDirector, Scene, GameObject} from 'moirai';

const updateFn = function(dt, gameObject) {
  gameObject.setState({x: gameObject.state.x += (dt * 10)});
};

const Game = () => (
  <Viewport>
    <SceneDirector>
      <Scene>
        <GameObject initialX={10} initialY={10} />
          <Texture source="hero.png" />
          <Behavior
            onUpdate={updateFn} />
        <GameObject />
      </Scene>
    </SceneDirector>
  </Viewport>
);

ReactDOM.render(<Game />, document.getElementById('container'));
```

This game engine is heavily inspired by [React Router](http://github.com/rackt/react-router).

## Philosophy
- Thin layer on top of React.js

## License
Public domain (UNLICENSE). If that does not work for you, you are allowed to license it under the terms of the MIT license.
