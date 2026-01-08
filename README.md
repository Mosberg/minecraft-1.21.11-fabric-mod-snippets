# Minecraft 1.21.11 Fabric Mod Snippets

This repository contains a collection of useful code snippets and examples for developing Minecraft mods using the Fabric modding framework for version 1.21.11. These snippets cover various aspects of mod development, including item creation, block manipulation, entity handling, and more.

## Table of Contents

- [Getting Started](#getting-started)
- [Code Snippets](#code-snippets)
  - [Creating a Custom Item](#creating-a-custom-item)
  - [Creating a Custom Block](#creating-a-custom-block)
  - [Handling Events](#handling-events)
- [Contributing](#contributing)
- [License](#license)

## Getting Started

To use the code snippets in this repository, you need to have a basic understanding of Java programming and the Fabric modding framework. Make sure you have the following prerequisites:

- Java Development Kit (JDK) 21 or higher
- Fabric Mod Loader
- Fabric API
- An IDE such as IntelliJ IDEA or Eclipse
  Clone this repository to your local machine:

```bash
git clone https://github.com/mosberg/minecraft-1.21.11-fabric-mod-snippets.git
```

## Code Snippets

### Creating a Custom Item

```java
import net.minecraft.item.Item;
import net.minecraft.item.ItemGroup;
import net.minecraft.util.Identifier;
import net.minecraft.util.registry.Registry;
public class CustomItem extends Item {
    public CustomItem() {
        super(new Item.Settings().group(ItemGroup.MISC));
    }

    public static void register() {
        Registry.register(Registry.ITEM, new Identifier("modid", "custom_item"), new CustomItem());
    }
}
```

### Creating a Custom Block

```java
import net.minecraft.block.Block;
import net.minecraft.block.Material;
import net.minecraft.util.Identifier;
import net.minecraft.util.registry.Registry;
public class CustomBlock extends Block {
    public CustomBlock() {
        super(Settings.of(Material.METAL).strength(4.0f));
    }
    public static void register() {
        Registry.register(Registry.BLOCK, new Identifier("modid", "custom_block"), new CustomBlock());
    }
}
```

### Handling Events

```java
import net.fabricmc.fabric.api.event.player.UseBlockCallback;
import net.minecraft.util.ActionResult;
import net.minecraft.util.hit.BlockHitResult;
import net.minecraft.world.World;
import net.minecraft.entity.player.PlayerEntity;
public class EventHandler {
    public static void register() {
        UseBlockCallback.EVENT.register((player, world, hand, hitResult) -> {
            if (!world.isClient) {
                BlockHitResult blockHit = (BlockHitResult) hitResult;
                // Custom logic when a block is used
                player.sendMessage(new LiteralText("Block used!"), false);
            }
            return ActionResult.SUCCESS;
        });
    }
}
```

## Contributing

Contributions are welcome! If you have useful code snippets or improvements, feel free to open a pull request or submit an issue.

## License

This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
