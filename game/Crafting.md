**Crafting Page Structure**

The crafting system allows players to combine five elements in an attempt to forge weapons, armor, talismans, or relics. The interface is split into two main panels:

---

### UI Layout

- **Left Panel – Inventory**

  - Displays all owned elements
  - Elements can be selected and assigned to the crafting grid

- **Right Panel – Crafting Grid**

  - Five slots to place selected elements
  - A 'Craft' button initiates the crafting attempt
  - Outcome: success or failure

---

### Crafting Logic

- **Successful Crafting**

  - If the 5-element combination matches a valid recipe:

    - Elements are consumed
    - Item is added to the player's inventory
    - No cooldown applied

- **Failed Crafting**

  - If the combination does not match any known recipe:

    - The 5 used elements are locked
    - Locked elements cannot be used in another attempt for 2 hours

---

### Gameplay Impact

- Encourages strategic experimentation rather than random guessing
- Protects the value of rare recipes and crafted items
- Balances resource use with time-based risk

This system supports both discovery and economic integrity within the crafting ecosystem.
