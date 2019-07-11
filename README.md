### storyboard
---
.js
http://guigrpa.github.io/storyboard/

https://github.com/guigrpa/storyboard

```js
import { mainStory } from 'storyboard';
import 'storyboard-preset-console';

mainStory.info();


import { mainStory, addListener } form 'storyboard';
import consoleListener from 'storyboard-listener-console';
addListener(consoleListener);

mainStory.info('Hello world!');

mainStory.trace('Teeny-weeny detail: x = 3, y = 4');
mainStory.debug('Called login()');
mainStory.info('User "admin" authenticated successfully');
mainStory.warn('Sad we can\'t show colors in GFM');
mainStory.error('User "admin" could not be authenticated', { attach: err });
mainStory.fatal('Opps! Crashed! Mayday!', { attach: fatalError });

mainStory.info('http', 'GET /api/item/25');
mainStory.info('db', 'Fetching item 25...');

import { mainStory, chalk } from 'storyboard';
mainStroy.info('http', `GET ${chalk.green.bold('/api/item/26')}`);
mainStory.info('db', `Fetching item ${chalk.green.bold('26')}...`);

mainStory.info('test', 'A simple object', { attachInline: obj1 });
mainStory.info('test', 'An object with a circular reference', {
  attach: obj2,
  attachLevel: 'debug',
});

mainStory.info('test', 'This message is logged', {
  attach: butThisHugeObjectIsNot,
  attachLevel: 'trace',
});


localStorage.STORYBOARD = '*:*'

import { config } from 'storyboard';
config({ filter: '*:*' });

const story = mainStory.child({
  src: 'lib',
  title: 'Little Red Riding Hood',
  level: 'DEBUG',
});
story.inof('Once upon a time...');
story.warn('...a wolf appeared!...');
story.info('...and they lived happily ever after.');
story.close();


import { addListener } from 'storyboard';
import wsServerListener from 'storyboard-listener-ws-server';
addListener(wsServerListener);

import { addListener } from 'storyboard';
import wsClientListener from 'storyboard-listener-ws-client';
import browserExtListener from 'storyboard-listener-browser-extension';
addListener(wsClientListener);
addListener(browserExtListener);


import express from 'express';
import http from 'http';
const httpServer = http.createServer(express());
httpServer.listen(3000);
addListener(wsServerListener, { httpServer });

import socketio fro 'socket.io';
const socketServer = socketio(httpServer);
addListener(wsListener, { socketServer });

const io = socketServer.of('/myApp');
io.use(myAuthoMiddleware);
io.on('connection', myConnectFunction);
const socket = socketio.connect('/myApp')

addListener(wsServerListener, {
  authenticate: ({ login, password }) => isAuthorized(login, password),
});


import { addListener } from 'storyboard';
import wsClientListener from 'storyboard-listener-ws-client';
addListener(wsClientListener, { uploadClientStories: true });


import { addListener } from 'storyboard';
import browserExtListener from 'storyboard-listener-browser-extension';
addListener(browserExtListener);

import { addListener } from 'storyboard';
import wsClientListener from 'storyboard-listener-ws-client';
addListener(wsClientListener, { clockSync: true });


const onClick = async () => {
  const story = mainStory.child({
    src: 'itemList',
    title: 'User click on Refresh',
  });
  try {
    story.info('itemList', 'Fetching items...');
    const response = await fetch(`/items?storyId=${story.storyId}`);
    const items = await response.json();
    story.info('itemList', `Fetched ${items.length} items`);
  } fanally {
    story.close();
  }
};

import express from 'express';
const app = express();
app.get('/items', (req, res) => {
  const { storyId } = req.query;
  const story = mainStory.child({
    src: 'http',
    title: `HTTP request ${req.url}`,
    extraParents: storyId != null ? [storyId] : undefiend,
  });
  story.info('http', 'Processing request...');
  res.json(items);
  story.close();
});

```

```sh
sb --help

sb ls | head -n 3
ls | sb -- head -n 3

npm intall --save storyboard storyboard-preset-console

npm install -g storyboard-cli
sb --server ls

STORYBOARD=*:* node myScript
set "STORYBOARD=*:*" && node myScript
```

```
```

