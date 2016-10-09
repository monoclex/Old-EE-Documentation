# Old EE Documentation
Documentation on the protocol for  Old EE

# Important Data

Game Id: `everybody-edits-old-gue3mggr0mppaimep8jw`

Room Type: `FlixelWalker1`

Sample Connection Code:

`
Client OldEEClient = PlayerIO.Connect("everybody-edits-old-gue3mggr0mppaimep8jw", "public", "whatever", "", "");
Connection OldEEConnection = OldEEClient.Multiplayer.CreateJoinRoom("0x0", "FlixelWalker1", true, null, null);
OldEEConnection.Send("init");
`

## How RoomId works

You need to get the X and Y position of the world in the lobby.

The X ranges from 0 to 8, and the Y ranges from 0-5

So an example looks like this: `0x0`, `8x5`, and everything inbetween.

# Send

## change

3 Args

Send to place a block

Arg 1: Int, The X position of the block
Arg 2: Int, The Y position of the block
Arg 3: Int, The block Id.

## face

1 Arg

Send to change your face

Arg 1: Int, The face Id.

## init

0 Args

Send to fully connect

## update

8 Args

Send to move

Arg 1: Double, The X position.
Arg 2: Double, The Y position.
Arg 3: Double, The SpeedX.
Arg 4: Double, The SpeedY.
Arg 5: Double, The Modifier X.
Arg 6: Double, The Modifier Y.
Arg 7: Double, Something.
Arg 8: Double, Something.

# Recieve

## add

4 Args

Recieved when someone joins.

Arg 1: Int, The player Id.
Arg 2: Int, The face they're wearing.
Arg 3: Int, The X position.
Arg 4: Int, The Y position.

## change

3 Args

Recieved when someone places a block.

Arg 1: Int, The X position of the block
Arg 2: Int, The Y position of the block
Arg 3: Int, The block Id.

## face

2 Args

Recieved when someone changes their face

Arg 1: Int, Their player Id.
Arg 2: Int, Their face Id.

## init

2 Args

Recieved when you complete connection and after you send "init"

Arg 1: String, The level... ?
Arg 2: Int, Your player Id.

## left

1 Arg

Recieved when someone leaves the world

Arg 1: Int, Their player Id.
