---
layout: post
title:  "Key-configuration"
date:   2017-03-14 22:47:20 +0100
categories: hardware
series: keyboard
tags: hardware keyboard productivity tips
image: "advantage2.jpg"
image_description: "Kinesis Advantage2"
---

This is my third post in the series concerning keyboards and increasing the productivity with them. If you haven't read the others yet, here are some links to them:

- [The weird and productive keyboard]({% post_url 2017-03-14-Advantage %}), my recommended keyboard for anybody wanting to increase their productivity, comfortlevel, or simply how to write the correct way.
- [Keyboard remapping gone mad]({% post_url 2017-03-16-Key-modifications %}), a post going through some ideas for how the keyboard can be remapped to get more functionality while at the same time avoiding painful key-combinations.

## Video showcasing some of the remappings

<video width="960" height="540" controls>
  <source src="/media/karabiner.mp4" type="video/mp4">
  <source src="/media/karabiner.webm" type="video/mp4">
Your browser does not support the video tag.
</video>

In this post, I will dive into the technical aspect of how to actually remap the keyboard. Many software lets you do this, but many will not do this at a low enough level to actually remap the keys. Some actually just tries it best to cancel out the effect of the key you remapped through it, and then emulating the new key you remapped.

As a disclaimer, I would just like to point out that I am not sponsored or in any way involved with Karabiner. I simply recommend it, as many others do.

Karabiner has a history of doing this remapping at the level we need to do our remapping of the modifier-keys, so that the OS doesn't even see what key you pressed physically, but the key you tell it to see through Karabiner.

What makes Karabiner extra useful, is that you can not only configure it through a graphical user interface, but also by simply editing a `.json`-file. This is great for those who are used to editing text-files, as most developers and programmers are.

## macOS Sierra

macOS Sierra brought some changes to the generic keyboard and mouse-drivers, and this broke earlier versions of Karabiner. Luckily, the developers are currently rewriting Karabiner, which is now called Karabiner Elements, to work with the updated OS.

New features are added quite often, and it is very stable. I have not have a single issue with the program at all, actually.

> I will keep this page updated as progress continues, so that the correct information is always available here.


## Downloading from the correct fork

The community is also constantly working on it, bringing in their own features. One of the features we will be needing has not yet been merged with the main repository, but I suspect it will very soon. This feature is the 'Standalone', which we need to create a `hyper`-key, or another modifier-key.

The version we need is [wwwjfy-s latest release](https://github.com/wwwjfy/Karabiner-Elements/releases)

## Configuring Karabiner-Elements

Looking back at my previous post about what remapping I wrote that there was a few different kinds of remappings I found the most helpful, and my recommened setup.

### Hyper-key

To remap the `caps-lock` into another working modifier-key, which often is called the `hyper`-key, we need to add just a few lines into the config. But as I mentioned, macOS, does not have a `hyper`-key, so we emulate on with a combination of all modifier-keys. That would be `ctr + shift + option + cmd`, a crazy key-combination. I highly doubt you actually are using that, and if you are, please stop it before the pain sets in.

So, to redefine `caps_lock` into `hyper`, we add this to the config:

```json
"one_to_many_mappings": {
    "caps_lock": [
        "left_control",
        "left_shift",
        "left_option",
        "left_command"
    ]
},
```

## Tapping modifier-key for F-key

Tapping a key is different that holding it. Modifier-keys are by default only useful for holding and then applying a key-combination. On their own, they do nothing. But we can add functionality when tapping the modifier-keys to do something a lot more useful. We can also do combinations, for instance holding `ctrl` and tapping `cmd`.

The target-keys you need here should be unused keys. My keyboard does not have F-keys beyond F13, so that means I can use these keys are a target. You can of course configure this to any key, but really, it should be a key that is not used at all.

```json
"standalone_keys": {
    "left_shift": "f12",
    "left_command": "f13",
    "left_option": "f14",
    "right_control": "f15",
    "right_command": "f16",
    "right_shift": "f17",
    "caps_lock": "f18"
}
```

## Extra ctrl and option-keys

Since I want extra modifier-keys, available on both sides of my keyboard, I did the same technique as for tapping modifier-keys, but applied it to a regular key.

Tapping `§` now behaves as normal, but holding it will now be `ctrl`. I also set `]` to `option`.

```json
"simple_modifications": {
    "close_bracket": "right_alt",
    "grave_accent_and_tilde": "left_control"
},
"standalone_keys": {
    "close_bracket": "close_bracket",
    "grave_accent_and_tilde": "grave_accent_and_tilde",
}
```


## The full config

This is my whole config-file for Karabiner-Elements. It holds a few more values than what was mentioned above, but I am sure you can figure those out easily.

```json
{
    "global": {
        "check_for_updates_on_startup": true,
        "show_in_menu_bar": true,
        "show_profile_name_in_menu_bar": false
    },
    "profiles": [
        {
            "devices": [],
            "fn_function_keys": {
                "f1": "display_brightness_decrement",
                "f10": "mute",
                "f11": "volume_decrement",
                "f12": "volume_increment",
                "f2": "display_brightness_increment",
                "f3": "mission_control",
                "f4": "launchpad",
                "f5": "illumination_decrement",
                "f6": "illumination_increment",
                "f7": "rewind",
                "f8": "play_or_pause",
                "f9": "fastforward"
            },
            "name": "Default profile",
            "one_to_many_mappings": {
                "scroll_lock": [
                    "left_control",
                    "left_shift",
                    "left_option",
                    "left_command"
                ]
            },
            "selected": true,
            "simple_modifications": {
                "close_bracket": "right_alt",
                "grave_accent_and_tilde": "left_control"
            },
            "standalone_keys": {
                "close_bracket": "close_bracket",
                "grave_accent_and_tilde": "grave_accent_and_tilde",
                "left_shift": "f12",
                "left_command": "f13",
                "left_option": "f14",
                "right_control": "f15",
                "right_command": "f16",
                "right_shift": "f17",
                "scroll_lock": "f18"
            },
            "virtual_hid_keyboard": {
                "caps_lock_delay_milliseconds": 0,
                "keyboard_type": "iso",
                "standalone_keys_delay_milliseconds": 180
            }
        }
    ]
}
```