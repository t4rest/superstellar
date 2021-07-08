# superstellar

![Superstellar](http://blog.u2i.com/wp-content/uploads/2017/05/banner.png)

Massive multiplayer galactic game written in Golang. It has been inspired by the old arcade space shooter called Asteroids.

## Live demo
[http://superstellar.u2i.is](http://superstellar.u2i.is)

## Rules
Destroy moving objects and don’t get killed by other players and asteroids. You’ve got two resources – health points and
energy points. You lose your health with every hit you get and every contact with the asteroid. Energy points are consumed
when shooting and using a boost drive. The more objects you kill, the bigger your health bar grows. Good luck

## Story behind the game
[https://medium.com/u2i-blogs/we-made-a-multiplayer-browser-game-in-go-for-fun-242a5990ce29/](https://medium.com/u2i-blogs/we-made-a-multiplayer-browser-game-in-go-for-fun-242a5990ce29/)

## Installation & running
1. Clone this repository to your `$GOPATH/src` directory
2. `cd` to that directory
3. Run `go get`
4. Run `go build`
5. Run `./superstellar` to run a server instance
6. Open new console and go to the game source directory.
7. `cd webroot`
8. `npm install` `yarn add node-sass`
9. `npm run dev`
10. Go to [http://localhost:7770](http://localhost:7770)

## Running stress test util
You can run a stress test util that spawns any number of clients which connect to the server and send ramdomly correct user
input messages.

1. `cd superstellar_utils`
1. `go build && go install`
1. Run `$GOPATH/bin/superstellar_utils 127.0.0.1 100 50ms` for spawning 100 clients, with 50 ms interval.

## Live profiling
It's possible to dump various information from the running server, e.g. stacktraces of all goroutines which might be useful
in case of a deadlock.

1. Run server
1. Go to [http://localhost:7777/debug/pprof/](http://localhost:7777/debug/pprof/)

## Using JS `__DEBUG__` flag

If you run `DEBUG=true npm run dev` you will see additional debugging
informations. You can add your own debugging info in code. Just detect that
we're in the debug mode:

```javascript
if (__DEBUG__) {
   console.log("I'm in debug mode!");
}
```

## Compiling protobufs

Run `./generateProto.sh`
