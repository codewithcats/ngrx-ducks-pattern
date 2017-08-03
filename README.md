# Ducks Pattern on NgRx

## Action
Action always contains type and may contain payload with specific type:
```ts
export interface Action<T> {
  type: string,
  payload: T
}
```
### Always define action payload type
This will help a lot when using action creator to create an action to be dispatched:
```ts
export interface Server {
  name: string
  id: string
}

export interface ServerPayload {
  server: Server
}

export const server = (serverMeta: Server) => ({
  type: SERVER,
  payload: {
    server: serverMeta
  }
})
```
