### storyboard
---
.js
http://guigrpa.github.io/storyboard/

https://github.com/guigrpa/storyboard

```js







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

```
```

```
```

