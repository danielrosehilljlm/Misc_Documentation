## How to: Add hashtags to the default Irish keyboard layout in Ubuntu

In order to permanently remap the Shift+3 combination in a default Irish keyboard in Ubuntu, follow these steps.

Firstly, navigate to the folder where the default keymaps are stored. This is

```
/usr/share/X11/xkb/symbols
```

Edit the Irish keyboard layout using nano or your text editor of choice:

sudo nano ie

![](/images/iekeyboard1.png)

The default combination for Shift + 3 is to display the Sterling currency symbol.

```
key <TLDE> { [ grave, notsign, brokenbar, >
key <AE01> { [ 1, exclam, exclamdown, on>
key <AE02> { [ 2, quotedbl, trademark, tw>
key <AE03> { [ 3, sterling, copyright, th>
```

Remap it to numbersign (not ‘hashtag’!)

![](/images/iekeyboard2.png)

```
key <TLDE> { [ grave, notsign, brokenbar, >
key <AE01> { [ 1, exclam, exclamdown, on>
key <AE02> { [ 2, quotedbl, trademark, tw>
key <AE03> { [ 3, numbersign, copyright, th>
```

Save changes.

Reload the keymap to verify that the change has been applied correctly:

```
setxkbmap -layout ie
```

Now you can use the Irish keyboard layout in Ubuntu while retaining quick access to create hashtags for Twitter like in the US layout!

(These changes will persist through a reboot).
