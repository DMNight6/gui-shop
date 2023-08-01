# GUI Shop

A fabric server-side mod to create and manage GUI shops.
They can be later opened by using commands, allowing integration with NPC mods like [Taterzens](placeholder.com)
<br>The mod supports LuckPerms for permissions.
<br><br>
## Installation
Put the .jar file in the "mods" folder
**(Requires Fabric API)**
<br><br>

## Commands and permissions
All commands can be used by admins (permission level 3) or by users/groups with the specific permission


| Description                | Command                                                                                              | Permission               | 
|----------------------------|------------------------------------------------------------------------------------------------------|--------------------------|
| Main command               | `/guishop`                                                                                           | `automessage.main`       |
| Create a shop              | `/guishop create <shopName>`                                                                         | `automessage.create`     |
| Delete a shop              | `/guishop delete <shopName> `                                                                        | `automessage.delete`     |
| Add an item in a shop      | `/guishop additem <shopName> <itemMaterial> [buyPrice] [sellPrice] [description] [nbt] <quantities>` | `automessage.additem`    |
| Remove an item from a shop | `/guishop removeitem <shopName> <itemName>`                                                          | `automessage.removeitem` |
| Open a shop                | `/guishop open <shopName>`                                                                           | `automessage.open`       |
| List all shops             | `/guishop list`                                                                                      | `automessage.list`       |
| List all items in a shop   | `/guishop list <shopName>`                                                                           | `automessage.list`       |
| Force save config          | `/guishop forcesave`                                                                                 | `automessage.forcesave`  |
| Reload config file         | `/automessage reload`                                                                                | `automessage.reload`     |

### Commands examples
Create a shop: `/guishop create "Test shop"`"

Add item in a shop: `/guishop additem "Diamond" "minecraft:diamond" 250.00 100.00 "This is a Diamond\\\\An expensive diamond\\\\Shiny" "{}" [1:10:32:64]"` *(you can split each description line by using "\\\\\\\\", and you can input up to 4 quantities splitted by ":")*

Remove item from shop: `/guishop removeitem "Test shop" "Diamond"`

Open a shop: `/guishop open "Test shop"`


## Configuration
You can find the config file in `./config/guishop.json`
<br>Both items' names and descriptions support [Adventure Text Format](https://docs.advntr.dev/minimessage/format.html).

You can even add items from the JSON file (check [JSON Example](#json-example)). This can be useful when your `additem` command would be very long, or to easily set a NBT *(remember to reload the mod using `/guishop reload`)*


### JSON example
```json5
{
  "shops": [
    {
      "shopName": "Shop number one",
      "items": [
        {
          "name": "The boat",
          "material": "minecraft:acacia_chest_boat",
          "description": [],
          "buyPrice": 50.0,
          "sellPrice": 25.0,
          "nbt": "{}",
          "quantityList": [
            1
          ]
        },
        {
          "name": "BBQ Sword",
          "material": "minecraft:diamond_sword",
          "description": [],
          "buyPrice": 0.0,
          "sellPrice": 0.0,
          "nbt": "{Damage:0,Enchantments:[{id:\"fire_aspect\",lvl:2},{id:\"sweeping\",lvl:2}],display:{Lore:['[{\"text\":\"Crispy and tasty\",\"italic\":false}]'],Name:'[{\"text\":\"The BBQ\",\"italic\":false}]'}}",
          "quantityList": [
            1
          ]
        },
        {
          "name": "Amethyst",
          "material": "minecraft:large_amethyst_bud",
          "description": [
            "<red>Such a spectacular</red>",
            "<purple>amethyst</purple>",
            "<rainbow>SHINY</rainbow>"
          ],
          "buyPrice": 200.0,
          "sellPrice": 100.0,
          "nbt": "{}",
          "quantityList": [
            1,
            40,
            64
          ]
        }
      ]
    },
    {
      "shopName": "A second shop",
      "items": []
    }
  ]
}
```
## Showcase
![Screenshot1]()

![Screenshot2]()

![Screenshot3]()