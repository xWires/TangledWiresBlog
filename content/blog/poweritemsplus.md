---
title: Introducing PowerItems+
description: A complete rewrite of PowerItems with all new features.
date: 2024-05-31
tags:
    - Java
    - PowerItems
    - PowerItems+
    - Minecraft Plugins
---
The code of PowerItems isn't great. I wrote a lot of it a few years ago when I was still fairly new to Java. However, it did fulfil its purpose: to allow Minecraft server admins to create items that look more interesting than normal items.

PowerItems also allows you to bind commands to items, which are run when a player right clicks whilst holding it. While this wasn’t the main purpose of PowerItems, I personally found it to be quite useful.

Anyway, recently, multiple people have requested that I add other stats that can be added to items, such as Crit Change, Crit Damage, and Strength. Adding these to PowerItems would be quite difficult, and require me to change a lot of the code anyway, so instead I will be creating a new plugin called PowerItems+ (or PowerItemsPlus) which will add these, and give server admins more control over items created with it. PowerItems+ will include a few default items and abilities, which you can assign to items. You will be able to create addons for PowerItems+ in Java that add more abilities and rarities.

To create a new ability, you will create a class that looks something like this:

```java
public class MyNewAbility implements PIPAbility {
    private String ID = "myNewAbility";
    private String NAME = "My New Ability";

    public void onLeftClick(Player p, PIPItem item) {
        p.sendMessage("Left clicked with " + item.getName());
    }
    public void onRightClick(Player p, PIPItem item) {
        p.sendMessage("Right clicked with " + item.getName());
    }
}
```

Adding new rarities will probably be done in the same way as done in PowerItems, you can find an example [here](https://github.com/xWires/PowerItemsExampleAddon/blob/main/src/main/java/xyz/tangledwires/PowerItemsAddon/App.java).

To be clear, PowerItems will still be supported, and it won't be going away any time soon, it may be updated less frequently, but I do plan on continuing to fix bugs and potentially add new features.