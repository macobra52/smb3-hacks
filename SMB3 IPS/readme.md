Super Mario Bros 3 
==================

All the following patches work for smb3 (prg0 or prg1), roms randomized using fcoughlin's smb3 randomizer, and any romhacks that do not move the respective data.


Enemies
==================


Faster Boss Bass
---------

Increases the speed Boss Bass moves back and forth so he is slightly faster than Mario at p speed. There is a rare glitch that can happen however where he will go offscreen and reappear invisible.


Half Boss Bass Respawn Time
-------

Decreases the time it takes Boss Bass to respawn after a death by half.


Faster Cheep Cheep
-------

Increases the speed of the roaming cheep cheep to be the same speed as vanilla Boss Bass.


Early Sun
------

Makes the Angry Sun dive at Mario much sooner than normal.


Faster Boom Boom
------

Increases the speed of the Boom Boom miniboss and decreases the time they pause between getting stomped and deploying their spikes.


Faster Koopalings
-------

Increases the speed of all Koopa Kid bosses and decreases the time they pause between getting stomped and jumping around in their shell. Additionally Lemmy's balls move around faster (since the previous change makes him easier)


Faster Hammer Bros
----------

Regular Hammer Bros move back and forth faster and jump more randomly.


All Four Bros
-----------

Includes the change above to regular Hammer Bros and does the following to the other three:
* Boomerang Bros move back and forth faster, throw their boomerangs farther and have a different throwing pattern
* Sledge Bros move back and forth faster and throw two hammers at a time
* Fire Bros move back and forth faster


Smarter Lakitu
----------

Changes how Lakitus throw their spinys to be based on the horizontal scrolling speed, so they will always hit Mario if he is going at the same speed.


Chain Chomps Break Free
----------

Modifies Chain Chomps to break free from their chains on the second tug instead of 50 like normal.


Half Bob-omb Explode Time
----------

Decreases the time it takes for a Bob-omb to explode after being stomped by half.


Faster Boo
----------

Increases the speed that Boo chases after Mario by 1.5x.


Dry Bones Get Up Faster
----------

Greatly decreases the time between when a Dry Bones gets stomped and when it reassembles itself (~3 seconds).


Fire Jets More Frequent
----------

Makes airship Fire Jets fire twice as often.


Faster Thwomps
----------

Halves the time in which a Thwomp (both up-down and left-right varieties) waits before returning back to its starting position. This does not increase their movement speed, but the speed in which up-down Thwomps move down can be modified by editing the IPS (location $0a in a hex editor, default $04)


Faster Bullet Bills
----------

Increases the speed of Bullet Bills (normal and homing) by 1.5x.


More Random Podoboos
----------

Increases the variance in which Podoboos jump out of the lava so that they can jump sooner than expected.


SMB2J Piranha Plants (All)
----------

Modifys all Piranha Plants (normal and giant) so that they will emerge even if Mario is standing next to their pipe, similar to Red Piranhas in SMB2J/Lost Levels. Note that the center of the giant Piranha is not exactly center so he can still emerge if Mario is standing on the right side of the pipe.


Piranha Plants Always Emerge (All)
----------

Modifys all Piranha Plants (normal and giant) so that they will always emerge regardless of where Mario is standing. The only exception is when standing exactly in the middle to prevent damage when coming out of an occupied pipe.


Shoe on Stomp 2
----------

A version of RussianManSMWC's Shoe on Stomp that does not modify the code beyond simple value swaps, making it compatible with other modifications here. The player-kuribo interaction works slightly different (you stomp the goomba inside of the shoe rather than bounce off him) but the general result is the same.


Koopaling Softlock Fix + Hammers Can Hit Koopalings
----------

Includes both the Koopaling Softlock Fix (see description below) and modifies Koopalings so that they can be hit by hammers thrown by Hammer Mario.


Other Difficulty
==================


Quarter Donut Block Fall Time
----------

Reduces the time it takes Donut Blocks to fall when Mario stands on them by 75%. To adjust the time to 50% or even instant modify the value at $0a in the ISP ($10 for 50%, $00 for instant)


Less Time Faster Tick
----------

Doubles the tick rate of the in-level timer and decreases all level starting times by 100 seconds. The only exception is 7-F1 which is adjusted to retain its 200 second starting time (otherwise it is impossible to complete when entering as small Mario).


Japanese Damage System
----------

Makes it so Mario always reverts to small upon taking a hit, regardless of his current power-up status.


Hardcore Mode
----------

Similar in concept to Hardcore Mode in other games. Sets starting lives to 0, patches out all methods of gaining lives, and on the game over screen replaces 'Continue' with 'Concede' which does the same thing as 'End'.


Fixes
==================


Bowser Hitbox Fix
-------

Extends Bowser's hitbox to occupy his lower half as well. This is done by redefining him to use the previously unused bound box 4 and adjusting dimensions accordingly.


Permanent Status Pause Glitch Fix
----------

Normally if a code/setting is used to give Mario a permanent power-up status, the game will softlock if the player does not enter the final Bowser door right away (after defeating him). Informally known as Bowser's time trap, this patch resolve the bug by clearing the graphics buffer while the Bowser door cycles through its normal pallets. For devs, this makes use of unused space at the end of bank 1, so be sure to adjust the IPS accordingly.


Clipping Patched
----------

Modifies the game so that Mario slides left when clipping conditions are met instead of right, preventing popular skips such as 7-1 and the 1UP clip in Bowser's Castle. My approach to patching out clipping that does not need any additional space and is therefore compatible with randomizer and other patches that do not modify this space in the rom.


Koopaling Softlock Fix
-------

While very rare, Koopalings can be defeated through non-standard means in the normal game, causing them to simply fall off the screen and softlock the game (since the wand never drops and the timer does not decrement). This simple patch resolves this by modifying their KillAction to match Bowser's so if this softlock condition occurs, they will still fly up and drop the wand like normal.


Misc.
==================


Cycle End Card Every Frame
----------

Increases the speed in which the end of level card changes from every eight frames to every frame, making it a bit more random if you don't collect it the exact same way every time.


Half P-Switch
----------

Halves the duration of the P-Switch timer. To double it instead, simply modify the IPS by setting address $0a to $c0


42 Coin 1UPs
----------

Makes it so that you only need to collect 42 coins for a 1UP. Can be easily modified with any custom amount, but glitchyness will occur with values over 100 ($64).


0 Lives
----------

Decreases Mario's life count to 0 at the start of the game and after resuming from a game over. To set a different life count, simply modify addresses $0a and $10 to whichever starting life count you want.


Random Power-up Direction
----------

Normally the direction a power-up goes (left or right) is based on where Mario hits the blocks. This makes the power-up direction random instead.


All Fanfares Give 1UP Only
----------

Matching three of the same end of level cards always awards a single 1up, no matter what is matched.


No Consecutive Stomps
----------

Removes the ability for Mario to accumulate points/lives when stomping on enemies without touching the ground. All stomps will award 100 points.


No More Bros
----------

Simple patch that removes all Hammer Bros from the world maps.


Infinite use Mushroom Houses
----------

When a mushroom house is cleared, this patch will make the player simply exit out instead of the 'poof' effect happening on the world map, allowing them to re-enter and obtain as many items as they want.


Move Sooner in Mushroom House
----------

Shortens the delay before Mario can actually move inside a Mushroom House to collect an item. Use All-Stars for a shorter delay (~2 seconds) or Instant to allow Mario to move instantly.


Exit Mushroom House Faster
----------

Shortens the delay between collecting an item in a Mushroom House and exiting back to the World Map.
