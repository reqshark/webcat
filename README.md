# webcat

A p2p pipe across the web using webrtc that uses your Github private/public for authentication and a [signalhub](https://github.com/mafintosh/signalhub) for discovery

```
npm install -g webcat
```

## Usage

webcat lets you establish a p2p pipe to other github users over the web.
Let's say I wanted to connect to [@maxogden](https://github.com/maxogden)

First I need to configure webcat once

```
webcat --configure
Enter your github username: mafintosh
```

Then on my machine I run

```
webcat maxogden
hello max
```

On Max's machine he runs

```
webcat mafintosh
hi mathias
```

webcat will create a p2p pipe between connect me and max by using a [signalhub](https://github.com/mafintosh/signalhub) to exchange webrtc metadata
and Github private/public keys to authenticate that Max is actually [@maxogden](https://github.com/maxogden) and that I am actually [@mafintosh](https://github.com/mafintosh)

On my machine my prompt now looks like

```
webcat maxogden
hello max
hi mathias
```

And on Max's machine it now looks like

```
webcat mafintosh
hi mathias
hello max
```

## Use cases

You can use webcat to pipe files across the internet!

On my machine

```
webcat maxogden < some-file
```

On Max's machine

```
webcat mafintosh > some-file
```


## License

MIT
