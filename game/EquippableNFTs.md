# Equippable NFTs in Senshi

This document outlines how equippable NFTs, based on the RMRK standard, will be integrated into the Senshi game. This will allow for a dynamic and composable system for in-game items like weapons, armors, and talismans.

## Core Concept: The Catalog

The foundation of our equippable NFT system is the **Catalog**. A Catalog is a smart contract that defines the structure of our composable assets. It contains a collection of "parts" that can be either:

- **Fixed Parts**: Static elements of an item, like the hilt of a sword.
- **Slot Parts**: Areas where other NFTs can be equipped, like a gem slot on a piece of armor.

Each Senshi (warrior) will be an NFT that has multiple "slot" parts. These slots can be filled with other NFTs, such as:

- Weapons
- Armors
- Talismans

This allows for a high degree of customization and a dynamic in-game economy.

## How it Works in Senshi

1.  **Warrior NFTs**: Each warrior is a base NFT with several "slot" parts. For example, a warrior might have slots for:
    *   Right Hand (for a weapon)
    *   Left Hand (for a shield or another weapon)
    *   Head (for a helmet)
    *   Chest (for chest armor)
    *   Legs (for leg armor)
    *   Talisman Slot

2.  **Item NFTs**: Weapons, armors, and talismans are also NFTs. These items are designed to be equipped into the corresponding slots on a warrior NFT.

3.  **The Catalog Contract**: We will create a Catalog contract for each type of item (e.g., a "Swords" catalog, a "Helmets" catalog). These catalogs will define the parts of each item. For example, a sword might have a "blade" part (fixed) and a "gem" slot (slot).

4.  **Equipping Items**: When a player wants to equip an item, they will interact with the warrior NFT's contract. This will link the item NFT to the corresponding slot on the warrior NFT. The visual representation of the warrior will then be updated to show the equipped item.

## Example: Equipping a Sword

1.  A player owns a **Warrior NFT**.
2.  The player acquires a **Katana NFT**.
3.  The player calls the `equip` function on the **Warrior NFT**, specifying the **Katana NFT** and the "Right Hand" slot.
4.  The **Warrior NFT**'s contract verifies that the **Katana NFT** is a valid weapon and that the "Right Hand" slot is empty.
5.  The **Katana NFT** is "equipped" to the warrior. The warrior's in-game appearance and stats are updated.

## Technical Implementation (Based on RMRK)

We will use a `RMRKCatalogFactory` to deploy our Catalog contracts. Each catalog will have a metadata URI pointing to its details and a defined type (e.g., "senshi/weapon").

Parts will be added to the catalog using `addPart` or `addPartList`. For slot parts, we will use `addEquippableAddresses` to specify which collections of NFTs can be equipped in that slot.

This system will allow for a rich and evolving world of items and warriors, all powered by composable, equippable NFTs.