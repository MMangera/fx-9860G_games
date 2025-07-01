# fx-9860G_games

A couple of games to install on your fx-9860G series calculator.

# How to install

Add these program files to your calculator by plugging it in to your computer through USB and moving the downloaded files to `@MainMem/PROGRAM` in the USB drive. There are certain things you may need to run in order to be able to use these files, however:

## Snake

Run the `SNK RSET` program. This resets `List 15` and `List 16` for their higscores and admin privileges. Then, create a new program with the following code:

```
"[username]"->Str 1
1->List 16[1]
```
where `[username]` is whatever username you choose for login. This initialises the creator user with admin privileges. Run this new program, delete it, and you are ready to go!

## Spider Dash

This one may require a bit more effort. Run the `SDR RSET` program. This resets `List 22` in `ListFile 6` which stores the highscores for each level. Then, create a new program with this code:

```
File 6
Prog "SDR LVLS"
File 1
```

This moves to `ListFile 6`, creates the levels in `List 1-4`, and moves back to `ListFile 1`. Once that is done, you can delete the program to finish.

# Programs Appendix

1. To get to `Str`, do `SHIFT` `4` (CATALOG) and type in `STR`. Press `EXE` to use it where your cursor is.
2. To get to `List`, do `SHIFT` `1` to place it where your cursor is.
3. To get to `File`, do `SHIFT` `4` (CATALOG) and type in `LIST`. Press `EXE` to use it where your cursor is.
4. To get to `Prog`, do `SHIFT` `VARS` (PRGM) `F2` (CTL) `F1` to place it where your cursor is.

## Extras

### Create a level in Spider Dash

#### Creating the level

To create a level in Spider Dash, go to the `SDR LVLS` program. Currently there are four levels, placed in `List 1-4`. Create a new list using `{}->List [5]` (5 might be different if you have already created levels previously, just use the next list that hasn't been used yet). Inside the list each item will correspond to a vertical slice of the level. Each digit of each item corresponds to a single object of the level. The following code is used to determine which objects are placed:

1. 0 is empty space (` `)
2. 1 is a platform (`■`)
3. 2 is an upward-facing spike (`^`)
4. 3 is a downward-facing spike (`v`)
5. 4 is a dash (`≫`)
6. 5 is an un-dash (`≪`)
7. 9 is an end portal

Each element is 5 digits and the digits represent objects from the bottom to the top; however, if an element is less than 5 digits it will act as if it is zfilled up to 5 digits (`101` is the same as `00101`). For example, `42003` would represent:

```
v


^
≫
```

Note that all levels must end with `99999`. Using this, you can create your level without too much difficulty. The difficulty of that level, you can store directly after the `99999`, using this scale:

1. Easy
2. Medium
3. Hard
4. Harder
5. Insane
6. Ludicrous
7. Extreme
8. Hardest
   
#### Applying the level

Run the new `SDR LVLS` script. You then can either add two extra zeroes to the `SDR RSET` program and run it, or, if you want to keep your highscores, add two zeroes directly to `List 22` by switching to `ListFile 6` using a program and adding it directly through `STAT` in the main menu. You will then need a name for your level, and you need to put it into the next free string in the string memory. For your first level, put the name in `Str 8` as the base levels' names are in `Str 4-7`. Next, go into `SDR DLVL` and edit the first series of `If` commands to add one for the title of your new level. You then want to go to the `SDR MENU` program and look for the line which says `1+MOD(L-1,[n])->L` where n is the number of levels. Switch out `n` for `n+1`. (e.g., `4` for `5`). After that, you should be ready to play your new level!
