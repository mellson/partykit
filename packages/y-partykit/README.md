## y-partykit

- ⭐️one sentence about yjs

(based off work in https://github.com/yjs/y-websocket)

- ⭐️ one para about y-partykit

- ⭐️ one para on what a yjs backend actually is

- ⭐️ one para on how yjs providers work

- 👾 how yjs + partykit scales

## Installation

```sh
npm install partykit@beta y-partykit@beta
```

## Usage

```ts
import { onConnect } from "y-partykit";
import type { PartyKitServer } from "partykit";

export default {
  async onConnect(conn, room) {
    return await onConnect(conn, room, options);
  },
} satisfies PartyKitServer;
```

👾 ## API

### `onConnect(conn, room, options)`

conn: PartyKitConnection

room: PartyKitRoom

options:

persist?: boolean;
callback?:
debounceWait?: number;
debounceMaxWait?: number;
timeout?: number;

    &

    url: string;
    headers?: Headers;
    objects?: Record<string, string>;

    |

    handler: (doc: Y.Doc) => void;

load?: () => Promise<Y.Doc>;
readOnly?: boolean;

### `new YPartyKitProvider(

host: string,
room: string,
doc: Y.Doc,
{
party?: string;
connect = true,
awareness = new awarenessProtocol.Awareness(doc),
params = {},
resyncInterval = -1, // Request server state every `resyncInterval` milliseconds
maxBackoffTime = 2500, // Maximum amount of time to wait before trying to reconnect (we try to reconnect using exponential backoff)
disableBc = false
})`

- ⭐️ howtos

  - load and save from a database

  - integrate with a text editor (todo: all of them in the docs)

  - awareness

    - quickly explain what awareness (use the word 'presence')

  - state management
    - a simple example with _either_ syncedstore https://syncedstore.org/ or with valtio+yjs
      - literally a copy-pastable boilerplat for initialising a shared store and _maybe_ changing a field or 2
