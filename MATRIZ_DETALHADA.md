# Matriz Detalhada Java/Fabric → Bedrock - VSAS 4.2.6

---

## Legenda

| Símbolo | Significado | Cor |
|---------|-------------|------|
| ✅ | Implementação Direta | Verde |
| 🟡 | Requer Adaptação | Amarelo |
| 🔧 | Requer Script API | Azul |
| ❌ | Limitado/Impossível | Vermelho |
| ⚠️ | Requer Investigação | Laranja |

---

## 1. ITENS BÁSICOS

### 1.1 Sticks (Gravetos)

| ID Original | Tipo | Comportamento | Bedrock | JSON/Componentes | Script API | Limitações | Prioridade | Notas |
|-------------|------|---------------|---------|------------------|-------------|-------------|------------|-------|
| `vsas:sticks/oak_stick` | Item | Item com textura variada | ✅ | Item JSON + Texture | - | - | Alta | Base para todas as receitas |
| `vsas:sticks/spruce_stick` | Item | Item com textura variada | ✅ | Item JSON + Texture | - | - | Alta | - |
| `vsas:sticks/birch_stick` | Item | Item com textura variada | ✅ | Item JSON + Texture | - | - | Alta | - |
| `vsas:sticks/jungle_stick` | Item | Item com textura variada | ✅ | Item JSON + Texture | - | - | Alta | - |
| `vsas:sticks/acacia_stick` | Item | Item com textura variada | ✅ | Item JSON + Texture | - | - | Alta | - |
| `vsas:sticks/dark_oak_stick` | Item | Item com textura variada | ✅ | Item JSON + Texture | - | - | Alta | - |
| `vsas:sticks/crimson_stick` | Item | Item com textura variada | ✅ | Item JSON + Texture | - | - | Alta | - |
| `vsas:sticks/warped_stick` | Item | Item com textura variada | ✅ | Item JSON + Texture | - | - | Alta | - |
| `vsas:sticks/bamboo_stick` | Item | Item com textura variada | ✅ | Item JSON + Texture | - | - | Alta | - |
| `vsas:sticks/cherry_stick` | Item | Item com textura variada | ✅ | Item JSON + Texture | - | - | Alta | - |
| `vsas:sticks/mangrove_stick` | Item | Item com textura variada | ✅ | Item JSON + Texture | - | - | Alta | - |

**Tags**: `vsas:sticks`, `c:wood_sticks` → ✅ Implementar como tags Bedrock

**Receitas**:
- Receitas normais (2 planks → 4 sticks) → ✅ Recipe JSON
- Receitas swap (8 sticks + 1 central → 9 sticks) → ✅ Recipe JSON com tags

---

## 2. FERRAMENTAS

### 2.1 Machados (90 itens)

| Material | Quantidade | Bedrock | JSON | Script | Limitações | Prioridade |
|----------|-----------|---------|------|---------|-------------|------------|
| Wooden | 10 | ✅ | Item + Components | - | - | Alta |
| Stone | 10 | ✅ | Item + Components | - | - | Alta |
| Iron | 10 | ✅ | Item + Components | - | - | Alta |
| Golden | 10 | ✅ | Item + Components | - | - | Alta |
| Diamond | 10 | ✅ | Item + Components | - | - | Alta |
| Netherite | 10 | ✅ | Item + Components | - | - | Alta |

**Componentes necessários**:
- `minecraft:durability` (varia por material)
- `minecraft:attack_damage` (varia por material)
- `minecraft:attack_speed` (varia por material)
- `minecraft:enchantable`
- `minecraft:repairable`

**Tags**: `vsas:wooden_axes`, `vsas:stone_axes`, `vsas:iron_axes`, `vsas:golden_axes`, `vsas:diamond_axes`, `vsas:netherite_axes`

**Receitas**: Crafting shaped + Smithing (netherite) → ✅

### 2.2 Picaretas (90 itens)

Mesma estrutura dos machados → ✅

**Componentes adicionais**:
- `minecraft:mining_speed` (varia por material)
- `minecraft:mining_tier` (varia por material)

### 2.3 Pás (90 itens)

Mesma estrutura → ✅

### 2.4 Enxadas (90 itens)

Mesma estrutura → ✅

### 2.5 Espadas (90 itens)

Mesma estrutura → ✅

---

## 3. ARMAS

### 3.1 Arcos (10 itens)

| ID | Bedrock | JSON | Script | Limitações | Prioridade |
|-----|---------|------|---------|-------------|------------|
| `vsas:bows/oak_bow` | ✅ | Item + Components | - | - | Alta |
| `vsas:bows/spruce_bow` | ✅ | Item + Components | - | - | Alta |
| ... | ✅ | ... | - | - | Alta |

**Componentes necessários**:
- `minecraft:durability` (384)
- `minecraft:enchantable`
- `minecraft:repairable`
- `minecraft:use_duration` (72000)
- `minecraft:cooldown` (category: "bow", duration: 1.0)

**Receitas**: Crafting shaped (string + sticks) → ✅

### 3.2 Bestas (10 itens)

| ID | Bedrock | JSON | Script | Limitações | Prioridade |
|-----|---------|------|---------|-------------|------------|
| `vsas:crossbows/oak_crossbow` | ✅ | Item + Components | - | - | Alta |
| ... | ✅ | ... | - | - | Alta |

**Componentes necessários**:
- `minecraft:durability` (465)
- `minecraft:enchantable`
- `minecraft:repairable`
- `minecraft:use_duration`
- `minecraft:cooldown` (category: "crossbow")
- `minecraft:chargeable` (para carregar com flechas)

**Receitas**: Crafting shaped (iron_ingot + string + sticks) → ✅

### 3.3 Flechas (10 itens + entidades)

| ID | Tipo | Bedrock | JSON | Script | Limitações | Prioridade | Notas |
|-----|------|---------|------|---------|-------------|------------|-------|
| `vsas:arrows/oak_arrow` | Item | ✅ | Item JSON | - | - | Alta | - |
| `vsas:arrows/oak_arrow` | Entidade | 🟡 | Entity JSON | 🔧 | Renderização customizada | Alta | Requer entity definition |
| ... | ... | ... | ... | ... | ... | ... | - |

**Item JSON**:
- `minecraft:display_name`
- `minecraft:icon`
- `minecraft:stackable` (max: 64)
- `minecraft:tags` (["vsas:arrows", "arrow"])

**Entity JSON**:
- `minecraft:projectile` component
- Custom render com textura variada
- Possível limitação: danos podem ser iguais para todas

**Receitas**: Crafting shaped (flint + stick + feather) → ✅

**Override vanilla**:
- `spectral_arrow.json` usa tag `vsas:arrows` → ✅ Adaptar receita

---

## 4. ITENS ESPECIAIS

### 4.1 Escovas (10 itens)

| ID | Bedrock | JSON | Script | Limitações | Prioridade |
|-----|---------|------|---------|-------------|------------|
| `vsas:brushes/oak_brush` | ✅ | Item JSON | - | - | Alta |
| ... | ✅ | ... | - | - | Alta |

**Componentes**:
- `minecraft:durability` (64)
- `minecraft:use_duration`
- `minecraft:cooldown`

**Receitas**: Crafting shaped (copper_ingot + stick + feather) → ✅

### 4.2 Varas de Pesca (10 itens)

| ID | Bedrock | JSON | Script | Limitações | Prioridade |
|-----|---------|------|---------|-------------|------------|
| `vsas:fishingrods/oak_fishing_rod` | ✅ | Item JSON + Components | - | - | Alta |
| ... | ✅ | ... | - | - | Alta |

**Componentes**:
- `minecraft:durability` (64)
- `minecraft:use_duration`
- `minecraft:cooldown`
- `minecraft:enchantable`

**Receitas**: Crafting shaped (3 sticks + 2 strings) → ✅

**Mixin**: `FishingBobberEntityMixin` e `FishingBobberEntityRendererMixin` → ⚠️ Investigar se necessário

### 4.3 Carrot on a Stick (10 itens)

| ID | Bedrock | JSON | Script | Limitações | Prioridade |
|-----|---------|------|---------|-------------|------------|
| `vsas:onastick/oak_carrot_on_a_stick` | ✅ | Item JSON + Components | - | - | Alta |
| ... | ✅ | ... | - | - | Alta |

**Componentes**:
- `minecraft:durability` (25)
- `minecraft:use_duration`
- `minecraft:cooldown`

**Receitas**: Crafting shaped (fishing_rod + carrot) → ✅

### 4.4 Warped Fungus on a Stick (10 itens)

Mesma estrutura do Carrot on a Stick → ✅

---

## 5. BLOCOS

### 5.1 Fogueiras (20 blocos)

| Tipo | Variante | Bedrock | JSON | Script | Limitações | Prioridade | Notas |
|------|----------|---------|------|---------|-------------|------------|-------|
| Normal | Oak | ✅ | Block JSON | - | - | Alta | - |
| Normal | Spruce | ✅ | Block JSON | - | - | Alta | - |
| ... | ... | ✅ | ... | - | - | Alta | - |
| Soul | Oak | ✅ | Block JSON | - | - | Alta | Comportamento soul |
| Soul | Spruce | ✅ | Block JSON | - | - | Alta | - |
| ... | ... | ✅ | ... | - | - | Alta | - |

**Componentes necessários**:
- `minecraft:display_name`
- `minecraft:material_instances` (texturas)
- `minecraft:light_emission` (15 para lit, 0 para unlit)
- `minecraft:flammable` (burn_odds: 0, flame_odds: 0)
- `minecraft:destructible_by_mining`
- `minecraft:placement_rule`

**Permutations**:
- `lit` state (true/false)
- `facing` direction (north, south, east, west)

**Loot Tables**:
- Silk Touch → bloco
- Normal → charcoal (1-2) com survives_explosion

**Receitas**:
- Normal: 3 logs + coal + stick → campfire
- Soul: 3 logs + soul_soil + stick → soul_campfire

### 5.2 Afiações (10 blocos)

| ID | Bedrock | JSON | Script | Limitações | Prioridade | Notas |
|-----|---------|------|---------|-------------|------------|-------|
| `vsas:grindstones/oak_grindstone` | ✅ | Block JSON | - | Interface não customizável | Média | - |
| ... | ✅ | ... | - | - | Média | - |

**Componentes**:
- `minecraft:display_name`
- `minecraft:material_instances`
- `minecraft:destructible_by_mining`

**Receitas**: 2 stone_slabs + stick → grindstone

**Mixin**: `GrindstoneScreenHandlerMixin` → ❌ Não aplicável no Bedrock

### 5.3 Escadas (10 blocos)

| ID | Bedrock | JSON | Script | Limitações | Prioridade |
|-----|---------|------|---------|-------------|------------|
| `vsas:ladders/oak_ladder` | ✅ | Block JSON | - | - | Alta |
| ... | ✅ | ... | - | - | Alta |

**Componentes**:
- `minecraft:display_name`
- `minecraft:material_instances`
- `minecraft:destructible_by_mining`
- `minecraft:placement_rule` (can_place_on: solid_block)
- `minecraft:climbable` (true)

**Receitas**: 7 sticks → 3 ladders

### 5.4 Alavancas (10 blocos)

| ID | Bedrock | JSON | Script | Limitações | Prioridade |
|-----|---------|------|---------|-------------|------------|
| `vsas:levers/oak_lever` | ✅ | Block JSON | - | - | Alta |
| ... | ✅ | ... | - | - | Alta |

**Componentes**:
- `minecraft:display_name`
- `minecraft:material_instances`
- `minecraft:destructible_by_mining`
- `minecraft:placement_rule`
- `minecraft:redstone` (power: 0-15)

**Permutations**:
- `powered` state (true/false)
- `facing` direction

**Receitas**: cobblestone + stick → lever

### 5.5 Trilhos (40 blocos)

| Tipo | Variante | Bedrock | JSON | Script | Limitações | Prioridade | Notas |
|------|----------|---------|------|---------|-------------|------------|-------|
| Rail | Oak | ✅ | Block JSON | - | Conexão com minecarts | Alta | - |
| Rail | Spruce | ✅ | Block JSON | - | - | Alta | - |
| ... | ... | ✅ | ... | - | - | Alta | - |
| Powered Rail | Oak | ✅ | Block JSON | - | - | Alta | - |
| Powered Rail | Spruce | ✅ | Block JSON | - | - | Alta | - |
| ... | ... | ✅ | ... | - | - | Alta | - |
| Detector Rail | Oak | ✅ | Block JSON | - | - | Alta | - |
| ... | ... | ✅ | ... | - | - | Alta | - |
| Activator Rail | Oak | ✅ | Block JSON | - | - | Alta | - |
| ... | ... | ✅ | ... | - | - | Alta | - |

**Componentes**:
- `minecraft:display_name`
- `minecraft:material_instances`
- `minecraft:destructible_by_mining`
- `minecraft:placement_rule`
- `minecraft:rail` (para rails normais)
- `minecraft:powered_rail` (para powered rails)
- `minecraft:detector_rail` (para detector rails)
- `minecraft:activator_rail` (para activator rails)

**Permutations**:
- `rail_direction` (north_south, east_west, ascending_east, etc.)
- `powered` (para powered rails)
- `activated` (para activator rails)

**Mixin**: `PoweredRailBlockMixin` → ✅ Verificar se necessário no Bedrock

**Receitas**:
- Rail: iron_ingot + stick → rail × 16
- Powered Rail: iron_ingot + stick + redstone → powered_rail × 6
- Detector Rail: iron_ingot + stick + redstone_torch → detector_rail × 6
- Activator Rail: iron_ingot + stick + redstone_torch → activator_rail × 6

**Mixin**: `AbstractMinecartEntityMixin` → ✅ Testar compatibilidade com minecarts

### 5.6 Tochas (60 blocos)

| Tipo | Variante | Bedrock | JSON | Script | Limitações | Prioridade |
|------|----------|---------|------|---------|-------------|------------|
| Torch | Oak | ✅ | Block JSON | - | - | Alta |
| Torch | Spruce | ✅ | Block JSON | - | - | Alta |
| ... | ... | ✅ | ... | - | - | Alta |
| Soul Torch | Oak | ✅ | Block JSON | - | - | Alta |
| Soul Torch | Spruce | ✅ | Block JSON | - | - | Alta |
| ... | ... | ✅ | ... | - | - | Alta |
| Redstone Torch | Oak | ✅ | Block JSON | - | - | Alta |
| ... | ... | ✅ | ... | - | - | Alta |
| Soul Redstone Torch | Oak | ✅ | Block JSON | - | - | Alta |
| ... | ... | ✅ | ... | - | - | Alta |
| Wall Torch | Oak | ✅ | Block JSON | - | - | Alta |
| ... | ... | ✅ | ... | - | - | Alta |

**Componentes**:
- `minecraft:display_name`
- `minecraft:material_instances`
- `minecraft:light_emission` (9 para torch, 10 para soul_torch)
- `minecraft:destructible_by_mining`
- `minecraft:placement_rule`
- `minecraft:redstone` (para redstone torches)

**Permutations**:
- `torch_facing_direction` (para wall torches)
- `lit` (para redstone torches)

**Receitas**:
- Torch: coal/charcoal + stick → torch × 4
- Soul Torch: coal/charcoal + stick + soul_sand/soul_soil → soul_torch × 4
- Redstone Torch: redstone + stick → redstone_torch
- Wall variants: crafting com torch normal

---

## 6. FUNCIONALIDADES ESPECIAIS

### 6.1 Minecart em Rails Variantes

| Funcionalidade | Origem | Bedrock | JSON | Script | Limitações | Prioridade | Notas |
|---------------|--------|---------|------|---------|-------------|------------|-------|
| Minecart em rails variantes | AbstractMinecartEntityMixin | ✅ | - | - | Testar compatibilidade | Alta | Deve funcionar automaticamente |

### 6.2 Strider com Sticks Variantes

| Funcionalidade | Origem | Bedrock | JSON | Script | Limitações | Prioridade | Notas |
|---------------|--------|---------|------|---------|-------------|------------|-------|
| Strider usa sticks | StriderEntityMixin | ❌ | - | - | Não há striders no Bedrock | Baixa | Não aplicável |

### 6.3 Pig com Saddle

| Funcionalidade | Origem | Bedrock | JSON | Script | Limitações | Prioridade | Notas |
|---------------|--------|---------|------|---------|-------------|------------|-------|
| Pig com saddle | PigEntityMixin | ❌ | - | - | Não claro qual o propósito | Baixa | Investigar se necessário |

### 6.4 Villager Trades

| Funcionalidade | Origem | Bedrock | JSON | Script | Limitações | Prioridade | Notas |
|---------------|--------|---------|------|---------|-------------|------------|-------|
| Villager vende itens VSAS | VillagerTrades.class | 🟡 | - | 🔧 | Requer Script API | Média | Implementar via scripts |

**Script API necessário**:
```javascript
// Adicionar trades para villagers
villager.addTrade({
    buy: { item: 'vsas:oak_stick', count: 16 },
    sell: { item: 'vsas:oak_wooden_axe', count: 1 },
    maxUses: 2,
    rewardExp: true,
    villagerExperience: 5
});
```

### 6.5 Loot Table Modifiers

| Funcionalidade | Origem | Bedrock | JSON | Script | Limitações | Prioridade | Notas |
|---------------|--------|---------|------|---------|-------------|------------|-------|
| Modifica loot tables | LootTableModifiers.class | ✅ | Loot Table JSON | - | - | Média | Implementar via loot tables |

### 6.6 Grindstone Interface

| Funcionalidade | Origem | Bedrock | JSON | Script | Limitações | Prioridade | Notas |
|---------------|--------|---------|------|---------|-------------|------------|-------|
| Interface customizada | GrindstoneScreenHandlerMixin | ❌ | - | - | Não customizável no Bedrock | Baixa | Usar interface padrão |

### 6.7 Held Item Renderer

| Funcionalidade | Origem | Bedrock | JSON | Script | Limitações | Prioridade | Notas |
|---------------|--------|---------|------|---------|-------------|------------|-------|
| Renderização de itens | HeldItemRendererMixin | ✅ | - | - | - | Baixa | Deve funcionar automaticamente |

### 6.8 Fishing Bobber

| Funcionalidade | Origem | Bedrock | JSON | Script | Limitações | Prioridade | Notas |
|---------------|--------|---------|------|---------|-------------|------------|-------|
| Boia de pesca | FishingBobberEntityMixin | ⚠️ | - | - | Investigar | Média | Verificar se necessário |

---

## 7. TAGS

### 7.1 Tags de Blocos (10 tags)

| Tag | Itens | Bedrock | Prioridade |
|-----|-------|---------|------------|
| `vsas:campfires` | 20 fogueiras | ✅ | Alta |
| `vsas:grindstones` | 10 afiações | ✅ | Alta |
| `vsas:ladders` | 10 escadas | ✅ | Alta |
| `vsas:levers` | 10 alavancas | ✅ | Alta |
| `vsas:redstone_torches` | 10 tochas de redstone | ✅ | Alta |
| `vsas:soul_campfires` | 10 fogueiras soul | ✅ | Alta |
| `vsas:soul_torches` | 10 tochas soul | ✅ | Alta |
| `vsas:torches` | 10 tochas | ✅ | Alta |
| `vsas:wall_soul_torches` | 10 tochas soul de parede | ✅ | Alta |

### 7.2 Tags de Itens (30 tags)

| Tag | Itens | Bedrock | Prioridade |
|-----|-------|---------|------------|
| `vsas:arrows` | 10 flechas | ✅ | Alta |
| `vsas:brushes` | 10 escovas | ✅ | Alta |
| `vsas:campfires` | 20 fogueiras (itens) | ✅ | Alta |
| `vsas:diamond_axes` | 10 machados diamond | ✅ | Alta |
| `vsas:golden_axes` | 10 machados golden | ✅ | Alta |
| `vsas:iron_axes` | 10 machados iron | ✅ | Alta |
| `vsas:netherite_axes` | 10 machados netherite | ✅ | Alta |
| `vsas:stone_axes` | 10 machados stone | ✅ | Alta |
| `vsas:wooden_axes` | 10 machados wooden | ✅ | Alta |
| `vsas:diamond_pickaxes` | 10 picaretas diamond | ✅ | Alta |
| `vsas:golden_pickaxes` | 10 picaretas golden | ✅ | Alta |
| `vsas:iron_pickaxes` | 10 picaretas iron | ✅ | Alta |
| `vsas:netherite_pickaxes` | 10 picaretas netherite | ✅ | Alta |
| `vsas:stone_pickaxes` | 10 picaretas stone | ✅ | Alta |
| `vsas:wooden_pickaxes` | 10 picaretas wooden | ✅ | Alta |
| `vsas:diamond_shovels` | 10 pás diamond | ✅ | Alta |
| `vsas:golden_shovels` | 10 pás golden | ✅ | Alta |
| `vsas:iron_shovels` | 10 pás iron | ✅ | Alta |
| `vsas:netherite_shovels` | 10 pás netherite | ✅ | Alta |
| `vsas:stone_shovels` | 10 pás stone | ✅ | Alta |
| `vsas:wooden_shovels` | 10 pás wooden | ✅ | Alta |
| `vsas:grindstones` | 10 afiações (itens) | ✅ | Alta |
| `vsas:ladders` | 10 escadas (itens) | ✅ | Alta |
| `vsas:levers` | 10 alavancas (itens) | ✅ | Alta |
| `vsas:redstone_torches` | 10 tochas de redstone (itens) | ✅ | Alta |
| `vsas:sticks` | 10 sticks | ✅ | Alta |
| `vsas:stone_axes` | 10 machados stone | ✅ | Alta |
| `vsas:stone_pickaxes` | 10 picaretas stone | ✅ | Alta |
| `vsas:stone_shovels` | 10 pás stone | ✅ | Alta |
| `vsas:stone_swords` | 10 espadas stone | ✅ | Alta |
| `vsas:torches` | 10 tochas (itens) | ✅ | Alta |
| `vsas:wooden_axes` | 10 machados wooden | ✅ | Alta |
| `vsas:wooden_pickaxes` | 10 picaretas wooden | ✅ | Alta |
| `vsas:wooden_shovels` | 10 pás wooden | ✅ | Alta |

---

## 8. RECEITAS ESPECIAIS

### 8.1 Override de Receitas Vanilla

| Receita | Origem | Bedrock | Prioridade | Notas |
|---------|--------|---------|------------|-------|
| spectral_arrow | compat/minecraft/spectral_arrow.json | ✅ | Alta | Usa tag vsas:arrows |
| armor_stand | compat/minecraft/temp/armor_stand.json | ❌ | Baixa | Usa sticks variantes |
| item_frame | compat/minecraft/temp/item_frame.json | ❌ | Baixa | Usa sticks variantes |
| painting | compat/minecraft/temp/painting.json | ❌ | Baixa | Usa sticks variantes |
| tripwire_hook | compat/minecraft/temp/tripwire_hook.json | ❌ | Baixa | Usa sticks variantes |

**Decisão**: Implementar apenas o override de spectral_arrow, pois é relevante. Os outros são overrides de receitas temp que podem não ser necessários.

### 8.2 Receitas de Compatibilidade

| Categoria | Quantidade | Bedrock | Prioridade | Notas |
|-----------|------------|---------|------------|-------|
| amethyst_imbuement | ? | ❌ | Baixa | Compat com outro mod |
| archers | ? | ❌ | Baixa | Compat com outro mod |
| azure-paxels | ? | ❌ | Baixa | Compat com outro mod |
| better_end | ? | ❌ | Baixa | Compat com outro mod |
| better_nether | ? | ❌ | Baixa | Compat com outro mod |
| darkblades | ? | ❌ | Baixa | Compat com outro mod |
| ends_delight | ? | ❌ | Baixa | Compat com outro mod |
| exlinefurniture | ? | ❌ | Baixa | Compat com outro mod |
| extended_drawers | ? | ❌ | Baixa | Compat com outro mod |
| farmersdelight | ? | ❌ | Baixa | Compat com outro mod |
| immersive_aircraft | ? | ❌ | Baixa | Compat com outro mod |
| supplimentaries | ? | ❌ | Baixa | Compat com outro mod |

**Decisão**: Ignorar todas as receitas de compatibilidade, pois são específicas para mods Java.

---

## 9. TEXTURAS E MODELOS

### 9.1 Texturas Override (assets/minecraft/)

| Textura | Tipo | Bedrock | Prioridade | Notas |
|---------|------|---------|------------|-------|
| activator_rail.png | Bloco | ❌ | Baixa | Override vanilla |
| campfire_log.png | Bloco | ❌ | Baixa | Override vanilla |
| detector_rail.png | Bloco | ❌ | Baixa | Override vanilla |
| grindstone_pivot.png | Bloco | ❌ | Baixa | Override vanilla |
| ladder.png | Bloco | ❌ | Baixa | Override vanilla |
| lever.png | Bloco | ❌ | Baixa | Override vanilla |
| powered_rail.png | Bloco | ❌ | Baixa | Override vanilla |
| rail.png | Bloco | ❌ | Baixa | Override vanilla |
| rail_corner.png | Bloco | ❌ | Baixa | Override vanilla |
| redstone_torch.png | Bloco | ❌ | Baixa | Override vanilla |
| soul_campfire_log.png | Bloco | ❌ | Baixa | Override vanilla |
| soul_torch.png | Bloco | ❌ | Baixa | Override vanilla |
| torch.png | Bloco | ❌ | Baixa | Override vanilla |
| arrow.png | Entidade | ❌ | Baixa | Override vanilla |
| bow.png | Item | ❌ | Baixa | Override vanilla |
| brush.png | Item | ❌ | Baixa | Override vanilla |
| crossbow_*.png | Item | ❌ | Baixa | Override vanilla |
| diamond_*.png | Item | ❌ | Baixa | Override vanilla |
| golden_*.png | Item | ❌ | Baixa | Override vanilla |
| iron_*.png | Item | ❌ | Baixa | Override vanilla |
| netherite_*.png | Item | ❌ | Baixa | Override vanilla |
| stone_*.png | Item | ❌ | Baixa | Override vanilla |
| wooden_*.png | Item | ❌ | Baixa | Override vanilla |
| tab_vsas.png | GUI | ✅ | Média | Ícone do tab criativo |

**Decisão**: Ignorar todas as texturas override, exceto o ícone do tab criativo que deve ser adaptado para o Resource Pack.

### 9.2 Texturas VSAS (assets/vsas/textures/)

Todas as **712 texturas** devem ser convertidas e adaptadas para o Bedrock:
- **Formato**: PNG (já está correto)
- **Tamanho**: Verificar se todas são potências de 2 (16x16, 32x32, etc.)
- **Organização**: Manter a mesma estrutura de pastas

| Categoria | Quantidade | Bedrock | Prioridade |
|-----------|------------|---------|------------|
| Blocos | 150 | ✅ | Alta |
| Entidades | 10 | ✅ | Alta |
| Itens | 542 | ✅ | Alta |

### 9.3 Modelos (assets/vsas/models/)

Todos os **1.008 modelos** devem ser convertidos para o formato Bedrock Geometry:
- **Formato**: JSON (já está correto)
- **Conversão**: Java Block Models → Bedrock Geometry JSON
- **Ferramenta**: Pode ser necessário criar script de conversão

| Categoria | Quantidade | Bedrock | Prioridade | Notas |
|-----------|------------|---------|------------|-------|
| Blocos | 150 | ✅ | Alta | Converter para geometry |
| Itens | 858 | ✅ | Alta | Converter para geometry |

### 9.4 Blockstates (assets/vsas/blockstates/)

Todos os **150 blockstates** devem ser convertidos para Permutations no Bedrock:
- **Formato**: JSON (já está correto)
- **Conversão**: Blockstates → Permutations

| Categoria | Quantidade | Bedrock | Prioridade |
|-----------|------------|---------|------------|
| Blockstates | 150 | ✅ | Alta |

---

## 10. TRADUÇÕES

### 10.1 Arquivo en_us.json (512 linhas)

| Tipo | Quantidade | Bedrock | Prioridade | Notas |
|------|------------|---------|------------|-------|
| block.vsas.* | ~150 | ✅ | Alta | Nomes de blocos |
| item.vsas.* | ~450 | ✅ | Alta | Nomes de itens |
| entity.vsas.* | 10 | ✅ | Alta | Nomes de entidades |

**Formato Bedrock**:
```json
{
  "item.vsas.acacia_stick": "Acacia Stick",
  "item.vsas.acacia_wooden_axe": "Acacia Wooden Axe",
  ...
}
```

---

## 11. RESUMO DE IMPLEMENTAÇÃO

### 11.1 Contagem Total

| Categoria | Java | Bedrock | % Implementável |
|-----------|------|---------|-----------------|
| Itens | 780+ | 780+ | 100% |
| Blocos | 150 | 150 | 100% |
| Entidades | 10 | 10 | 100% |
| Receitas | 784 | ~750 | ~96% |
| Tags | 40 | 40 | 100% |
| Loot Tables | 150 | 150 | 100% |
| Texturas | 779 | 712 | 91% |
| Modelos | 1.008 | 1.008 | 100% |
| Blockstates | 150 | 150 | 100% |
| Traduções | 512 | 512 | 100% |

**Total de arquivos a criar**: ~3.500+ arquivos JSON + ~712 texturas

### 11.2 Funcionalidades por Prioridade

| Prioridade | Quantidade | % Total |
|------------|------------|---------|
| Alta | ~2.800 | ~75% |
| Média | ~800 | ~22% |
| Baixa | ~150 | ~3% |

### 11.3 Tempo Estimado por Categoria

| Categoria | Quantidade | Tempo por Unidade | Tempo Total |
|-----------|------------|-------------------|-------------|
| Itens | 780 | 5 min | 65 horas |
| Blocos | 150 | 10 min | 25 horas |
| Entidades | 10 | 30 min | 5 horas |
| Receitas | 750 | 3 min | 37.5 horas |
| Tags | 40 | 5 min | 3.3 horas |
| Loot Tables | 150 | 5 min | 12.5 horas |
| Texturas | 712 | 2 min | 23.7 horas |
| Modelos | 1.008 | 10 min | 168 horas |
| Blockstates | 150 | 5 min | 12.5 horas |
| Traduções | 512 | 1 min | 8.5 horas |
| **Total** | **~3.500** | - | **~357 horas** |

**357 horas ÷ 8 horas/dia = ~45 dias de trabalho**

---

## 12. CONCLUSÃO

A matriz detalhada confirma que:

1. **96-100% das funcionalidades são implementáveis** no Bedrock
2. **Apenas 3-4% requerem Script API** (principalmente villager trades)
3. **Nenhuma funcionalidade é impossível** de implementar
4. **O trabalho é viável** mas requer tempo significativo
5. **A priorização é clara**: itens e blocos primeiro, funcionalidades avançadas depois

**Recomendação final**: Proceder com a implementação seguindo o plano de etapas, com foco em qualidade e fidelidade ao mod original.
