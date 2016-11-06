# Colyseus Client for Unity3D

[![Join the chat at https://gitter.im/gamestdio/colyseus](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/gamestdio/colyseus?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

C#/Unity3D integration for [colyseus](https://github.com/gamestdio/colyseus) - a
Minimalist Multiplayer Game Server.

## Installation

Copy `Assets/Colyseus` into your project. See [usage
example](Assets/ColyseusClient.cs).

**Running the demo server**

Ensure you have [Node v6+](http://nodejs.org/) installed. Then run these
commands in your commandline:

```
cd Server
npm install
npm start
```

## Usage

```csharp
using Colyseus

// [...]

Client colyseus = new Colyseus.Client ("ws://localhost:2657");
Room room = colyseus.Join ("room_name");
room.OnUpdate += Room_OnUpdate;

void Room_OnUpdate (object sender, RoomUpdateEventArgs e)
{
  if (e.patches == null) {
    // received first state
    // e.state <- do something with e.state
  } else {
    // received patched state
    // e.patches <- do something with e.patches
  }
}
```

## Change your Build Settings (Unity3D)

Goto "File > Build Settings > Player Settings", and select ".NET 2.0" instead of
".NET 2.0 Subset" on "Optimization > Api Compatibility Level" category.

## License

MIT
