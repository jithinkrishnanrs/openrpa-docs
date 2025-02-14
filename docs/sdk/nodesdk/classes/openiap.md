[@openiap/nodeapi](../README.md) / [Exports](../modules.md) / openiap

# Class: openiap

OpenIAP

## Hierarchy

- `EventEmitter`

  ↳ **`openiap`**

## Table of contents

### Constructors

- [constructor](openiap.md#constructor)

### Properties

- [agent](openiap.md#agent)
- [allowconnectgiveup](openiap.md#allowconnectgiveup)
- [client](openiap.md#client)
- [connected](openiap.md#connected)
- [connecting](openiap.md#connecting)
- [defaltqueue](openiap.md#defaltqueue)
- [flowconfig](openiap.md#flowconfig)
- [jwt](openiap.md#jwt)
- [loginreject](openiap.md#loginreject)
- [loginresolve](openiap.md#loginresolve)
- [pingerhandle](openiap.md#pingerhandle)
- [queuecallbacks](openiap.md#queuecallbacks)
- [queues](openiap.md#queues)
- [reconnectms](openiap.md#reconnectms)
- [signedin](openiap.md#signedin)
- [url](openiap.md#url)
- [version](openiap.md#version)
- [watchids](openiap.md#watchids)
- [captureRejectionSymbol](openiap.md#capturerejectionsymbol)
- [captureRejections](openiap.md#capturerejections)
- [defaultMaxListeners](openiap.md#defaultmaxlisteners)
- [errorMonitor](openiap.md#errormonitor)

### Methods

- [AddWorkItemQueue](openiap.md#addworkitemqueue)
- [Aggregate](openiap.md#aggregate)
- [Close](openiap.md#close)
- [Count](openiap.md#count)
- [CreateCollection](openiap.md#createcollection)
- [CreateIndex](openiap.md#createindex)
- [CreateWorkflowInstance](openiap.md#createworkflowinstance)
- [CustomCommand](openiap.md#customcommand)
- [DeleteAgent](openiap.md#deleteagent)
- [DeleteAgentPod](openiap.md#deleteagentpod)
- [DeleteMany](openiap.md#deletemany)
- [DeleteOne](openiap.md#deleteone)
- [DeletePackage](openiap.md#deletepackage)
- [DeleteWorkItemQueue](openiap.md#deleteworkitemqueue)
- [DeleteWorkitem](openiap.md#deleteworkitem)
- [Distinct](openiap.md#distinct)
- [DownloadFile](openiap.md#downloadfile)
- [DropCollection](openiap.md#dropcollection)
- [DropIndex](openiap.md#dropindex)
- [EnsureCustomer](openiap.md#ensurecustomer)
- [FindOne](openiap.md#findone)
- [GetAgentLog](openiap.md#getagentlog)
- [GetAgentPods](openiap.md#getagentpods)
- [GetDocumentVersion](openiap.md#getdocumentversion)
- [GetElement](openiap.md#getelement)
- [GetIndexes](openiap.md#getindexes)
- [InsertMany](openiap.md#insertmany)
- [InsertOne](openiap.md#insertone)
- [InsertOrUpdateMany](openiap.md#insertorupdatemany)
- [InsertOrUpdateOne](openiap.md#insertorupdateone)
- [InvokeOpenRPA](openiap.md#invokeopenrpa)
- [ListCollections](openiap.md#listcollections)
- [Ping](openiap.md#ping)
- [PopWorkitem](openiap.md#popworkitem)
- [PushWorkitem](openiap.md#pushworkitem)
- [PushWorkitems](openiap.md#pushworkitems)
- [Query](openiap.md#query)
- [QueueMessage](openiap.md#queuemessage)
- [RegisterExchange](openiap.md#registerexchange)
- [RegisterQueue](openiap.md#registerqueue)
- [Signin](openiap.md#signin)
- [StartAgent](openiap.md#startagent)
- [StopAgent](openiap.md#stopagent)
- [UnRegisterQueue](openiap.md#unregisterqueue)
- [UnWatch](openiap.md#unwatch)
- [UpdateDocument](openiap.md#updatedocument)
- [UpdateOne](openiap.md#updateone)
- [UpdateWorkItemQueue](openiap.md#updateworkitemqueue)
- [UpdateWorkitem](openiap.md#updateworkitem)
- [UploadFile](openiap.md#uploadfile)
- [Watch](openiap.md#watch)
- [\_\_server\_pinger](openiap.md#__server_pinger)
- [addListener](openiap.md#addlistener)
- [cliOnConnected](openiap.md#clionconnected)
- [cliOnDisconnected](openiap.md#cliondisconnected)
- [cliOnMessage](openiap.md#clionmessage)
- [connect](openiap.md#connect)
- [emit](openiap.md#emit)
- [eventNames](openiap.md#eventnames)
- [getMaxListeners](openiap.md#getmaxlisteners)
- [listenerCount](openiap.md#listenercount)
- [listeners](openiap.md#listeners)
- [off](openiap.md#off)
- [on](openiap.md#on)
- [onConnectGaveUp](openiap.md#onconnectgaveup)
- [onConnected](openiap.md#onconnected)
- [onDisconnected](openiap.md#ondisconnected)
- [once](openiap.md#once)
- [prependListener](openiap.md#prependlistener)
- [prependOnceListener](openiap.md#prependoncelistener)
- [rawListeners](openiap.md#rawlisteners)
- [removeAllListeners](openiap.md#removealllisteners)
- [removeListener](openiap.md#removelistener)
- [setMaxListeners](openiap.md#setmaxlisteners)
- [stringify](openiap.md#stringify)
- [GetUniqueIdentifier](openiap.md#getuniqueidentifier)
- [getEventListeners](openiap.md#geteventlisteners)
- [listenerCount](openiap.md#listenercount-1)
- [on](openiap.md#on-1)
- [once](openiap.md#once-1)
- [setMaxListeners](openiap.md#setmaxlisteners-1)

## Constructors

### constructor

• **new openiap**(`url?`, `jwt?`)

Create a client for connecting to an OpenIAP flow instace.
By default it loads the apiurl from environment variable apiurl, grpcapiurl or wscapiurl
You can supply username and password in the URL ( remember this needs to e URL encoded ) or you
can supply a JWT token in the jwt environment variable or as the second parameter to the constructor.

You can connect using one of these protocols
- Using google RPC by using grpc:// as protocol. This require you also supply a port number. Example: `grpc://host.name:port`
For docker or kubernetes deployments this is usually the main domain prefixed with grpc.
for instance if your main domain is `app.openiap.io` then the grpc url would be `grpc://grpc.app.openiap.io:443`
For developer installations, the grpc url would be `grpc://localhost:50051`
- Using WebSocket by using ws:// or wss:// as protocol. wss when using certificates. ws when unsecured
For example `wss://app.openiap.io` or `ws://localhost.openiap.io`
- Using named pipes by using pipe:// as protocol. For example `pipe://localhost/testpipe`
- Using TCP sockets by using tcp:// as protocol. For example `tcp://localhost.openiap.io:8080`
- Using HTTP/REST by using http:// or https:// as protocol. https when using certificates. http when unsecured
For example `https://app.openiap.io/api/v2` or `http://localhost.openiap.io/api/v2`

**`Example`**

Connect to OpenIAP flow instance
```typescript
const { openiap } = require("@openiap/nodeapi");
client.connect().then(async client=> {
 console.log("Connected")
 const result = await client.Query({ query: { "_type": "test" } });
 console.log(result);
 client.Close();
}).catch(err => {
console.log("Failed to connect: " + err)
}
```

**`Example`**

Connect to OpenIAP using a connection string. 
```typescript
const { openiap } = require("@openiap/nodeapi");
async function main() {
  const client = new openiap("grpc://grpc.app.openiap.io:443");
  await client.connect();
  const user = client.Signin({username: "henrik", password: "SuperSecret"});
}
main();
```

**`Example`**

Alternatively we can supply credentials in the connection string, then we do not need to call Signin
```typescript
const { openiap } = require("@openiap/nodeapi");
async function main() {
  const client = new openiap("grpc://henrik:SuperSecret@grpc.app.openiap.io:443");
  await client.connect();
}
main();
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `url` | `string` | `""` | By default we read from environment variable apiurl, grpcapiurl or wscapiurl but can be overriden here |
| `jwt` | `string` | `""` | By default we read from environment variable jwt but can be overriden here |

#### Overrides

EventEmitter.constructor

#### Defined in

[src/openiap.ts:121](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L121)

## Properties

### agent

• **agent**: [`clientAgent`](../modules.md#clientagent) = `"node"`

Define client type when authenticating toward the server

#### Defined in

[src/openiap.ts:37](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L37)

___

### allowconnectgiveup

• **allowconnectgiveup**: `boolean` = `true`

If false, the client will never give up trying to connect to the server, if true, will give up after 17 seconds

#### Defined in

[src/openiap.ts:41](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L41)

___

### client

• **client**: [`client`](client.md)

The internal client object

#### Defined in

[src/openiap.ts:24](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L24)

___

### connected

• **connected**: `boolean` = `false`

Define if connected to server

#### Defined in

[src/openiap.ts:49](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L49)

___

### connecting

• **connecting**: `boolean` = `false`

Define if we are trying to (re)connect

#### Defined in

[src/openiap.ts:53](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L53)

___

### defaltqueue

• `Private` **defaltqueue**: `string` = `""`

#### Defined in

[src/openiap.ts:32](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L32)

___

### flowconfig

• **flowconfig**: `any` = `{}`

#### Defined in

[src/openiap.ts:33](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L33)

___

### jwt

• **jwt**: `string` = `""`

The JWT used when authenticating to the server

#### Defined in

[src/openiap.ts:65](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L65)

___

### loginreject

• `Private` **loginreject**: `any`

#### Defined in

[src/openiap.ts:26](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L26)

___

### loginresolve

• `Private` **loginresolve**: `any`

#### Defined in

[src/openiap.ts:25](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L25)

___

### pingerhandle

• `Private` **pingerhandle**: `any`

#### Defined in

[src/openiap.ts:28](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L28)

___

### queuecallbacks

• `Private` **queuecallbacks**: `any` = `{}`

#### Defined in

[src/openiap.ts:29](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L29)

___

### queues

• `Private` **queues**: `any` = `{}`

#### Defined in

[src/openiap.ts:31](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L31)

___

### reconnectms

• `Private` **reconnectms**: `number` = `100`

#### Defined in

[src/openiap.ts:27](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L27)

___

### signedin

• **signedin**: `boolean` = `false`

If connected, are we also signed in or is server waiting on use to authenticate

#### Defined in

[src/openiap.ts:57](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L57)

___

### url

• **url**: `string` = `""`

The URL used when connecting to the server

#### Defined in

[src/openiap.ts:61](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L61)

___

### version

• **version**: `string` = `"0.0.14"`

Define the version of the client sent to the server

#### Defined in

[src/openiap.ts:45](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L45)

___

### watchids

• `Private` **watchids**: `any` = `{}`

#### Defined in

[src/openiap.ts:30](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L30)

___

### captureRejectionSymbol

▪ `Static` `Readonly` **captureRejectionSymbol**: typeof [`captureRejectionSymbol`](openiap.md#capturerejectionsymbol)

#### Inherited from

EventEmitter.captureRejectionSymbol

#### Defined in

node_modules/@types/node/events.d.ts:328

___

### captureRejections

▪ `Static` **captureRejections**: `boolean`

Sets or gets the default captureRejection value for all emitters.

#### Inherited from

EventEmitter.captureRejections

#### Defined in

node_modules/@types/node/events.d.ts:333

___

### defaultMaxListeners

▪ `Static` **defaultMaxListeners**: `number`

#### Inherited from

EventEmitter.defaultMaxListeners

#### Defined in

node_modules/@types/node/events.d.ts:334

___

### errorMonitor

▪ `Static` `Readonly` **errorMonitor**: typeof [`errorMonitor`](openiap.md#errormonitor)

This symbol shall be used to install a listener for only monitoring `'error'`
events. Listeners installed using this symbol are called before the regular
`'error'` listeners are called.

Installing a listener using this symbol does not change the behavior once an
`'error'` event is emitted, therefore the process will still crash if no
regular `'error'` listener is installed.

#### Inherited from

EventEmitter.errorMonitor

#### Defined in

node_modules/@types/node/events.d.ts:327

## Methods

### AddWorkItemQueue

▸ **AddWorkItemQueue**(`options`, `priority?`, `span?`): `Promise`<[`WorkItemQueue`](../modules.md#workitemqueue)\>

Create a new workitem queue. Workitem queues are registered in the wiq collection.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `AddWorkItemQueueOptions` | `undefined` | AddWorkItemQueueOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<[`WorkItemQueue`](../modules.md#workitemqueue)\>

#### Defined in

[src/openiap.ts:1445](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1445)

___

### Aggregate

▸ **Aggregate**<`T`\>(`options`, `priority?`, `span?`): `Promise`<`T`[]\>

Run an mongodb aggregation pipeline toward the OpenIAP flow database.
See https://docs.mongodb.com/manual/aggregation/ for more information

**`See`**

https://docs.mongodb.com/manual/aggregation/

**`Example`**

Get the count of all documents with type "test" from entities collection
```typescript
const result = await client.Aggregate({ collectionname: "entities", aggregates: [{ "$match": { "_type": "test" } }, { "$count": "count" }] });
```

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`AggregateOptions`](../modules.md#aggregateoptions) | `undefined` | [AggregateOptions](../modules.md#aggregateoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`T`[]\>

An array of documents matching the aggregation pipeline

#### Defined in

[src/openiap.ts:726](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L726)

___

### Close

▸ **Close**(): `void`

Close connection to server. Use this to ensure the client will not reconnect to the server

#### Returns

`void`

#### Defined in

[src/openiap.ts:184](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L184)

___

### Count

▸ **Count**(`options`, `priority?`, `span?`): `Promise`<`number`\>

Getting the count of documents in a collection can be done using this function. 
Leave query empty to get the total count of documents in the collection.

**`Example`**

Get the count of documents with type "test" from entities collection
```typescript
const result = await client.Count({ collectionname: "entities", query: { "_type": "test" } });
```

**`Example`**

Get the total number of documents in the entities collection
```typescript
const result = await client.Count({ collectionname: "entities" });
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`CountOptions`](../modules.md#countoptions) | `undefined` | [CountOptions](../modules.md#countoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`number`\>

The number of documents matching the query

#### Defined in

[src/openiap.ts:667](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L667)

___

### CreateCollection

▸ **CreateCollection**(`options`, `priority?`, `span?`): `Promise`<`void`\>

Create a collection removing all data from the collection. Only users with admin rights can Create collections.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `CreateCollectionOptions` | `undefined` | CreateCollectionOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`void`\>

#### Defined in

[src/openiap.ts:529](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L529)

___

### CreateIndex

▸ **CreateIndex**(`options`, `priority?`, `span?`): `Promise`<`string`\>

Return the console output of an running agent, can be in docker, kubernetes or running remote.
Requires invoke permission on agent

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `CreateIndexOptions` | `undefined` | CreateIndexOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`string`\>

Returns the index name

#### Defined in

[src/openiap.ts:1724](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1724)

___

### CreateWorkflowInstance

▸ **CreateWorkflowInstance**(`options`, `priority?`, `span?`): `Promise`<`string`\>

Old command used by nodered "Workflow in" and "assign" nodes for creating a new workflow instance.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`CreateWorkflowInstanceOptions`](../modules.md#createworkflowinstanceoptions) | `undefined` |  |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`string`\>

#### Defined in

[src/openiap.ts:1524](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1524)

___

### CustomCommand

▸ **CustomCommand**<`T`\>(`options`, `priority?`, `span?`): `Promise`<`string`\>

Run custom commands not defined in the protocol yet.
This is how new functioanlly is added and tested, before it is finally added to the offical proto3 protocol.

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`CustomCommandOptions`](../modules.md#customcommandoptions) | `undefined` |  |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`string`\>

If command has a result, this will be returned as a string. This will most likely need to be parser as JSON

#### Defined in

[src/openiap.ts:1503](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1503)

___

### DeleteAgent

▸ **DeleteAgent**(`options`, `priority?`, `span?`): `Promise`<`void`\>

Remove an agent if running. Docker and Kubernetes only.
Removes instance on docker, remove deployment, ingress and other resources on Kubernetes
Requires delete permission on agent

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `DeleteAgentOptions` | `undefined` | DeleteAgentOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`void`\>

void

#### Defined in

[src/openiap.ts:1692](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1692)

___

### DeleteAgentPod

▸ **DeleteAgentPod**(`options`, `priority?`, `span?`): `Promise`<`void`\>

Remove an agent pod, found with GetAgentPods. Docker and Kubernetes only.
Requires invoke permission on agent

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `DeleteAgentPodOptions` | `undefined` | DeleteAgentPodOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`void`\>

void

#### Defined in

[src/openiap.ts:1671](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1671)

___

### DeleteMany

▸ **DeleteMany**(`options`, `priority?`, `span?`): `Promise`<`number`\>

Delete many documents from a collection based on a query.
Will return 0 if no documents are deleted.

**`Example`**

Delete all documents with name "find me" in entities collection
```typescript
const result = await client.DeleteMany({ query: { name: "find me" } });
console.log("Deleted " + result + " documents");
```
Delete all documents with type "invoice" in entities collection
```typescript
const result = await client.DeleteMany({ query: { _type: "invoice" } });
console.log("Deleted " + result + " documents");
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`DeleteManyOptions`](../modules.md#deletemanyoptions) | `undefined` | [DeleteManyOptions](../modules.md#deletemanyoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`number`\>

The number of deleted documents

#### Defined in

[src/openiap.ts:970](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L970)

___

### DeleteOne

▸ **DeleteOne**(`options`, `priority?`, `span?`): `Promise`<`number`\>

Delete one document from a collection.
Will throw an error if document does not exist or you don't have the right permissions.
if recursive is set to true, all asssoicated documents will be deleted as well.
Currently only user and customer objects in the "users" collection are supported for recursive deletion.

**`Example`**

Delete a document with id "643917fb153b7c2c1466fb21" in entities collection
```typescript
const result = await client.DeleteOne({ id: "643917fb153b7c2c1466fb21" } });
console.log("Deleted " + result + " documents");
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`DeleteOneOptions`](../modules.md#deleteoneoptions) | `undefined` | [DeleteOneOptions](../modules.md#deleteoneoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`number`\>

Number of deleted documents (will always be 1)

#### Defined in

[src/openiap.ts:938](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L938)

___

### DeletePackage

▸ **DeletePackage**(`options`, `priority?`, `span?`): `Promise`<`void`\>

Delete an agent Package.
Removes the associated file and then delete te package from the agents collection.
Requires delete permission on the Package

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `DeletePackageOptions` | `undefined` | DeletePackageOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`void`\>

void

#### Defined in

[src/openiap.ts:1769](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1769)

___

### DeleteWorkItemQueue

▸ **DeleteWorkItemQueue**(`options`, `priority?`, `span?`): `Promise`<`void`\>

Delete a workitem queue. Workitem queues are registered in the wiq collection. If queue has workitems in it, the request will fail, unless purge is set to true.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `DeleteWorkItemQueueOptions` | `undefined` | DeleteWorkItemQueueOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`void`\>

#### Defined in

[src/openiap.ts:1483](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1483)

___

### DeleteWorkitem

▸ **DeleteWorkitem**(`options`, `priority?`, `span?`): `Promise`<`void`\>

Delete one workitem and all associated files from a workitem queue.

**`Example`**

Delete a workitem
```typescript
client.DeleteWorkitem({ id: "64366f12cffb7419a89d5e10" });
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`DeleteWorkitemOptions`](../modules.md#deleteworkitemoptions) | `undefined` |  |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`void`\>

#### Defined in

[src/openiap.ts:1427](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1427)

___

### Distinct

▸ **Distinct**(`options`, `priority?`, `span?`): `Promise`<`string`[]\>

Finds the distinct values for a specified field across a single collection

**`Example`**

Get the distinct name of all documents with type "test" 
```typescript
const result = await client.Distinct({ collectionname: "entities", field: "name", query: { "_type": "test" } });
```

**`Example`**

Get the distinct types in the entities collection
```typescript
const result = await client.Distinct({ collectionname: "entities", field: "_type" });
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `DistinctOptions` | `undefined` | DistinctOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`string`[]\>

returns the results in an array

#### Defined in

[src/openiap.ts:698](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L698)

___

### DownloadFile

▸ **DownloadFile**(`options`): `Promise`<[`DownloadResponse`](../modules.md#downloadresponse)\>

Download a file from OpenIAP flow database, using the file id or file name. 
This uses streams to download file content, and is therefore not supported using REST interface.

#### Parameters

| Name | Type |
| :------ | :------ |
| `options` | [`DownloadFileOptions`](../modules.md#downloadfileoptions) |

#### Returns

`Promise`<[`DownloadResponse`](../modules.md#downloadresponse)\>

#### Defined in

[src/openiap.ts:1061](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1061)

___

### DropCollection

▸ **DropCollection**(`options`, `priority?`, `span?`): `Promise`<`void`\>

Drop a collection removing all data from the collection. Only users with admin rights can drop collections.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`DropCollectionOptions`](../modules.md#dropcollectionoptions) | `undefined` | [DropCollectionOptions](../modules.md#dropcollectionoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`void`\>

#### Defined in

[src/openiap.ts:511](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L511)

___

### DropIndex

▸ **DropIndex**(`options`, `priority?`, `span?`): `Promise`<`void`\>

Drop a MongoDB index from a collection.
Requires admins permission

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `DropIndexOptions` | `undefined` | DropIndexOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`void`\>

void

#### Defined in

[src/openiap.ts:1748](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1748)

___

### EnsureCustomer

▸ **EnsureCustomer**(`options`, `priority?`, `span?`): `Promise`<`EnsureCustomerResponse`\>

Create a collection removing all data from the collection. Only users with admin rights can Create collections.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `EnsureCustomerOptions` | `undefined` | EnsureCustomerOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`EnsureCustomerResponse`\>

#### Defined in

[src/openiap.ts:1544](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1544)

___

### FindOne

▸ **FindOne**<`T`\>(`options`, `priority?`, `span?`): `Promise`<`T`\>

Query a collection for data and return the first document

**`Example`**

Get the first document with type "test" from entities collection
```typescript
const result = await client.FindOne({ query: { "_type": "test" } });
```

**`Example`**

Get the first document with type "test" from entities collection and only return the name field
```typescript
const result = await client.FindOne({ collectionname: "entities", query: { "_type": "test" }, projection: { "name": 1 } });
```

**`Example`**

Get the first document with type "test" from entities collection and only return the name field and order by name
```typescript
const result = await client.FindOne({ collectionname: "entities", query: { "_type": "test" }, projection: { "name": 1 }, orderby: { "name": 1 } });
```

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`FindOneOptions`](../modules.md#findoneoptions) | `undefined` | [FindOneOptions](../modules.md#findoneoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`T`\>

a document matching the query

#### Defined in

[src/openiap.ts:601](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L601)

___

### GetAgentLog

▸ **GetAgentLog**(`options`, `priority?`, `span?`): `Promise`<`string`\>

Return the console output of an running agent, can be in docker, kubernetes or running remote.
Requires invoke permission on agent

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `GetAgentLogOptions` | `undefined` | GetAgentLogOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`string`\>

Return pods console output

#### Defined in

[src/openiap.ts:1628](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1628)

___

### GetAgentPods

▸ **GetAgentPods**(`options`, `priority?`, `span?`): `Promise`<`any`[]\>

Return a list of pods for an running agent. Docker and Kubernetes only.
Requires invoke permission on agent

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `GetAgentPodsOptions` | `undefined` | GetAgentPodsOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`any`[]\>

Array of pods

#### Defined in

[src/openiap.ts:1649](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1649)

___

### GetDocumentVersion

▸ **GetDocumentVersion**<`T`\>(`options`, `priority?`, `span?`): `Promise`<`T`[]\>

By default OpenIAP will keep history information about all data in the database.
This function will try and reconstruct the document at it was at a given version. 
This can be used to restore data to a previous state or even restore deleted data.

**`Example`**

Get the document with id "643917fb153b7c2c1466fb21" from entities collection at version 1
```typescript
const result = await client.GetDocumentVersion({ id: "643917fb153b7c2c1466fb21", version: 1 });
```

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`GetDocumentVersionOptions`](../modules.md#getdocumentversionoptions) | `undefined` | [GetDocumentVersionOptions](../modules.md#getdocumentversionoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`T`[]\>

The reconstructed document

#### Defined in

[src/openiap.ts:636](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L636)

___

### GetElement

▸ **GetElement**(`xpath`): `Promise`<`string`\>

Dummy function used to test the connection to the server.

#### Parameters

| Name | Type |
| :------ | :------ |
| `xpath` | `string` |

#### Returns

`Promise`<`string`\>

xpath with added text

#### Defined in

[src/openiap.ts:1048](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1048)

___

### GetIndexes

▸ **GetIndexes**(`options`, `priority?`, `span?`): `Promise`<`any`[]\>

#### Parameters

| Name | Type | Default value |
| :------ | :------ | :------ |
| `options` | `GetIndexesOptions` | `undefined` |
| `priority` | `number` | `2` |
| `span` | `Span` | `null` |

#### Returns

`Promise`<`any`[]\>

#### Defined in

[src/openiap.ts:1705](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1705)

___

### InsertMany

▸ **InsertMany**<`T`\>(`options`, `priority?`, `span?`): `Promise`<`T`[]\>

Bulk insert multiple documents into a collection, this is faster than using InsertOne multiple times.

**`Example`**

Insert multiple documents with type "test" into entities collection
```typescript
const result = await client.InsertMany({ collectionname: "entities", items: [{ "_type": "test", name: "find me" }, { "_type": "test", name: "find me too" }] });
```

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`InsertManyOptions`](../modules.md#insertmanyoptions) | `undefined` | [InsertManyOptions](../modules.md#insertmanyoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`T`[]\>

When skipresults is false, will return an array of the documents that was created, including the _id field

#### Defined in

[src/openiap.ts:778](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L778)

___

### InsertOne

▸ **InsertOne**<`T`\>(`options`, `priority?`, `span?`): `Promise`<`T`\>

Insert a document into a collection

**`Example`**

Insert a document with type "test" into entities collection
```typescript
const result = await client.InsertOne({ collectionname: "entities", item: { "_type": "test", name: "find me" } });
```

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`InsertOneOptions`](../modules.md#insertoneoptions) | `undefined` | [InsertOneOptions](../modules.md#insertoneoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`T`\>

The object that was created, including the _id field

#### Defined in

[src/openiap.ts:752](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L752)

___

### InsertOrUpdateMany

▸ **InsertOrUpdateMany**<`T`\>(`options`, `priority?`, `span?`): `Promise`<`T`[]\>

Will match all documents toward a collection using the uniqeness parameters ( _id if left out ) and update it if it exists, or insert it if it does not exist.
Will trhow an error if more than one document exists that matches the uniqeness parameters.
This will use bulk operations to speed up the process.

**`Example`**

Insert or update multiple invoice documents in entities collection
```typescript
const invoices = [{ "_type": "invoice", invoiceid: "1234", name: "find me" }, { "_type": "invoice", invoiceid: "1235", name: "find me too" }]
const result = await client.InsertOrUpdateMany({ items: invoices, uniqeness: ["invoiceid"] });
console.log("Inserted document with id: " + result[0]._id + " and name: " + result[0].name);
console.log("Inserted document with id: " + result[1]._id + " and name: " + result[1].name);

const same_invoice = [{ "_type": "invoice", invoiceid: "1234", name: "Can you still find me?"}, { "_type": "invoice", invoiceid: "1235", name: "Can you still find me too?"}]
const updated = await client.InsertOrUpdateMany({ items: same_invoice, uniqeness: ["invoiceid"] });
console.log("Updated document with id: " + updated[0]._id + " and new name: " + updated[0].name);
console.log("Updated document with id: " + updated[1]._id + " and new name: " + updated[1].name);
```

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`InsertOrUpdateManyOptions`](../modules.md#insertorupdatemanyoptions) | `undefined` | [InsertOrUpdateManyOptions](../modules.md#insertorupdatemanyoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`T`[]\>

The updated or inserted documents including the _id field

#### Defined in

[src/openiap.ts:908](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L908)

___

### InsertOrUpdateOne

▸ **InsertOrUpdateOne**<`T`\>(`options`, `priority?`, `span?`): `Promise`<`T`\>

Will match a document in a collection on the uniqeness parameters ( _id if left out ) and update it if it exists, or insert it if it does not exist.
Will trhow an error if more than one document exists that matches the uniqeness parameters.

**`Example`**

Insert or update a document with invoiceid "1234" in entities collection
```typescript
const result = await client.InsertOrUpdateOne({ item: { "_type": "invoice", invoiceid: "1234", name: "find me" }, uniqeness: ["invoiceid"] });
console.log("Inserted document with id: " + result._id + " and name: " + result.name);

const same_invoice = { "_type": "invoice", invoiceid: "1234", name: "Can you still find me?"}
const updated = await client.InsertOrUpdateOne({ item: same_invoice, uniqeness: ["invoiceid"] });
console.log("Updated document with id: " + updated._id + " and new name: " + updated.name);
```

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`InsertOrUpdateOneOptions`](../modules.md#insertorupdateoneoptions) | `undefined` | [InsertOrUpdateOneOptions](../modules.md#insertorupdateoneoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`T`\>

The updated or inserted document including the _id field

#### Defined in

[src/openiap.ts:872](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L872)

___

### InvokeOpenRPA

▸ **InvokeOpenRPA**<`T`\>(`options`, `priority?`, `span?`): `Promise`<`T`\>

Invoke an OpenRPA workflow on a robot or a role with multiple robots in.
At writing, this command is only supprted using OpenAPI endpoint

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `InvokeOpenRPAOptions` | `undefined` | InvokeOpenRPAOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`T`\>

null if rpc is false, else the result of the workflow if workflow has any inout/out parameters

#### Defined in

[src/openiap.ts:1565](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1565)

___

### ListCollections

▸ **ListCollections**(`options?`, `priority?`, `span?`): `Promise`<`any`[]\>

Returns a list of all known collections. By default filtering out history collectins.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`ListCollectionsOptions`](../modules.md#listcollectionsoptions) | `{}` | [ListCollectionsOptions](../modules.md#listcollectionsoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`any`[]\>

#### Defined in

[src/openiap.ts:492](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L492)

___

### Ping

▸ **Ping**(): `Promise`<`void`\>

Used internally to send a ping message to server, to keep the connection alive.
Only used if server require pings, or if the client is configured to send pings using [DoPing](config.md#doping)

#### Returns

`Promise`<`void`\>

#### Defined in

[src/openiap.ts:414](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L414)

___

### PopWorkitem

▸ **PopWorkitem**(`options`, `priority?`, `span?`): `Promise`<[`Workitem`](../modules.md#workitem)\>

Pop an item of a workitem queue. An items aviailable in the queue will be determined by it's status, retry time and runat time steamp.
If multiple items are available, the items will be fatched based on each wrkitem's priority field.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`PopWorkitemOptions`](../modules.md#popworkitemoptions) | `undefined` |  |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<[`Workitem`](../modules.md#workitem)\>

If no workitem is available, this will return null.

#### Defined in

[src/openiap.ts:1352](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1352)

___

### PushWorkitem

▸ **PushWorkitem**(`options`, `priority?`, `span?`): `Promise`<[`Workitem`](../modules.md#workitem)\>

Push a workitem to a workqueue. Workitem can be processed by a worker after calling [PopWorkitem](openiap.md#popworkitem)

**`See`**

 - [PopWorkitem](openiap.md#popworkitem)
 - [PushWorkitems](openiap.md#pushworkitems)

**`Example`**

Push a workitem to myworkqueue
```typescript
const workitem = await client.PushWorkitem({ wiq: "myworkqueue", payload: { "hello": "world" } });
console.log("Pushed workitem with id " + workitem._id);
```

**`Example`**

Push a workitem with a file to myworkqueue 
```typescript
import * as path  from 'path';
import * as fs  from "fs";
import * as pako from 'pako';
// ....
const filepath = "/path/data.csv";
const filename = path.basename(filepath);
const workitem = await client.PushWorkitem({
 payload: {"name": "test " + filename}, wiq: "q2", name: "file test " + filename,
  files: [{ _id:"", filename, compressed: true, file: pako.deflate(fs.readFileSync(filepath, null)) }]});
console.log("Pushed workitem with id " + workitem._id);

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`PushWorkitemOptions`](../modules.md#pushworkitemoptions) | `undefined` |  |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<[`Workitem`](../modules.md#workitem)\>

Returns the workitem that was pushed, including the workitem id

#### Defined in

[src/openiap.ts:1285](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1285)

___

### PushWorkitems

▸ **PushWorkitems**(`options`, `priority?`, `span?`): `Promise`<[`Workitem`](../modules.md#workitem)[]\>

Push multiple workitems to a workqueue. Workitems can be processed by a worker after calling [PopWorkitem](openiap.md#popworkitem)

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`PushWorkitemsOptions`](../modules.md#pushworkitemsoptions) | `undefined` |  |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<[`Workitem`](../modules.md#workitem)[]\>

an array of workitems that was pushed, including the workitem id's

#### Defined in

[src/openiap.ts:1314](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1314)

___

### Query

▸ **Query**<`T`\>(`options`, `priority?`, `span?`): `Promise`<`T`[]\>

Query a collection for data

**`Example`**

Get all documents with type "test" from entities collection
```typescript
const result = await client.Query({ query: { "_type": "test" } });
```

**`Example`**

Get all documents with type "test" from entities collection and only return the name field
```typescript
const result = await client.Query({ collectionname: "entities", query: { "_type": "test" }, projection: { "name": 1 } });
```

**`Example`**

Get all documents with type "test" from entities collection and only return the name field and order by name
```typescript
const result = await client.Query({ collectionname: "entities", query: { "_type": "test" }, projection: { "name": 1 }, orderby: { "name": 1 } });
```

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`QueryOptions`](../modules.md#queryoptions) | `undefined` | [QueryOptions](../modules.md#queryoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`T`[]\>

an array of documents matching the query

#### Defined in

[src/openiap.ts:563](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L563)

___

### QueueMessage

▸ **QueueMessage**(`options`, `rpc?`, `priority?`, `span?`): `Promise`<`any`\>

Send message to queue or exchange. If recevied sends a reply back, set rpc = true to recevied response as return value.
Be aware, right now there is no timeout on the wait, so if recevier never sends a reply it will hang for ever

**`See`**

 - [RegisterQueue](openiap.md#registerqueue)
 - [RegisterExchange](openiap.md#registerexchange)

**`Example`**

Send message to myqueue and wait for reply, then dump the result to console
```typescript
const result = await client.QueueMessage({ queuename: "myqueue", data: { "hello": "world" } }, true);
console.log("result from queue " + JSON.stringify(result, null, 2));
```

**`Example`**

Send message to myexchange
```typescript
await client.QueueMessage({ exchangename: "myexchange", data: { "hello": "world" } }, false);
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`QueueMessageOptions`](../modules.md#queuemessageoptions) | `undefined` |  |
| `rpc` | `boolean` | `false` |  |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`any`\>

If rpc is trye, will return the reply from the queue. If rpc is false, will return null when server has received the message

#### Defined in

[src/openiap.ts:1218](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1218)

___

### RegisterExchange

▸ **RegisterExchange**(`options`, `callback`, `priority?`, `span?`): `Promise`<`string`\>

Register an exchange and a message queue and consume it. Exchange's are registered in the mq collection. 
This uses streams to notify client about messages, and is therefore not supported using REST interface.

**`See`**

 - [QueueMessage](openiap.md#queuemessage)
 - [UnRegisterQueue](openiap.md#unregisterqueue)

**`Example`**

```typescript
const queuename = await client.RegisterExchange({ exchange: "myexchange" }, (msg, payload, user, jwt) => {
  console.log(JSON.stringify(payload, null, 2));
});
console.log("registered exchange myexchange and is consuming it using queue " + queuename);
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`RegisterExchangeOptions`](../modules.md#registerexchangeoptions) | `undefined` |  |
| `callback` | (`msg`: [`QueueEvent`](../modules.md#queueevent), `payload`: `any`, `user`: `any`, `jwt`: `string`) => `any` | `undefined` |  |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`string`\>

Returns the queue name, used to consume the exchange. Use this when unregistering the exchange with [UnRegisterQueue](openiap.md#unregisterqueue)

#### Defined in

[src/openiap.ts:1148](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1148)

___

### RegisterQueue

▸ **RegisterQueue**(`options`, `callback`, `priority?`, `span?`): `Promise`<`string`\>

Register and consume a Message Queue. Queues are registered in the mq collection. 
If no queue name is provided, a random queue name is generated.
This uses streams to notify client about messages, and is therefore not supported using REST interface.

**`See`**

 - [QueueMessage](openiap.md#queuemessage)
 - [UnRegisterQueue](openiap.md#unregisterqueue)

**`Example`**

```typescript
const queuename = await client.RegisterQueue({ queuename: "myqueue" }, (msg, payload, user, jwt) => {
  console.log(JSON.stringify(payload, null, 2));
  if(payload == null) payload = {}
  payload.result = true
  // If returning a onject, it will be sent back to the sender of the message, if caller requested a response using rpc = true. 
  return payload;
});
console.log("registered queue " + queuename);
```

#### Parameters

| Name | Type | Default value |
| :------ | :------ | :------ |
| `options` | [`RegisterQueueOptions`](../modules.md#registerqueueoptions) | `undefined` |
| `callback` | (`msg`: [`QueueEvent`](../modules.md#queueevent), `payload`: `any`, `user`: `any`, `jwt`: `string`) => `any` | `undefined` |
| `priority` | `number` | `2` |
| `span` | `Span` | `null` |

#### Returns

`Promise`<`string`\>

Returns the queue name. Use this name to send messages to the queue. Also use this to unregister the queue with [UnRegisterQueue](openiap.md#unregisterqueue)

#### Defined in

[src/openiap.ts:1110](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1110)

___

### Signin

▸ **Signin**(`options`, `span?`): `Promise`<[`SigninResponse`](../modules.md#signinresponse)\>

By default we use crendetials from the connection string or from jwt environment variable.
But you can also call Signin to login with a username and password or with a jwt token.
This function can also be used to validate credentials without changing the current credentials by setting 
[validateonly](../modules.md#validateonly) to true.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`SigninOptions`](../modules.md#signinoptions) | `undefined` | [SigninOptions](../modules.md#signinoptions) |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<[`SigninResponse`](../modules.md#signinresponse)\>

#### Defined in

[src/openiap.ts:448](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L448)

___

### StartAgent

▸ **StartAgent**(`options`, `priority?`, `span?`): `Promise`<`void`\>

Start an agent inside Docker or Kubernetes
Requires invoke permission on agent

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `StartAgentOptions` | `undefined` | StartAgentOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`void`\>

void

#### Defined in

[src/openiap.ts:1588](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1588)

___

### StopAgent

▸ **StopAgent**(`options`, `priority?`, `span?`): `Promise`<`void`\>

Stop an agent running inside Docker or Kubernetes
Requires invoke permission on agent

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `StopAgentOptions` | `undefined` | StopAgentOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`void`\>

void

#### Defined in

[src/openiap.ts:1608](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1608)

___

### UnRegisterQueue

▸ **UnRegisterQueue**(`options`, `priority?`, `span?`): `Promise`<`void`\>

Tell server to close queue and stop receving message from the queue ( or queue consuming an exchange )

**`See`**

 - [RegisterQueue](openiap.md#registerqueue)
 - [RegisterExchange](openiap.md#registerexchange)

**`Example`**

```typescript
const queuename = await client.RegisterExchange({ exchange: "myexchange" }, async (msg, payload, user, jwt) => {
  console.log(JSON.stringify(payload, null, 2));
  await client.UnRegisterQueue({ queuename: queuename });
  console.log("unregistered queue " + queuename);
});
console.log("registered exchange myexchange and is consuming it using queue " + queuename);
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`UnRegisterQueueOptions`](../modules.md#unregisterqueueoptions) | `undefined` |  |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`void`\>

#### Defined in

[src/openiap.ts:1182](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1182)

___

### UnWatch

▸ **UnWatch**(`options`, `priority?`, `span?`): `Promise`<`void`\>

Unregister a change stream ( watch ) created with [Watch](openiap.md#watch) to stop receiving notifications from the watch.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`UnWatchOptions`](../modules.md#unwatchoptions) | `undefined` |  |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`void`\>

#### Defined in

[src/openiap.ts:1029](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1029)

___

### UpdateDocument

▸ **UpdateDocument**(`options`, `priority?`, `span?`): `Promise`<[`UpdateResult`](../modules.md#updateresult)\>

Run an update command on a collection, to update one or more documents matching a query.
See https://docs.mongodb.com/manual/reference/operator/update/ for more information on the update operators.

**`See`**

https://docs.mongodb.com/manual/reference/operator/update/

**`Example`**

Update all documents with type "test" in entities collection
```typescript
const result = await client.UpdateDocument({ collectionname: "entities", query: { "_type": "test" }, document: { "$set": { "name": "find me" } } });
console.log("Updated " + result.matchedCount + " documents");
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`UpdateDocumentOptions`](../modules.md#updatedocumentoptions) | `undefined` | [UpdateDocumentOptions](../modules.md#updatedocumentoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<[`UpdateResult`](../modules.md#updateresult)\>

An object with update statistics see [UpdateResult](../interfaces/UpdateResult.md)

#### Defined in

[src/openiap.ts:839](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L839)

___

### UpdateOne

▸ **UpdateOne**<`T`\>(`options`, `priority?`, `span?`): `Promise`<`T`\>

Update ( replace ) an existing document in a collection.
Any fields that starts with underscoore will be preserved. This is to prevent the system from overwriting fields that are used by the system.
So if you update a document but leave out any of the existing _ fields, they will be added back to the document.

**`Example`**

Update a document with type "test" in entities collection
```typescript
const result = await client.InsertOne({ item: { "_type": "test", name: "find me" } });
console.log("Inserted document with id: " + result._id + " and name: " + result.name);
result.name = "Can you still find me?"
const updated = await client.UpdateOne({ item: result });
console.log("Updated document with id: " + updated._id + " and name: " + updated.name);
```

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`UpdateOneOptions`](../modules.md#updateoneoptions) | `undefined` | [UpdateOneOptions](../modules.md#updateoneoptions) |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`T`\>

Returns the document that was updated

#### Defined in

[src/openiap.ts:810](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L810)

___

### UpdateWorkItemQueue

▸ **UpdateWorkItemQueue**(`options`, `priority?`, `span?`): `Promise`<[`WorkItemQueue`](../modules.md#workitemqueue)\>

Create a new workitem queue. Workitem queues are registered in the wiq collection. To delete all items from qyueue, set purge to true.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | `UpdateWorkItemQueueOptions` | `undefined` | UpdateWorkItemQueueOptions |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<[`WorkItemQueue`](../modules.md#workitemqueue)\>

#### Defined in

[src/openiap.ts:1464](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1464)

___

### UpdateWorkitem

▸ **UpdateWorkitem**(`options`, `priority?`, `span?`): `Promise`<[`Workitem`](../modules.md#workitem)\>

Update an existing workitem. Workitem can be fetched using [PopWorkitem](openiap.md#popworkitem). Use this to update the status of a workitem.
You can also update the payload, and update or add files to the workitem.

**`See`**

[PopWorkitem](openiap.md#popworkitem)

**`Example`**

Update a workitem
```typescript
const workitem = await client.PopWorkitem({ wiq: "purchase_orders" }); // Will update the workitem state to processing
if(workitem == null) return;
await new Promise(resolve => setTimeout(resolve, 1000)); // simulate processing 
if(workitem.payload == null) workitem.payload = {}
workitem.payload.transaction = "ID45434" // update payload
workitem.status = "successful" // must be successful, processing or retry
await client.UpdateWorkitem({ workitem }); // update workitem
console.log("Updated workitem with id " + workitem._id);
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`UpdateWorkitemOptions`](../modules.md#updateworkitemoptions) | `undefined` |  |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<[`Workitem`](../modules.md#workitem)\>

Returns the updated workitem

#### Defined in

[src/openiap.ts:1394](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1394)

___

### UploadFile

▸ **UploadFile**(`options`): `Promise`<[`UploadResponse`](../modules.md#uploadresponse)\>

Upload a file to OpenIAP flow database.
This uses streams to download file content, and is therefore not supported using REST interface.

**`See`**

 - [UploadResponse](../interfaces/UploadResponse.md)
 - [UploadFileOptions](../modules.md#uploadfileoptions)

**`Example`**

Upload test.txt from current folder to OpenIAP flow database
```typescript
const res = await client.UploadFile({ filename: "test.txt" });
console.log("file upladed with id " + res.id);
```

#### Parameters

| Name | Type |
| :------ | :------ |
| `options` | [`UploadFileOptions`](../modules.md#uploadfileoptions) |

#### Returns

`Promise`<[`UploadResponse`](../modules.md#uploadresponse)\>

Server response, including the file id

#### Defined in

[src/openiap.ts:1081](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L1081)

___

### Watch

▸ **Watch**(`options`, `callback`, `priority?`, `span?`): `Promise`<`string`\>

Register a change stream ( watch ) on a collection. Use paths to narrow the scope of the watch.
The callback will be called for each document that matches the paths when ever it is inserted, updated or deleted from the database
This uses streams to notify client about changes, and is therefore not supported using REST interface.

**`Example`**

```ts
const watchid = await db.Watch({ collectionname: "entities", paths: ["$.[?(@._type == 'test')]"] }, (operation, document) => {
    console.log(operation + " on " + document.name);
});
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `options` | [`WatchOptions`](../modules.md#watchoptions) | `undefined` |  |
| `callback` | (`operation`: `string`, `document`: `any`) => `void` | `undefined` |  |
| `priority` | `number` | `2` | Message priority, the higher the number the higher the priority. Default is 2, 3 or higher requeires updates to server configuration |
| `span` | `Span` | `null` | - |

#### Returns

`Promise`<`string`\>

server id assigned to the watch. Used with [UnWatch](openiap.md#unwatch) to stop receiving notifications from the watch.

#### Defined in

[src/openiap.ts:998](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L998)

___

### \_\_server\_pinger

▸ **__server_pinger**(): `void`

#### Returns

`void`

#### Defined in

[src/openiap.ts:176](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L176)

___

### addListener

▸ **addListener**(`eventName`, `listener`): [`openiap`](openiap.md)

Alias for `emitter.on(eventName, listener)`.

**`Since`**

v0.1.26

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `string` \| `symbol` |
| `listener` | (...`args`: `any`[]) => `void` |

#### Returns

[`openiap`](openiap.md)

#### Inherited from

EventEmitter.addListener

#### Defined in

node_modules/@types/node/events.d.ts:354

___

### cliOnConnected

▸ `Private` **cliOnConnected**(`client`): `Promise`<`void`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `client` | [`client`](client.md) |

#### Returns

`Promise`<`void`\>

#### Defined in

[src/openiap.ts:218](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L218)

___

### cliOnDisconnected

▸ `Private` **cliOnDisconnected**(`client`, `error`): `void`

#### Parameters

| Name | Type |
| :------ | :------ |
| `client` | [`client`](client.md) |
| `error` | `Error` |

#### Returns

`void`

#### Defined in

[src/openiap.ts:288](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L288)

___

### cliOnMessage

▸ `Private` **cliOnMessage**(`client`, `message`): `Promise`<`any`\>

Override this function to get notified when the client receives a message from the server.
This will only be called for messages that are not handled by the client it self.
Using EventMitter is also possible .on("message", (client, command, message) => {})

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `client` | [`client`](client.md) | Return client instance that received the message |
| `message` | [`Envelope`](../modules.md#envelope) | The message that was received |

#### Returns

`Promise`<`any`\>

#### Defined in

[src/openiap.ts:352](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L352)

___

### connect

▸ **connect**(`first?`): `Promise`<[`User`](../modules.md#user)\>

**`Example`**

```typescript
var client = new openiap();
client.connect().then(async (user) => {
   console.log("Logged in as " + user.username);
}).catch((err) => {
  console.log("Failed to login: " + err);
});

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `first` | `boolean` | `true` | Should be left out or used as true. Is used internally for controlling retry logic |

#### Returns

`Promise`<[`User`](../modules.md#user)\>

Returns the [User](../interfaces/User.md) object if login was successful, otherwise throws an error

#### Defined in

[src/openiap.ts:143](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L143)

___

### emit

▸ **emit**(`eventName`, `...args`): `boolean`

Synchronously calls each of the listeners registered for the event named`eventName`, in the order they were registered, passing the supplied arguments
to each.

Returns `true` if the event had listeners, `false` otherwise.

```js
const EventEmitter = require('events');
const myEmitter = new EventEmitter();

// First listener
myEmitter.on('event', function firstListener() {
  console.log('Helloooo! first listener');
});
// Second listener
myEmitter.on('event', function secondListener(arg1, arg2) {
  console.log(`event with parameters ${arg1}, ${arg2} in second listener`);
});
// Third listener
myEmitter.on('event', function thirdListener(...args) {
  const parameters = args.join(', ');
  console.log(`event with parameters ${parameters} in third listener`);
});

console.log(myEmitter.listeners('event'));

myEmitter.emit('event', 1, 2, 3, 4, 5);

// Prints:
// [
//   [Function: firstListener],
//   [Function: secondListener],
//   [Function: thirdListener]
// ]
// Helloooo! first listener
// event with parameters 1, 2 in second listener
// event with parameters 1, 2, 3, 4, 5 in third listener
```

**`Since`**

v0.1.26

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `string` \| `symbol` |
| `...args` | `any`[] |

#### Returns

`boolean`

#### Inherited from

EventEmitter.emit

#### Defined in

node_modules/@types/node/events.d.ts:610

___

### eventNames

▸ **eventNames**(): (`string` \| `symbol`)[]

Returns an array listing the events for which the emitter has registered
listeners. The values in the array are strings or `Symbol`s.

```js
const EventEmitter = require('events');
const myEE = new EventEmitter();
myEE.on('foo', () => {});
myEE.on('bar', () => {});

const sym = Symbol('symbol');
myEE.on(sym, () => {});

console.log(myEE.eventNames());
// Prints: [ 'foo', 'bar', Symbol(symbol) ]
```

**`Since`**

v6.0.0

#### Returns

(`string` \| `symbol`)[]

#### Inherited from

EventEmitter.eventNames

#### Defined in

node_modules/@types/node/events.d.ts:669

___

### getMaxListeners

▸ **getMaxListeners**(): `number`

Returns the current max listener value for the `EventEmitter` which is either
set by `emitter.setMaxListeners(n)` or defaults to [defaultMaxListeners](openiap.md#defaultmaxlisteners).

**`Since`**

v1.0.0

#### Returns

`number`

#### Inherited from

EventEmitter.getMaxListeners

#### Defined in

node_modules/@types/node/events.d.ts:526

___

### listenerCount

▸ **listenerCount**(`eventName`): `number`

Returns the number of listeners listening to the event named `eventName`.

**`Since`**

v3.2.0

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `eventName` | `string` \| `symbol` | The name of the event being listened for |

#### Returns

`number`

#### Inherited from

EventEmitter.listenerCount

#### Defined in

node_modules/@types/node/events.d.ts:616

___

### listeners

▸ **listeners**(`eventName`): `Function`[]

Returns a copy of the array of listeners for the event named `eventName`.

```js
server.on('connection', (stream) => {
  console.log('someone connected!');
});
console.log(util.inspect(server.listeners('connection')));
// Prints: [ [Function] ]
```

**`Since`**

v0.1.26

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `string` \| `symbol` |

#### Returns

`Function`[]

#### Inherited from

EventEmitter.listeners

#### Defined in

node_modules/@types/node/events.d.ts:539

___

### off

▸ **off**(`eventName`, `listener`): [`openiap`](openiap.md)

Alias for `emitter.removeListener()`.

**`Since`**

v10.0.0

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `string` \| `symbol` |
| `listener` | (...`args`: `any`[]) => `void` |

#### Returns

[`openiap`](openiap.md)

#### Inherited from

EventEmitter.off

#### Defined in

node_modules/@types/node/events.d.ts:499

___

### on

▸ **on**(`eventName`, `listener`): [`openiap`](openiap.md)

Adds the `listener` function to the end of the listeners array for the
event named `eventName`. No checks are made to see if the `listener` has
already been added. Multiple calls passing the same combination of `eventName`and `listener` will result in the `listener` being added, and called, multiple
times.

```js
server.on('connection', (stream) => {
  console.log('someone connected!');
});
```

Returns a reference to the `EventEmitter`, so that calls can be chained.

By default, event listeners are invoked in the order they are added. The`emitter.prependListener()` method can be used as an alternative to add the
event listener to the beginning of the listeners array.

```js
const myEE = new EventEmitter();
myEE.on('foo', () => console.log('a'));
myEE.prependListener('foo', () => console.log('b'));
myEE.emit('foo');
// Prints:
//   b
//   a
```

**`Since`**

v0.1.101

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `eventName` | `string` \| `symbol` | The name of the event. |
| `listener` | (...`args`: `any`[]) => `void` | The callback function |

#### Returns

[`openiap`](openiap.md)

#### Inherited from

EventEmitter.on

#### Defined in

node_modules/@types/node/events.d.ts:385

___

### onConnectGaveUp

▸ **onConnectGaveUp**(`client`): `void`

#### Parameters

| Name | Type |
| :------ | :------ |
| `client` | [`openiap`](openiap.md) |

#### Returns

`void`

#### Defined in

[src/openiap.ts:286](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L286)

___

### onConnected

▸ **onConnected**(`client`): `Promise`<`void`\>

Override this function to add logic executed when the client has connected to the server.
If credentails has been set, the client will automatically login before calling this function
Using EventMitter is also possible using client.on("connected", (client) => {})

**`Example`**

using onConnected override
```typescript
var client = new openiap();
client.onConnected = (client) => {
  console.log("Connected to server");
}
client.connect();
```

**`Example`**

using EventEmitter. Remember to remove the listener when done to avoid memory leaks
```typescript
var client = new openiap();
client.on("connected", (client) => {
 console.log("Connected to server");
});
client.connect();
```

#### Parameters

| Name | Type |
| :------ | :------ |
| `client` | [`openiap`](openiap.md) |

#### Returns

`Promise`<`void`\>

#### Defined in

[src/openiap.ts:216](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L216)

___

### onDisconnected

▸ **onDisconnected**(`client`, `error`): `void`

Override this function to add logic executed when the client has disconnected from the server.
Using EventMitter is also possible .on("disconnected", (client, error) => {})

**`Example`**

using onConnected override
```typescript
var client = new openiap();
client.onDisconnected = (client, err) => {
  console.log("Disconnected from server");
}
client.connect();
```

**`Example`**

using EventEmitter. Remember to remove the listener when done to avoid memory leaks
```typescript
var client = new openiap();
client.on("disconnected", (client, err) => {
 console.log("Disconnected from server");
});
client.connect();
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `client` | [`openiap`](openiap.md) | Return client instance that disconnected |
| `error` | `Error` | If the disconnect was caused by an error, this will contain the error object |

#### Returns

`void`

#### Defined in

[src/openiap.ts:284](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L284)

___

### once

▸ **once**(`eventName`, `listener`): [`openiap`](openiap.md)

Adds a **one-time**`listener` function for the event named `eventName`. The
next time `eventName` is triggered, this listener is removed and then invoked.

```js
server.once('connection', (stream) => {
  console.log('Ah, we have our first user!');
});
```

Returns a reference to the `EventEmitter`, so that calls can be chained.

By default, event listeners are invoked in the order they are added. The`emitter.prependOnceListener()` method can be used as an alternative to add the
event listener to the beginning of the listeners array.

```js
const myEE = new EventEmitter();
myEE.once('foo', () => console.log('a'));
myEE.prependOnceListener('foo', () => console.log('b'));
myEE.emit('foo');
// Prints:
//   b
//   a
```

**`Since`**

v0.3.0

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `eventName` | `string` \| `symbol` | The name of the event. |
| `listener` | (...`args`: `any`[]) => `void` | The callback function |

#### Returns

[`openiap`](openiap.md)

#### Inherited from

EventEmitter.once

#### Defined in

node_modules/@types/node/events.d.ts:414

___

### prependListener

▸ **prependListener**(`eventName`, `listener`): [`openiap`](openiap.md)

Adds the `listener` function to the _beginning_ of the listeners array for the
event named `eventName`. No checks are made to see if the `listener` has
already been added. Multiple calls passing the same combination of `eventName`and `listener` will result in the `listener` being added, and called, multiple
times.

```js
server.prependListener('connection', (stream) => {
  console.log('someone connected!');
});
```

Returns a reference to the `EventEmitter`, so that calls can be chained.

**`Since`**

v6.0.0

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `eventName` | `string` \| `symbol` | The name of the event. |
| `listener` | (...`args`: `any`[]) => `void` | The callback function |

#### Returns

[`openiap`](openiap.md)

#### Inherited from

EventEmitter.prependListener

#### Defined in

node_modules/@types/node/events.d.ts:634

___

### prependOnceListener

▸ **prependOnceListener**(`eventName`, `listener`): [`openiap`](openiap.md)

Adds a **one-time**`listener` function for the event named `eventName` to the _beginning_ of the listeners array. The next time `eventName` is triggered, this
listener is removed, and then invoked.

```js
server.prependOnceListener('connection', (stream) => {
  console.log('Ah, we have our first user!');
});
```

Returns a reference to the `EventEmitter`, so that calls can be chained.

**`Since`**

v6.0.0

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `eventName` | `string` \| `symbol` | The name of the event. |
| `listener` | (...`args`: `any`[]) => `void` | The callback function |

#### Returns

[`openiap`](openiap.md)

#### Inherited from

EventEmitter.prependOnceListener

#### Defined in

node_modules/@types/node/events.d.ts:650

___

### rawListeners

▸ **rawListeners**(`eventName`): `Function`[]

Returns a copy of the array of listeners for the event named `eventName`,
including any wrappers (such as those created by `.once()`).

```js
const emitter = new EventEmitter();
emitter.once('log', () => console.log('log once'));

// Returns a new Array with a function `onceWrapper` which has a property
// `listener` which contains the original listener bound above
const listeners = emitter.rawListeners('log');
const logFnWrapper = listeners[0];

// Logs "log once" to the console and does not unbind the `once` event
logFnWrapper.listener();

// Logs "log once" to the console and removes the listener
logFnWrapper();

emitter.on('log', () => console.log('log persistently'));
// Will return a new Array with a single function bound by `.on()` above
const newListeners = emitter.rawListeners('log');

// Logs "log persistently" twice
newListeners[0]();
emitter.emit('log');
```

**`Since`**

v9.4.0

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `string` \| `symbol` |

#### Returns

`Function`[]

#### Inherited from

EventEmitter.rawListeners

#### Defined in

node_modules/@types/node/events.d.ts:569

___

### removeAllListeners

▸ **removeAllListeners**(`event?`): [`openiap`](openiap.md)

Removes all listeners, or those of the specified `eventName`.

It is bad practice to remove listeners added elsewhere in the code,
particularly when the `EventEmitter` instance was created by some other
component or module (e.g. sockets or file streams).

Returns a reference to the `EventEmitter`, so that calls can be chained.

**`Since`**

v0.1.26

#### Parameters

| Name | Type |
| :------ | :------ |
| `event?` | `string` \| `symbol` |

#### Returns

[`openiap`](openiap.md)

#### Inherited from

EventEmitter.removeAllListeners

#### Defined in

node_modules/@types/node/events.d.ts:510

___

### removeListener

▸ **removeListener**(`eventName`, `listener`): [`openiap`](openiap.md)

Removes the specified `listener` from the listener array for the event named`eventName`.

```js
const callback = (stream) => {
  console.log('someone connected!');
};
server.on('connection', callback);
// ...
server.removeListener('connection', callback);
```

`removeListener()` will remove, at most, one instance of a listener from the
listener array. If any single listener has been added multiple times to the
listener array for the specified `eventName`, then `removeListener()` must be
called multiple times to remove each instance.

Once an event is emitted, all listeners attached to it at the
time of emitting are called in order. This implies that any`removeListener()` or `removeAllListeners()` calls _after_ emitting and _before_ the last listener finishes execution
will not remove them from`emit()` in progress. Subsequent events behave as expected.

```js
const myEmitter = new MyEmitter();

const callbackA = () => {
  console.log('A');
  myEmitter.removeListener('event', callbackB);
};

const callbackB = () => {
  console.log('B');
};

myEmitter.on('event', callbackA);

myEmitter.on('event', callbackB);

// callbackA removes listener callbackB but it will still be called.
// Internal listener array at time of emit [callbackA, callbackB]
myEmitter.emit('event');
// Prints:
//   A
//   B

// callbackB is now removed.
// Internal listener array [callbackA]
myEmitter.emit('event');
// Prints:
//   A
```

Because listeners are managed using an internal array, calling this will
change the position indices of any listener registered _after_ the listener
being removed. This will not impact the order in which listeners are called,
but it means that any copies of the listener array as returned by
the `emitter.listeners()` method will need to be recreated.

When a single function has been added as a handler multiple times for a single
event (as in the example below), `removeListener()` will remove the most
recently added instance. In the example the `once('ping')`listener is removed:

```js
const ee = new EventEmitter();

function pong() {
  console.log('pong');
}

ee.on('ping', pong);
ee.once('ping', pong);
ee.removeListener('ping', pong);

ee.emit('ping');
ee.emit('ping');
```

Returns a reference to the `EventEmitter`, so that calls can be chained.

**`Since`**

v0.1.26

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `string` \| `symbol` |
| `listener` | (...`args`: `any`[]) => `void` |

#### Returns

[`openiap`](openiap.md)

#### Inherited from

EventEmitter.removeListener

#### Defined in

node_modules/@types/node/events.d.ts:494

___

### setMaxListeners

▸ **setMaxListeners**(`n`): [`openiap`](openiap.md)

By default `EventEmitter`s will print a warning if more than `10` listeners are
added for a particular event. This is a useful default that helps finding
memory leaks. The `emitter.setMaxListeners()` method allows the limit to be
modified for this specific `EventEmitter` instance. The value can be set to`Infinity` (or `0`) to indicate an unlimited number of listeners.

Returns a reference to the `EventEmitter`, so that calls can be chained.

**`Since`**

v0.3.5

#### Parameters

| Name | Type |
| :------ | :------ |
| `n` | `number` |

#### Returns

[`openiap`](openiap.md)

#### Inherited from

EventEmitter.setMaxListeners

#### Defined in

node_modules/@types/node/events.d.ts:520

___

### stringify

▸ **stringify**(`object`): `string`

Wrapper around JSON.stringify to allow serialiszing object with regular expressions

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `object` | `any` | Object to serialize |

#### Returns

`string`

#### Defined in

[src/openiap.ts:427](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L427)

___

### GetUniqueIdentifier

▸ `Static` **GetUniqueIdentifier**(): `string`

Used to generate a unique identifier, used for example when creating new packages.

#### Returns

`string`

A unique identifier

#### Defined in

[src/openiap.ts:338](https://github.com/openiap/nodeapi/blob/a159861/src/openiap.ts#L338)

___

### getEventListeners

▸ `Static` **getEventListeners**(`emitter`, `name`): `Function`[]

Returns a copy of the array of listeners for the event named `eventName`.

For `EventEmitter`s this behaves exactly the same as calling `.listeners` on
the emitter.

For `EventTarget`s this is the only way to get the event listeners for the
event target. This is useful for debugging and diagnostic purposes.

```js
const { getEventListeners, EventEmitter } = require('events');

{
  const ee = new EventEmitter();
  const listener = () => console.log('Events are fun');
  ee.on('foo', listener);
  getEventListeners(ee, 'foo'); // [listener]
}
{
  const et = new EventTarget();
  const listener = () => console.log('Events are fun');
  et.addEventListener('foo', listener);
  getEventListeners(et, 'foo'); // [listener]
}
```

**`Since`**

v15.2.0, v14.17.0

#### Parameters

| Name | Type |
| :------ | :------ |
| `emitter` | `EventEmitter` \| `_DOMEventTarget` |
| `name` | `string` \| `symbol` |

#### Returns

`Function`[]

#### Inherited from

EventEmitter.getEventListeners

#### Defined in

node_modules/@types/node/events.d.ts:299

___

### listenerCount

▸ `Static` **listenerCount**(`emitter`, `eventName`): `number`

A class method that returns the number of listeners for the given `eventName`registered on the given `emitter`.

```js
const { EventEmitter, listenerCount } = require('events');
const myEmitter = new EventEmitter();
myEmitter.on('event', () => {});
myEmitter.on('event', () => {});
console.log(listenerCount(myEmitter, 'event'));
// Prints: 2
```

**`Since`**

v0.9.12

**`Deprecated`**

Since v3.2.0 - Use `listenerCount` instead.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `emitter` | `EventEmitter` | The emitter to query |
| `eventName` | `string` \| `symbol` | The event name |

#### Returns

`number`

#### Inherited from

EventEmitter.listenerCount

#### Defined in

node_modules/@types/node/events.d.ts:271

___

### on

▸ `Static` **on**(`emitter`, `eventName`, `options?`): `AsyncIterableIterator`<`any`\>

```js
const { on, EventEmitter } = require('events');

(async () => {
  const ee = new EventEmitter();

  // Emit later on
  process.nextTick(() => {
    ee.emit('foo', 'bar');
    ee.emit('foo', 42);
  });

  for await (const event of on(ee, 'foo')) {
    // The execution of this inner block is synchronous and it
    // processes one event at a time (even with await). Do not use
    // if concurrent execution is required.
    console.log(event); // prints ['bar'] [42]
  }
  // Unreachable here
})();
```

Returns an `AsyncIterator` that iterates `eventName` events. It will throw
if the `EventEmitter` emits `'error'`. It removes all listeners when
exiting the loop. The `value` returned by each iteration is an array
composed of the emitted event arguments.

An `AbortSignal` can be used to cancel waiting on events:

```js
const { on, EventEmitter } = require('events');
const ac = new AbortController();

(async () => {
  const ee = new EventEmitter();

  // Emit later on
  process.nextTick(() => {
    ee.emit('foo', 'bar');
    ee.emit('foo', 42);
  });

  for await (const event of on(ee, 'foo', { signal: ac.signal })) {
    // The execution of this inner block is synchronous and it
    // processes one event at a time (even with await). Do not use
    // if concurrent execution is required.
    console.log(event); // prints ['bar'] [42]
  }
  // Unreachable here
})();

process.nextTick(() => ac.abort());
```

**`Since`**

v13.6.0, v12.16.0

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `emitter` | `EventEmitter` | - |
| `eventName` | `string` | The name of the event being listened for |
| `options?` | `StaticEventEmitterOptions` | - |

#### Returns

`AsyncIterableIterator`<`any`\>

that iterates `eventName` events emitted by the `emitter`

#### Inherited from

EventEmitter.on

#### Defined in

node_modules/@types/node/events.d.ts:254

___

### once

▸ `Static` **once**(`emitter`, `eventName`, `options?`): `Promise`<`any`[]\>

Creates a `Promise` that is fulfilled when the `EventEmitter` emits the given
event or that is rejected if the `EventEmitter` emits `'error'` while waiting.
The `Promise` will resolve with an array of all the arguments emitted to the
given event.

This method is intentionally generic and works with the web platform [EventTarget](https://dom.spec.whatwg.org/#interface-eventtarget) interface, which has no special`'error'` event
semantics and does not listen to the `'error'` event.

```js
const { once, EventEmitter } = require('events');

async function run() {
  const ee = new EventEmitter();

  process.nextTick(() => {
    ee.emit('myevent', 42);
  });

  const [value] = await once(ee, 'myevent');
  console.log(value);

  const err = new Error('kaboom');
  process.nextTick(() => {
    ee.emit('error', err);
  });

  try {
    await once(ee, 'myevent');
  } catch (err) {
    console.log('error happened', err);
  }
}

run();
```

The special handling of the `'error'` event is only used when `events.once()`is used to wait for another event. If `events.once()` is used to wait for the
'`error'` event itself, then it is treated as any other kind of event without
special handling:

```js
const { EventEmitter, once } = require('events');

const ee = new EventEmitter();

once(ee, 'error')
  .then(([err]) => console.log('ok', err.message))
  .catch((err) => console.log('error', err.message));

ee.emit('error', new Error('boom'));

// Prints: ok boom
```

An `AbortSignal` can be used to cancel waiting for the event:

```js
const { EventEmitter, once } = require('events');

const ee = new EventEmitter();
const ac = new AbortController();

async function foo(emitter, event, signal) {
  try {
    await once(emitter, event, { signal });
    console.log('event emitted!');
  } catch (error) {
    if (error.name === 'AbortError') {
      console.error('Waiting for the event was canceled!');
    } else {
      console.error('There was an error', error.message);
    }
  }
}

foo(ee, 'foo', ac.signal);
ac.abort(); // Abort waiting for the event
ee.emit('foo'); // Prints: Waiting for the event was canceled!
```

**`Since`**

v11.13.0, v10.16.0

#### Parameters

| Name | Type |
| :------ | :------ |
| `emitter` | `_NodeEventTarget` |
| `eventName` | `string` \| `symbol` |
| `options?` | `StaticEventEmitterOptions` |

#### Returns

`Promise`<`any`[]\>

#### Inherited from

EventEmitter.once

#### Defined in

node_modules/@types/node/events.d.ts:194

▸ `Static` **once**(`emitter`, `eventName`, `options?`): `Promise`<`any`[]\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `emitter` | `_DOMEventTarget` |
| `eventName` | `string` |
| `options?` | `StaticEventEmitterOptions` |

#### Returns

`Promise`<`any`[]\>

#### Inherited from

EventEmitter.once

#### Defined in

node_modules/@types/node/events.d.ts:195

___

### setMaxListeners

▸ `Static` **setMaxListeners**(`n?`, `...eventTargets`): `void`

```js
const {
  setMaxListeners,
  EventEmitter
} = require('events');

const target = new EventTarget();
const emitter = new EventEmitter();

setMaxListeners(5, target, emitter);
```

**`Since`**

v15.4.0

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `n?` | `number` | A non-negative number. The maximum number of listeners per `EventTarget` event. |
| `...eventTargets` | (`EventEmitter` \| `_DOMEventTarget`)[] | - |

#### Returns

`void`

#### Inherited from

EventEmitter.setMaxListeners

#### Defined in

node_modules/@types/node/events.d.ts:317
