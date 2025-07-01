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

[!!!do this later!!!]
