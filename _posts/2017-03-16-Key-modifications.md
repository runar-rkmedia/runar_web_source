---
layout: post
title:  "Keyboard remapping gone mad"
date:   2017-03-16 22:47:20 +0100
categories: hardware
tags: hardware keyboard productivity tips
---

Remapping the keyboard is highly useful, especially if you find that there currently is not enough keys on your keyboard. Instead of slaving though remembering cumbersome key-combinations to get your work done, why not add some extra keys on your keyboard? Of course, we are not physically adding keys, but using the ones we have a bit smarter.

<figure>
  <video width="960" controls>
    <source src="/media/karabiner.mp4" type="video/mp4">
    <source src="/media/karabiner.webm" type="video/mp4">
  Your browser does not support the video tag.
  </video>
  <figurecaption>Video showcasing some of the remappings.
  </figurecaption>
</figure>

Like on your touch phone or pad, you can tap, hold, swipe as you navigate through the interface. Yet, you are only interacting with a single surface.

Our current keyboards have not evolved very much since their birth. Sure, you can get keys with tiny screens on them, or fancy light. But this doesn't really help productivity much. What we need are multiple ways to interact with each key. Ergo, we need more ways to press a button.

Of course, we already press buttons in different ways. Some you hold and use in addition to other keys, some you only tap. Other keys, you hold and repeat. But currently, there is no keyboard that defaults to assign different keys depending on whether you tap or hold the key.

Steve Losh, wrote a great article, called [A Modern Space Cadet](http://stevelosh.com/blog/2012/10/a-modern-space-cadet/), where he wrote about a smarter use of the keyboard. Even though the article is a few years old now, and the software he suggests to remap the keyboard is outdated, the article is well worth a read. I have taken great inspiration from the article.


{:.float-right}
![XKCD: Borrow Your Laptop](https://imgs.xkcd.com/comics/borrow_your_laptop.png)

## Caps-lock

Caps-lock is arguably the most remapped key on the keyboard. It doesn't do anything very useful. Unless you like to post angry comments on various news sites, you probably don't use the key. If you find yourself to be on of those who do, you probably shouldn't be using the internet. For everybody else, remap it to something else. I do it for the `Hyper`-key. Well, that is on macOS, the `hyper` key doesn't exist, so I remapped it to `Ctrl-Cmd-Alt-Shift`. So now I have more of the easily-hit key-combos than I can think of.

## Tap-keys and hold keys

Some keys you use differently than others. You hold your modifier keys while you tap other keys. Why not double the usage of some of these keys?

Especially the modifier keys seem to be good candidates for using as tapping as well as their regular hold-behaviour.

We do however need a target key to remap to. It is not too important which key you choose to remap to, but it should be an unused key.

I don't use my F-row too much, especially F12 and above. Therefore I decided to use these keys as a target for remapping. Now my modifier keys does something useful while tapping, especially in Atom.

Physical key  | Tap| Action in Atom |
---           | --- |--- |
Left Shift    | F12 | expand-region |
Left Command  | F13 | toggle-line-comments |
Left Alt      | F14 | wrap-with-abbreviation |
Right Ctrl    | F15 | outdent-selected-rows |
Right Command | F16 |indent-selected-rows |
Right Shift   | F17 |preview |

Combine these keys with regular modiefier keys, and you have a whole lot of new keyboard-shortcuts you can easily use. `Ctr+Command(tap)` will now actually be a command, and vise-versa, `Command+Ctrl(tap)` will be wholly different.

### Missing Control-key

The `Ctrl`-key is not to be found on the left side of my current keyboard, which I find frustrating. For this reason, I remapped my `§`-key to be `Ctrl` when held, and when tapped it functions as a regular `§`-key. Other alternatives would be using the `Caps-lock` as `Ctrl`, But I have other uses for that.


## Special keys and compromises

To accommodate the need in Norwegian for special characters, like `æ, å, ø`, I use a small toggle on the keyboard. Under the hood, I have set some keys whose placements matches the Norwegian-layout to output that character, but only when the `Macro`-function on the keyboard is enabled.

Physical key | Macro | Output
---          | ---   | ---
'            | alt-' | æ
shift-'      | alt-' | Æ
;            | alt-o | ø
shift-;      | alt-o | Ø
\            | alt-a | å
shift-\      | alt-a | Å


But isn't this just the same as changing the keyboard layout to Norwegian in the OS? Well, no. The Norwegian keyboard layout has quite a few differences compared to the US-layout. It switches many of the characters on the keyboard, which makes for unnecessary adjustments if one is using two layouts. In my view, it is better to just switch a few of the most needed keys, instead of all of them.

Of course, when the macro is enabled, I am unable to use their normal key. I find this an okay compromise. With just a tap, I can disable the `Macro`--function, and I can again access those keys. After all, when I am writing Norwegian, I am generally not writing code, but emails, or chatting and such. I can, for the most part, do without those keys then.

In my next post in the series, I will dive into how to remap the keyboard to achieve these goals discussed here. You can find the post here: [Key-configuration]({% post_url 2017-04-08-Karabiner %})
