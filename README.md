# How to Use Bloxd.io Matchmake API

This repository documents how to use the `api.matchmakePlayer()` function in Bloxd.io WorldCode to send players to specific game lobbies.

## Files

- [USAGE-HOMEPAGE.md](USAGE-HOMEPAGE.md) — All available games on bloxd.io
- [USAGE-STAGING.md](USAGE-STAGING.md) — Extra games available on staging.bloxd.io (may have bugs)

## Basic Syntax

```js
api.matchmakePlayer(myId, "gamename_variation", "lobbyName");
```

Replace `"gamename_variation"` with the desired game mode ID and `"lobbyName"` with the target lobby.

### Custom Game

```js
api.matchmakePlayer(myId, "classic_playerSchematic|XXXXXXXXXX", "lobbyName");
```

Replace `"XXXXXXXXXX"` with the desired Custom Game ID and `"lobbyName"` with the target lobby.

## How to get a Custom Game ID?

- Join the Custom Game
- Open the invite menu:
  - **PC:** Press the `I` key
  - **Mobile:** Tap the + person icon
- Tap/click the copy button — you'll get something like:
  `https://bloxd.io/play/classic_playerSchematic%7CVJmue7CFECakKq4fBsdG5/322`
- Remove everything before `classic`:
  `classic_playerSchematic%7CVJmue7CFECakKq4fBsdG5/322`
- Remove the `/number` at the end:
  `classic_playerSchematic%7CVJmue7CFECakKq4fBsdG5`
- Use it in the function:
```js
api.matchmakePlayer(myId, "classic_playerSchematic%7CVJmue7CFECakKq4fBsdG5", "1");
```

> **Note:** `%7C` is the URL-encoded form of `|` — both work in the function.

## License
This project is licensed under the **MIT License**. **You're free to modify and distribute as long as you include the LICENSE file and any existing copyright notices. See the LICENSE file for details.**

## Contributing
Feel free to fork this project and submit pull requests! Contributions are welcome, especially:
- New game modes added to Bloxd.io
- Corrections to existing game mode IDs
- Improvements to the documentation
