# Modifications

This section is highly inspired [A Modern Space Cadet](http://stevelosh.com/blog/2012/10/a-modern-space-cadet/) by Steve Losh, which is a good read if you are interested in a more useful keyboard. The software described in his post is however not usable in macOS sierra, but there is a new project called [Karabiner-Elements](https://github.com/tekezo/Karabiner-Elements) which works really well.

![XKCD: Borrow Your Laptop](https://imgs.xkcd.com/comics/borrow_your_laptop.png)

## Control-key

The `Ctrl`-key is not to be found on the left side, which I find frustrating. For this reason, I remapped my `§`-key to be `Ctrl` when held, and when tapped it functions as a regular `§`-key. Other alternatives would be using the `Caps-lock` as `Ctrl`, But I have other uses for that.

## Caps-lock

Caps-lock is arguably the most remapped key on the keyboard. It doesn't do anything very useful. Unless you like to post angry comments on various news-sites, you probably don't use the key. If you find yourself to be on of those who do, you probably shouldn't be using the internet. For everybody else, remap it to something else. I do it for the `Hyper`-key. Well, that is on macOS, the hyper-key doesn't exist, so I remapped it to `Ctrl-Cmd-Alt-Shift`. So now I have more easy to hit key-combos than I can think of.

## Tap-keys and hold-keys

Some keys you use different than others. You hold your modifier-keys while you tap other keys. When not double the usage of some of these keys?

Especially the modifier-keys seems to be the good candidates for using as tapping as well as their normal hold-behaviour. I don't use my F-row too much, especially F12 and above. Therefore these keys are free to use as a target for remapping. Now my modifier-keys does something useful while tapping, especially in Atom.

Physical key  | Tap| Action in Atom |
---           | --- |--- |
Left Shift    | F12 | expand-region |
Left Command  | F13 | toggle-line-comments |
Left Alt      | F14 | wrap-with-abbreviation |
Right Ctrl    | F15 | outdent-selected-rows |
Right Command | F16 |indent-selected-rows |
Right Shift   | F17 |preview |


## Special-keys and compromises

To accommodate the need in Norwegian for special characters, like `æ, å, ø`, I use a small toggle on the keyboard. Under the hood, I have set the some keys whose placements matches the Norwegian-layout to output that character, but only when the `Macro`-function on the keyboard is enabled.

Physical key | Macro | Output
---          | ---   | ---
'            | alt-' | æ
shift-'      | alt-' | Æ
;            | alt-o | ø
shift-;      | alt-o | Ø
\            | alt-a | å
shift-\      | alt-a | Å


But isn't this just the same as changing the keyboard-layout to Norwegian in the OS? Well, no. The Norwegian keyboard-layout has quite a few differences compared to the US-layout. It switches many of the characters on the keyboard, which makes for unnecessary adjustments if one is using two layouts. In my view, it is better to just switch a few of the most needed keys, instead of all of them.

Of course, when the macro is enabled, I am unable to use their normal key. I find this an okay compromise. With just a tap, I can disable the `Macro`--function, and I can again access those keys. After all, when I am writing Norwegian, it is generally not in code, but in email, chatting and such. I can for the most part do without those keys then.
