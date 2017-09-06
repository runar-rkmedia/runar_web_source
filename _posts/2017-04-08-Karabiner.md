---
layout: post
title:  "Key-configuration"
date:   2017-04-08 11:47:20 +0100
categories: software
tags: productivity tips
image: "Karabiner.png"
image_description: "Karabiner"
excerpt: "In this post, I will dive into the technical aspect of how to remap the keyboard. Many software lets you do this, but most will not do this at a low enough level to actually remap the keys. Some just try it's best to cancel out the effect of the key you want it to remap, and then emulating the target key."
---

This is my third post in the series concerning keyboards and increasing the productivity with them. If you haven't read the others yet, here are some links to them:

- [The weird and productive keyboard]({% post_url 2017-03-14-Advantage %}), my recommended keyboard for anybody wanting to increase their productivity, comfort level, or simply how to write the correct way.
- [Keyboard remapping gone mad]({% post_url 2017-03-16-Key-modifications %}), a post going through some ideas for how the keyboard can be remapped to get more functionality while at the same time avoiding painful key-combinations.

Below is a recap-video from the last post, of some of the features of this remap:

<figure>
  <video width="960" controls>
    <source src="/media/karabiner.mp4" type="video/mp4">
    <source src="/media/karabiner.webm" type="video/mp4">
  Your browser does not support the video tag.
  </video>
  <figurecaption>Video showcasing some of the remappings.
  </figurecaption>
</figure>

In this post, I will dive into the technical aspect of how to remap the keyboard. Many software lets you do this, but most will not do this at a low enough level to actually remap the keys. Some just try it's best to cancel out the effect of the key you want it to remap, and then emulating the target key.

## Karabiner to the rescue

As a disclaimer, I would just like to point out that I am not sponsored or in any way involved with Karabiner. I simply recommend it, as many others do.

Karabiner has a history of doing this remapping at the level we need to do our remapping of the modifier keys, so that the OS doesn't even see what key you pressed physically, but the key you tell it to see through Karabiner.

What makes Karabiner extra useful, is that you can not only configure it through a graphical user interface, but also by just editing a `.json`-file. This is great for those who are used to editing text files, as most developers and programmers are.

It is no also possible to share and import complex key-modification-rules, which is a very handy and welcome feature.

### macOS Sierra

macOS Sierra brought some changes to the generic keyboard and mouse drivers, and this broke earlier versions of Karabiner. Luckily, the developers are currently rewriting Karabiner, which is now called Karabiner Elements, to work with the updated OS.

New features are added quite often, and it is very stable. I have not had a single issue with the program at all.

> Because Karabiner Elements is not yet released and actively worked on, big changes are happening fast.
>
> I will keep this page updated as progress continues so that the correct information is always available here.


## Downloading Karabiner-Elements

You can download the application from [Karabiner-Elements GitHub-Page](https://github.com/tekezo/Karabiner-Elements/).

## Configuring Karabiner-Elements

Looking back at my previous post about what remapping I wrote that there were a few different kinds of remappings I found the most helpful, and my recommended setup.

Karabiner-Elements has made the process of sharing and importing comples key-modifications really easy. The rules can now be created and stored in simple `.json`-files, and imported via a regular internet-browser. A collection of rules is available from the developer's site, and also inside the application itself.

### Hyper-key

To remap the `caps-lock` into another working modifier-key, which often is called the `hyper`-key, we need to add just a few lines into the config. But as I mentioned, macOS does not have a `hyper`-key, so we emulate on with a combination of all modifier keys. That would be `ctrl + shift + option + cmd`, a crazy key-combination. I highly doubt you actually are using that, and if you are, please stop it before the pain sets in.

In the latest release, 0.91.5 as of writing, this configuration is included, and you can simply import it from the _Complex Modifications_-tab.

- Press _Add Rule_
- Press _Import more rules from the internet_

A list of rules should follow. One of them should be named _Change caps_lock key_. Simply press _Import_, and select the rules you would like to enable from that import. If you ever change your mind, just disable the rule.

## Tapping modifier-key for F-key

Tapping a key is different that holding it. Modifier keys are by default only useful for holding and then applying a key-combination. On their own, they do nothing. But we can add functionality when tapping the modifier keys to do something a lot more useful. We can also do combinations, for instance holding `ctrl` and tapping `cmd`.

The target-keys you need here should be unused keys. My keyboard does not have F-keys beyond F13, so that means I can use these keys are a target. You can, of course, configure this to any key, but really, it should be a key that is not used at all.

I have created a pull-request to get this configuration into the main server, so you can add them from there. In the meantime, you can import it directly from my site. Just follow link below and allow it to import into Karabiner.

{% assign mod_json = site.url_site  | append: "/media/modifiers_to_f-keys.json" %}

<a href="karabiner://karabiner/assets/complex_modifications/import?url={{ mod_json | escape  }}">import-file for Karabiner-Elements</a>

## Extra ctrl and option keys

Since I want extra modifier keys, available on both sides of my keyboard, I did the same technique as for tapping modifier keys but applied it to a regular key.

You can do this on the _Simple Modifications_-tab inside the Karabiner-Elements-GUI, from the simple drop-down-menu. Or, if you are are more comfortable with pure text, in your `json`, add these elements.

```json
"simple_modifications": {
    "close_bracket": "right_option",
    "grave_accent_and_tilde": "left_control"
}
```
