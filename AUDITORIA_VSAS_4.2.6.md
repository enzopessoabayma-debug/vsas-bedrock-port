# Auditoria Técnica Completa - Variant Sticks & Stuff (VSAS) 4.2.6
## Conversão para Minecraft Bedrock Add-On

---

## 1. INFORMAÇÕES GERAIS DO PROJETO ORIGINAL

### 1.1 Identificação
- **Nome**: Variant Sticks and Stuff (VSAS)
- **Versão**: 4.2.6
- **Autor**: Xanthian
- **Licença**: MIT License
- **Plataforma**: Minecraft Java Edition / Fabric Mod Loader
- **Versão Minecraft**: 1.20.2
- **Fabric API**: >= 0.14.20
- **Java**: >= 17

### 1.2 Licença e Créditos
```
The MIT License (MIT)

Copyright (c) 2020-2022 Xanthian

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```

**Requisito para Bedrock**: Preservar o arquivo LICENSE_vsas no root do Add-On e incluir créditos no manifest.json de ambos os packs.

---

## 2. ESTRUTURA DO ARQUIVO ORIGINAL

### 2.1 Arquivos Principais
```
vsas-4.2.6.zip (1.927.313 bytes, 3.840 arquivos)
├── LICENSE_vsas (1.079 bytes)
├── fabric.mod.json (800 bytes)
├── vsas.mixins.json (586 bytes)
├── vsas.accesswidener
├── vsas-refmap.json (17.016 bytes)
├── META-INF/
│   ├── MANIFEST.MF (411 bytes)
│   └── jars/
│       └── mixinextras-fabric-0.2.0-rc.4.jar (148.015 bytes)
├── assets/ (1.872 arquivos)
│   ├── minecraft/ (67 arquivos - overrides vanilla)
│   │   └── textures/
│   │       ├── block/ (18 arquivos - texturas override)
│   │       ├── entity/ (1 arquivo - arrow.png)
│   │       ├── item/ (30 arquivos - texturas override)
│   │       └── gui/container/creative_inventory/ (1 arquivo - tab_vsas.png)
│   └── vsas/ (1.872 arquivos)
│       ├── lang/ (1 arquivo - en_us.json, 512 linhas)
│       ├── blockstates/ (150 arquivos)
│       │   ├── campfires/ (20 arquivos)
│       │   ├── grindstones/ (10 arquivos)
│       │   ├── ladders/ (10 arquivos)
│       │   ├── levers/ (10 arquivos)
│       │   ├── rails/ (40 arquivos)
│       │   └── torches/ (60 arquivos)
│       ├── models/ (1.008 arquivos)
│       │   ├── block/ (150 arquivos)
│       │   │   ├── campfires/ (20 arquivos)
│       │   │   ├── grindstones/ (10 arquivos)
│       │   │   ├── ladders/ (10 arquivos)
│       │   │   ├── levers/ (10 arquivos)
│       │   │   ├── rails/ (40 arquivos)
│       │   │   └── torches/ (60 arquivos)
│       │   └── item/ (858 arquivos)
│       │       ├── arrows/ (10 arquivos)
│       │       ├── axes/ (90 arquivos)
│       │       ├── bows/ (10 arquivos)
│       │       ├── brushes/ (10 arquivos)
│       │       ├── campfires/ (20 arquivos)
│       │       ├── crossbows/ (10 arquivos)
│       │       ├── fishingrods/ (10 arquivos)
│       │       ├── grindstones/ (10 arquivos)
│       │       ├── hoes/ (90 arquivos)
│       │       ├── ladders/ (10 arquivos)
│       │       ├── levers/ (10 arquivos)
│       │       ├── onastick/ (10 arquivos)
│       │       ├── pickaxes/ (90 arquivos)
│       │       ├── rails/ (40 arquivos)
│       │       ├── shovels/ (90 arquivos)
│       │       ├── sticks/ (10 arquivos)
│       │       ├── swords/ (90 arquivos)
│       │       └── torches/ (60 arquivos)
│       └── textures/ (712 arquivos)
│           ├── block/ (150 arquivos)
│           │   ├── campfires/ (20 arquivos)
│           │   ├── grindstones/ (10 arquivos)
│           │   ├── ladders/ (10 arquivos)
│           │   ├── levers/ (10 arquivos)
│           │   ├── rails/ (40 arquivos)
│           │   └── torches/ (60 arquivos)
│           ├── entity/ (10 arquivos - arrows)
│           └── item/ (542 arquivos)
│               ├── arrows/ (10 arquivos)
│               ├── axes/ (90 arquivos)
│               ├── bows/ (10 arquivos)
│               ├── brushes/ (10 arquivos)
│               ├── campfires/ (20 arquivos)
│               ├── crossbows/ (10 arquivos)
│               ├── fishingrods/ (10 arquivos)
│               ├── grindstones/ (10 arquivos)
│               ├── hoes/ (90 arquivos)
│               ├── ladders/ (10 arquivos)
│               ├── levers/ (10 arquivos)
│               ├── onastick/ (10 arquivos)
│               ├── pickaxes/ (90 arquivos)
│               ├── rails/ (40 arquivos)
│               ├── shovels/ (90 arquivos)
│               ├── sticks/ (10 arquivos)
│               ├── swords/ (90 arquivos)
│               └── torches/ (60 arquivos)
├── data/ (1.484 arquivos)
│   └── vsas/ (1.484 arquivos)
│       ├── advancements/ (510 arquivos)
│       │   └── recipes/ (510 arquivos em 12 categorias)
│       ├── loot_tables/ (150 arquivos)
│       │   └── blocks/ (150 arquivos em 6 categorias)
│       ├── recipes/ (784 arquivos)
│       │   ├── arrows/ (10 arquivos)
│       │   ├── axes/ (90 arquivos)
│       │   ├── bows/ (10 arquivos)
│       │   ├── brushes/ (10 arquivos)
│       │   ├── campfires/ (20 arquivos)
│       │   ├── compat/ (274 arquivos - compatibilidade com outros mods)
│       │   │   ├── amethyst_imbuement/
│       │   │   ├── archers/
│       │   │   ├── azure-paxels/
│       │   │   ├── better_end/
│       │   │   ├── better_nether/
│       │   │   ├── darkblades/
│       │   │   ├── ends_delight/
│       │   │   ├── exlinefurniture/
│       │   │   ├── extended_drawers/
│       │   │   ├── farmersdelight/
│       │   │   ├── immersive_aircraft/
│       │   │   ├── minecraft/ (32 arquivos)
│       │   │   │   └── temp/ (4 arquivos)
│       │   │   └── supplimentaries/
│       │   ├── crossbows/ (10 arquivos)
│       │   ├── fishingrods/ (10 arquivos)
│       │   ├── grindstones/ (10 arquivos)
│       │   ├── hoes/ (90 arquivos)
│       │   ├── ladders/ (10 arquivos)
│       │   ├── levers/ (10 arquivos)
│       │   ├── onastick/ (10 arquivos)
│       │   ├── pickaxes/ (90 arquivos)
│       │   ├── rails/ (40 arquivos)
│       │   ├── shovels/ (90 arquivos)
│       │   ├── sticks/ (30 arquivos - 10 normais + 20 swap)
│       │   ├── swords/ (90 arquivos)
│       │   └── torches/ (60 arquivos)
│       └── tags/ (40 arquivos)
│           ├── blocks/ (10 arquivos)
│           └── items/ (30 arquivos)
└── net/ (112 arquivos .class - código compilado Java)
    └── xanthian/vsas/ (112 arquivos)
        ├── blocks/ (13 classes)
        │   ├── blocktypes/ (13 classes)
        │   ├── ActivatorRails.class
        │   ├── Campfires.class
        │   ├── DetectorRails.class
        │   ├── Grindstones.class
        │   ├── Ladders.class
        │   ├── Levers.class
        │   ├── PoweredRails.class
        │   ├── Rails.class
        │   ├── RedstoneTorches.class
        │   ├── SoulCampfires.class
        │   ├── SoulTorches.class
        │   └── Torches.class
        ├── datagen/ (7 classes)
        ├── entity/ (1 classe + 10 classes arrows)
        ├── items/ (10 classes)
        │   ├── arrows/ (10 classes)
        │   └── itemtypes/ (10 classes)
        ├── materials/ (1 classe)
        ├── mixin/ (12 classes)
        ├── renderer/ (11 classes - arrows renders)
        └── util/ (7 classes)
```

---

## 3. INVENTÁRIO DE VARIANTES DE MADEIRA

### 3.1 Tipos de Madeira Suportados (10 tipos)

| Tipo | ID VSAS | Descrição |
|------|---------|-----------|
| Oak | oak | Carvalho |
| Spruce | spruce | Pinheiro |
| Birch | birch | Bétula |
| Jungle | jungle | Selva |
| Acacia | acacia | Acácia |
| Dark Oak | dark_oak | Carvalho Escuro |
| Crimson | crimson | Carmim (Nether) |
| Warped | warped | Retorcido (Nether) |
| Bamboo | bamboo | Bambu |
| Cherry | cherry | Cerejeira |
| Mangrove | mangrove | Mangue |

### 3.2 Itens e Blocos por Categoria

#### 3.2.1 Sticks (Gravetos) - **10 itens**
- `vsas:sticks/{wood_type}_stick`
- Texturas: 10 arquivos PNG
- Modelos: 10 arquivos JSON (herdam de `minecraft:item/handheld`)
- Tags: `vsas:sticks`, `c:wood_sticks`

#### 3.2.2 Axes (Machados) - **90 itens**
- 10 tipos de madeira × 9 materiais = 90 itens
- Materiais: wooden, stone, iron, golden, diamond, netherite
- IDs: `vsas:axes/{wood_type}_{material}_axe`
- Texturas: 90 arquivos PNG
- Modelos: 90 arquivos JSON
- Tags: tags por material (wooden_axes, stone_axes, iron_axes, etc.)

#### 3.2.3 Pickaxes (Picaretas) - **90 itens**
- Mesma estrutura dos machados
- IDs: `vsas:pickaxes/{wood_type}_{material}_pickaxe`

#### 3.2.4 Shovels (Pás) - **90 itens**
- Mesma estrutura
- IDs: `vsas:shovels/{wood_type}_{material}_shovel`

#### 3.2.5 Swords (Espadas) - **90 itens**
- Mesma estrutura
- IDs: `vsas:swords/{wood_type}_{material}_sword`

#### 3.2.6 Hoes (Enxadas) - **90 itens**
- Mesma estrutura
- IDs: `vsas:hoes/{wood_type}_{material}_hoe`

#### 3.2.7 Bows (Arcos) - **10 itens**
- 10 tipos de madeira (apenas material wooden)
- IDs: `vsas:bows/{wood_type}_bow`
- Texturas: 10 arquivos PNG
- Modelos: 10 arquivos JSON

#### 3.2.8 Crossbows (Bestas) - **10 itens**
- Mesma estrutura dos arcos
- IDs: `vsas:crossbows/{wood_type}_crossbow`

#### 3.2.9 Fishing Rods (Varas de Pesca) - **10 itens**
- IDs: `vsas:fishingrods/{wood_type}_fishing_rod`

#### 3.2.10 Brushes (Escovas) - **10 itens**
- IDs: `vsas:brushes/{wood_type}_brush`

#### 3.2.11 On-a-Stick Items - **20 itens**
- Carrot on a Stick: 10 variantes (1 por madeira)
- Warped Fungus on a Stick: 10 variantes
- IDs: `vsas:onastick/{wood_type}_carrot_on_a_stick`
- IDs: `vsas:onastick/{wood_type}_warped_fungus_on_a_stick`

#### 3.2.12 Arrows (Flechas) - **10 itens + 1 entidade cada**
- IDs: `vsas:arrows/{wood_type}_arrow`
- Entidades: `vsas:{wood_type}_arrow` (ex: `vsas:acacia_arrow`)
- Renderers customizados para cada tipo

#### 3.2.13 Campfires (Fogueiras) - **20 blocos**
- 10 tipos de madeira × 2 variantes (normal e soul)
- IDs: `vsas:campfires/{wood_type}_campfire`
- IDs: `vsas:campfires/{wood_type}_soul_campfire`
- Blockstates: 20 arquivos JSON
- Modelos: 40 arquivos JSON (normal + off para cada)
- Texturas: 40 arquivos PNG

#### 3.2.14 Grindstones (Afiações) - **10 blocos**
- IDs: `vsas:grindstones/{wood_type}_grindstone`

#### 3.2.15 Ladders (Escadas) - **10 blocos**
- IDs: `vsas:ladders/{wood_type}_ladder`

#### 3.2.16 Levers (Alavancas) - **10 blocos**
- IDs: `vsas:levers/{wood_type}_lever`

#### 3.2.17 Rails (Trilhos) - **40 blocos**
- 10 tipos × 4 variantes: rail, powered_rail, detector_rail, activator_rail
- IDs: `vsas:rails/{wood_type}_rail`
- IDs: `vsas:rails/{wood_type}_powered_rail`
- IDs: `vsas:rails/{wood_type}_detector_rail`
- IDs: `vsas:rails/{wood_type}_activator_rail`

#### 3.2.18 Torches (Tochas) - **60 blocos**
- 10 tipos × 6 variantes: torch, soul_torch, redstone_torch, soul_redstone_torch + wall variants
- IDs: `vsas:torches/{wood_type}_torch`
- IDs: `vsas:torches/{wood_type}_soul_torch`
- IDs: `vsas:torches/{wood_type}_redstone_torch`
- IDs: `vsas:torches/{wood_type}_soul_redstone_torch`
- Wall variants também presentes

### 3.3 Resumo de Quantidades

| Categoria | Quantidade | Tipo |
|-----------|------------|------|
| Sticks | 10 | Item |
| Axes | 90 | Item |
| Pickaxes | 90 | Item |
| Shovels | 90 | Item |
| Swords | 90 | Item |
| Hoes | 90 | Item |
| Bows | 10 | Item |
| Crossbows | 10 | Item |
| Fishing Rods | 10 | Item |
| Brushes | 10 | Item |
| On-a-Stick | 20 | Item |
| Arrows | 10 | Item + Entidade |
| Campfires | 20 | Bloco |
| Grindstones | 10 | Bloco |
| Ladders | 10 | Bloco |
| Levers | 10 | Bloco |
| Rails | 40 | Bloco |
| Torches | 60 | Bloco |
| **Total** | **780 itens/blocos** | |

---

## 4. ANÁLISE DE RECEITAS

### 4.1 Receitas Principais (784 total)

#### 4.1.1 Receitas de Sticks
- **Receitas normais**: 10 receitas (1 por tipo de madeira)
  - Pattern: 2 planks vertical → 4 sticks
  - Exemplo: `acacia_planks` × 2 → `vsas:sticks/acacia_stick` × 4

- **Receitas swap**: 20 receitas
  - Pattern: 8 sticks + 1 stick central → 9 sticks do tipo
  - Usa tag `c:wood_sticks` para os sticks laterais
  - Permite conversão entre tipos de sticks

#### 4.1.2 Receitas de Ferramentas
- **Machados, Picaretas, Pás, Enxadas, Espadas**: 90 receitas cada = 450 total
  - Pattern padrão do Minecraft para cada tipo
  - Usam os sticks variantes como material do cabo
  - Exemplo: `acacia_wooden_axe` = 3 acacia_planks + 2 acacia_sticks

#### 4.1.3 Receitas de Armas
- **Arcos**: 10 receitas
  - Pattern: string + sticks variantes
- **Bestas**: 10 receitas
  - Pattern: iron_ingot + string + sticks variantes

#### 4.1.4 Receitas de Itens Especiais
- **Fishing Rods**: 10 receitas (3 sticks + 2 strings)
- **Brushes**: 10 receitas (copper_ingot + stick variado + feather)
- **On-a-Stick**: 20 receitas (fishing_rod variado + carrot/fungus)
- **Arrows**: 10 receitas (flint + stick variado + feather)

#### 4.1.5 Receitas de Blocos
- **Campfires**: 20 receitas (3 logs + coal + stick variado)
- **Soul Campfires**: 20 receitas (3 logs + soul_soil + stick variado)
- **Grindstones**: 10 receitas (2 stone_slabs + stick variado)
- **Ladders**: 10 receitas (7 sticks variantes)
- **Levers**: 10 receitas (1 cobblestone + 1 stick variado)
- **Rails**: 40 receitas (iron_ingot + sticks variantes)
- **Torches**: 60 receitas (coal/charcoal + stick variado)

#### 4.1.6 Receitas Smithing (Netherite)
- **Ferramentas de Netherite**: 90 receitas (1 por ferramenta diamond + netherite_ingot)
  - Exemplo: `vsas:axes/acacia_diamond_axe` + netherite_ingot → `vsas:axes/acacia_netherite_axe`

#### 4.1.7 Receitas de Compatibilidade (274 receitas)
- **Compat com outros mods**: 274 receitas
  - Integração com mods populares (Farmers Delight, Better End, etc.)
  - **NÃO RELEVANTE para Bedrock** - podem ser ignoradas

### 4.2 Overrides de Receitas Vanilla
- **spectral_arrow.json**: Modifica receita para usar tag `vsas:arrows` em vez de `minecraft:arrow`
  - Pattern: glowstone_dust + vsas:arrows → spectral_arrow × 2
- **Receitas temp**: 4 receitas temporárias em `compat/minecraft/temp/`
  - armor_stand, item_frame, painting, tripwire_hook
  - Usam sticks variantes em vez de sticks vanilla

### 4.3 Tags de Itens e Blocos

#### 4.3.1 Tags de Blocos (10 tags)
- `vsas:campfires` - Todas as fogueiras variantes
- `vsas:grindstones` - Todas as afiações variantes
- `vsas:ladders` - Todas as escadas variantes
- `vsas:levers` - Todas as alavancas variantes
- `vsas:redstone_torches` - Todas as tochas de redstone variantes
- `vsas:soul_campfires` - Todas as fogueiras soul variantes
- `vsas:soul_torches` - Todas as tochas soul variantes
- `vsas:torches` - Todas as tochas variantes
- `vsas:wall_soul_torches` - Tochas soul de parede

#### 4.3.2 Tags de Itens (30 tags)
- `vsas:arrows` - Todas as flechas variantes
- `vsas:brushes` - Todas as escovas variantes
- `vsas:campfires` - Todos os itens de fogueira
- Materiais específicos:
  - `vsas:diamond_axes`, `vsas:golden_axes`, `vsas:iron_axes`, `vsas:netherite_axes`, `vsas:stone_axes`, `vsas:wooden_axes`
  - `vsas:diamond_pickaxes`, `vsas:golden_pickaxes`, etc.
  - `vsas:diamond_shovels`, etc.
  - `vsas:netherite_hoes`, etc.
- `vsas:grindstones` - Itens de afiação
- `vsas:ladders` - Itens de escada
- `vsas:levers` - Itens de alavanca
- `vsas:redstone_torches` - Itens de tocha de redstone
- `vsas:sticks` - Todos os sticks variantes
- `vsas:stone_axes`, `vsas:stone_pickaxes`, `vsas:stone_shovels`
- `vsas:stone_swords`
- `vsas:torches` - Todos os itens de tocha
- `vsas:wooden_axes`, `vsas:wooden_pickaxes`, `vsas:wooden_shovels`

---

## 5. ANÁLISE DE COMPORTAMENTOS ESPECIAIS (Java/Fabric)

### 5.1 Mixins (Injeção de Código)

#### 5.1.1 Mixins de Entidades
| Mixin | Classe Alvo | Função |
|-------|-------------|--------|
| `AbstractClientPlayerEntityMixin` | AbstractClientPlayerEntity | Modifica renderização do jogador |
| `AbstractMinecartEntityMixin` | AbstractMinecartEntity | Permite minecarts usarem rails variantes |
| `FishingBobberEntityMixin` | FishingBobberEntity | Modifica comportamento da boia de pesca |
| `FishingBobberEntityRendererMixin` | FishingBobberEntityRenderer | Renderização da boia |
| `PigEntityMixin` | PigEntity | Permite porcos usarem saddles com sticks variantes? |
| `StriderEntityMixin` | StriderEntity | Permite striders usarem sticks variantes como bastão |

#### 5.1.2 Mixins de Blocos
| Mixin | Classe Alvo | Função |
|-------|-------------|--------|
| `BlockEntityTypeMixin` | BlockEntityType | Registra tipos de entidade de bloco |
| `GrindstoneScreenHandlerMixin` | GrindstoneScreenHandler | Modifica interface da afiação |
| `PoweredRailBlockMixin` | PoweredRailBlock | Permite powered rails variantes |

#### 5.1.3 Mixins de Renderização
| Mixin | Classe Alvo | Função |
|-------|-------------|--------|
| `HeldItemRendererMixin` | HeldItemRenderer | Renderização de itens seguros |

#### 5.1.4 Mixins de POI (Points of Interest)
| Mixin | Classe Alvo | Função |
|-------|-------------|--------|
| `PointOfInterestTypesAccessor` | PointOfInterestTypes | Acessa tipos de POI para villager trades |

### 5.2 Classes Principais de Blocos

#### 5.2.1 Campfires (Fogueiras)
- `Campfires.class` - Classe principal
- `VariantCampfireBlock.class` - Bloco variante
- **Comportamento**: Fogueiras com texturas e modelos baseados no tipo de madeira
- **Loot Tables**: Retorna o bloco quando minerado com Silk Touch, senão charcoal

#### 5.2.2 Grindstones (Afiações)
- `Grindstones.class`
- `VariantGrindstoneBlock.class`
- **Comportamento**: Afiações com aparência de madeira variada

#### 5.2.3 Ladders (Escadas)
- `Ladders.class`
- `VariantLadderBlock.class`
- **Comportamento**: Escadas com textura de madeira variada

#### 5.2.4 Levers (Alavancas)
- `Levers.class`
- `VariantLeverBlock.class`
- **Comportamento**: Alavancas com textura de madeira variada

#### 5.2.5 Rails (Trilhos)
- `Rails.class` - Trilhos normais
- `PoweredRails.class` - Trilhos energizados
- `DetectorRails.class` - Trilhos detectores
- `ActivatorRails.class` - Trilhos ativadores
- `VariantRailBlock.class`, `VariantPoweredRailBlock.class`, etc.
- **Comportamento**: Todos os tipos de trilhos com textura de madeira variada
- **Mixin**: `PoweredRailBlockMixin` permite que powered rails variantes funcionem

#### 5.2.6 Torches (Tochas)
- `Torches.class` - Tochas normais
- `SoulTorches.class` - Tochas soul
- `RedstoneTorches.class` - Tochas de redstone
- `VariantTorchBlock.class`, `VariantSoulTorchBlock.class`, etc.
- **Comportamento**: Tochas com textura de madeira variada

### 5.3 Classes Principais de Itens

#### 5.3.1 Ferramentas
- `Axes.class`, `Pickaxes.class`, `Shovels.class`, `Hoes.class`, `Swords.class`
- `VariantAxeItem.class`, `VariantPickaxeItem.class`, etc.
- **Comportamento**: Ferramentas com danos e durabilidade baseados no material e tipo de madeira

#### 5.3.2 Armas
- `Bows.class`, `Crossbows.class`
- `VariantBowItem.class`, `VariantCrossbowItem.class`
- **Comportamento**: Arcos e bestas com texturas variantes

#### 5.3.3 Itens Especiais
- `Sticks.class` - Sticks variantes
- `Arrows.class` - Flechas variantes
- `Brushes.class` - Escovas variantes
- `FishingRods.class` - Varas de pesca variantes
- `OnAStick.class` - Itens no palito (carrot, fungus)
- **Classes de itens específicos**:
  - `AcaciaArrowItem.class`, `BambooArrowItem.class`, etc.
  - `VariantCarrotOnAStickItem.class`, `VariantFungusOnAStickItem.class`

### 5.4 Entidades

#### 5.4.1 Arrow Entities
- 10 classes de entidade de flecha (1 por tipo de madeira)
- `AcaciaArrowEntity.class`, `BambooArrowEntity.class`, etc.
- **Comportamento**: Flechas com texturas e possivelmente danos variantes
- **Renderers**: Renderizadores customizados para cada tipo

#### 5.4.2 EntityInit
- `EntityInit.class` - Inicialização de entidades
- Registra as entidades de flecha variantes

### 5.5 Utilitários

#### 5.5.1 Villager Trades
- `VillagerTrades.class` (26.257 bytes)
- **Função**: Adiciona trades de vilageiros para comprar itens variantes
- **Importância**: Permite que villagers vendam itens VSAS

#### 5.5.2 Loot Table Modifiers
- `LootTableModifiers.class`
- **Função**: Modifica loot tables para incluir itens variantes

#### 5.5.3 ModRegistries
- `ModRegistries.class`
- **Função**: Registra todos os itens, blocos e entidades do mod

#### 5.5.4 ModItemGroup
- `ModItemGroup.class` (28.189 bytes)
- **Função**: Cria o tab criativo do VSAS
- **Ícone**: `assets/vsas/icon.png`

#### 5.5.5 Data Generators
- `DataGenerator.class` - Gera dados do mod
- `BlockTagGenerator.class`, `ItemTagGenerator.class` - Geram tags
- `LangFileGenerator.class` - Gera arquivos de linguagem
- `LootTableGenerator.class` - Gera loot tables
- `ModelGenerator.class` - Gera modelos
- `RecipeGenerator.class` - Gera receitas

---

## 6. ANÁLISE DE RECURSOS VISUAIS

### 6.1 Texturas Override (assets/minecraft/)
- **67 arquivos** que sobrescrevem texturas vanilla
- **Blocos**: activator_rail, campfire_log, detector_rail, grindstone_pivot, ladder, lever, powered_rail, rail, rail_corner, redstone_torch, soul_campfire_log, soul_torch, torch
- **Entidades**: arrow
- **Itens**: arrow, bow, brush, campfire, crossbow_*, diamond_*, golden_*, iron_*, netherite_*, soul_campfire, stone_*, wooden_*
- **GUI**: tab_vsas.png (ícone do tab criativo)

**Observação**: Estas texturas são overrides para fazer os itens vanilla usarem as texturas variantes quando apropriado.

### 6.2 Texturas VSAS (assets/vsas/textures/)
- **712 arquivos** de texturas customizadas

#### 6.2.1 Texturas de Blocos (150)
- Campfires: 40 texturas (20 normais + 20 soul)
- Grindstones: 10 texturas
- Ladders: 10 texturas
- Levers: 10 texturas
- Rails: 40 texturas (10 por tipo × 4 variantes)
- Torches: 60 texturas (10 por tipo × 6 variantes)

#### 6.2.2 Texturas de Entidades (10)
- Arrows: 10 texturas (1 por tipo de madeira)

#### 6.2.3 Texturas de Itens (542)
- Arrows: 10 texturas
- Axes: 90 texturas
- Bows: 10 texturas
- Brushes: 10 texturas
- Campfires: 20 texturas
- Crossbows: 10 texturas
- Fishing Rods: 10 texturas
- Grindstones: 10 texturas
- Hoes: 90 texturas
- Ladders: 10 texturas
- Levers: 10 texturas
- On-a-Stick: 10 texturas
- Pickaxes: 90 texturas
- Rails: 40 texturas
- Shovels: 90 texturas
- Sticks: 10 texturas
- Swords: 90 texturas
- Torches: 60 texturas

### 6.3 Modelos 3D (assets/vsas/models/)
- **1.008 arquivos** de modelos JSON

#### 6.3.1 Modelos de Blocos (150)
- Todos os blocos têm modelos customizados
- Campfires: Modelos complexos com elementos de fogo
- Grindstones: Modelos com partes giratórias
- Rails: Modelos com conexões
- Torches: Modelos com chama

#### 6.3.2 Modelos de Itens (858)
- Todos os itens têm modelos
- Herdam de `minecraft:item/handheld` para itens seguros
- Modelos customizados para itens especiais (bows, crossbows, etc.)

### 6.4 Blockstates (assets/vsas/blockstates/)
- **150 arquivos** definindo estados dos blocos
- Campfires: facing + lit states
- Rails: connected states
- Levers: powered states
- Torches: wall variants

### 6.5 Traduções (assets/vsas/lang/en_us.json)
- **512 linhas** de tradução
- Cobre todos os itens, blocos e entidades
- Formato: `block.vsas.{category}.{wood_type}_{item}`, `item.vsas.{category}.{wood_type}_{item}`, `entity.vsas.{wood_type}_{item}`

---

## 7. ANÁLISE DE LOOT TABLES

### 7.1 Loot Tables de Blocos (150 arquivos)
- **Campfires**: 20 loot tables
  - Silk Touch: Retorna o bloco
  - Normal: Retorna charcoal (2 unidades se survives_explosion)
- **Grindstones**: 10 loot tables
  - Retorna o bloco
- **Ladders**: 10 loot tables
  - Retorna o bloco
- **Levers**: 10 loot tables
  - Retorna o bloco
- **Rails**: 40 loot tables
  - Retorna o bloco
- **Torches**: 60 loot tables
  - Retorna o bloco

---

## 8. ANÁLISE DE ADVANCEMENTS

### 8.1 Advancements de Receitas (510 arquivos)
- Organizados em 12 categorias:
  - combat/arrows (10)
  - combat/bows (10)
  - combat/crossbows (10)
  - decorations/campfires (20)
  - decorations/grindstones (10)
  - decorations/ladders (10)
  - decorations/torches (20)
  - misc/sticks (20)
  - redstone/levers (10)
  - redstone/torches (20)
  - tools/axes (90)
  - tools/brushes (10)
  - tools/fishingrods (10)
  - tools/hoes (90)
  - tools/pickaxes (90)
  - tools/shovels (90)
  - tools/swords (90)
  - transportation/onastick (10)
  - transportation/rails (40)

- **Estrutura**: Cada advancement desbloqueia uma receita específica
- **Requisitos**: Ter o item base (stick, plank, etc.) e a receita desbloqueada

---

## 9. MATRIZ DE COMPATIBILIDADE JAVA/FABRIC → BEDROCK

### 9.1 Legenda
- ✅ **Direto**: Pode ser implementado diretamente com JSON/Componentes
- 🟡 **Adaptação**: Requer adaptação ou workarounds
- 🔧 **Script API**: Requer Script API do Bedrock
- ❌ **Limitado**: Funcionalidade limitada ou não disponível
- ⚠️ **Investigar**: Requer investigação adicional

### 9.2 Matriz Detalhada

#### 9.2.1 Itens Básicos

| Funcionalidade | Origem | Comportamento | Bedrock | JSON/Componentes | Script API | Limitações | Prioridade |
|---------------|--------|---------------|---------|------------------|-------------|-------------|------------|
| Sticks variantes | `vsas:sticks/*` | Itens com textura variada | ✅ | Item JSON + Texture | - | - | Alta |
| Tags de sticks | `vsas:sticks` | Agrupamento de sticks | ✅ | Tag JSON | - | - | Alta |

#### 9.2.2 Ferramentas

| Funcionalidade | Origem | Comportamento | Bedrock | JSON/Componentes | Script API | Limitações | Prioridade |
|---------------|--------|---------------|---------|------------------|-------------|-------------|------------|
| Machados variantes | `vsas:axes/*` | Ferramentas com danos/durabilidade | ✅ | Item JSON + Components | - | - | Alta |
| Picaretas variantes | `vsas:pickaxes/*` | Ferramentas com danos/durabilidade | ✅ | Item JSON + Components | - | - | Alta |
| Pás variantes | `vsas:shovels/*` | Ferramentas com danos/durabilidade | ✅ | Item JSON + Components | - | - | Alta |
| Enxadas variantes | `vsas:hoes/*` | Ferramentas com danos/durabilidade | ✅ | Item JSON + Components | - | - | Alta |
| Espadas variantes | `vsas:swords/*` | Ferramentas com danos/durabilidade | ✅ | Item JSON + Components | - | - | Alta |
| Tags de ferramentas | `vsas:*_axes`, etc. | Agrupamento | ✅ | Tag JSON | - | - | Alta |

#### 9.2.3 Armas

| Funcionalidade | Origem | Comportamento | Bedrock | JSON/Componentes | Script API | Limitações | Prioridade |
|---------------|--------|---------------|---------|------------------|-------------|-------------|------------|
| Arcos variantes | `vsas:bows/*` | Armas com textura variada | ✅ | Item JSON + Components | - | - | Alta |
| Bestas variantes | `vsas:crossbows/*` | Armas com textura variada | ✅ | Item JSON + Components | - | - | Alta |
| Flechas variantes | `vsas:arrows/*` | Flechas com textura variada | 🟡 | Item JSON + Entity JSON | 🔧 | Entidades customizadas | Alta |
| Tags de armas | `vsas:arrows`, etc. | Agrupamento | ✅ | Tag JSON | - | - | Alta |

#### 9.2.4 Itens Especiais

| Funcionalidade | Origem | Comportamento | Bedrock | JSON/Componentes | Script API | Limitações | Prioridade |
|---------------|--------|---------------|---------|------------------|-------------|-------------|------------|
| Escovas variantes | `vsas:brushes/*` | Itens com textura variada | ✅ | Item JSON | - | - | Alta |
| Varas de pesca variantes | `vsas:fishingrods/*` | Itens com textura variada | ✅ | Item JSON + Components | - | - | Alta |
| Carrot on a Stick | `vsas:onastick/*` | Itens com textura variada | ✅ | Item JSON + Components | - | - | Alta |
| Warped Fungus on a Stick | `vsas:onastick/*` | Itens com textura variada | ✅ | Item JSON + Components | - | - | Alta |

#### 9.2.5 Blocos

| Funcionalidade | Origem | Comportamento | Bedrock | JSON/Componentes | Script API | Limitações | Prioridade |
|---------------|--------|---------------|---------|------------------|-------------|-------------|------------|
| Fogueiras variantes | `vsas:campfires/*` | Blocos com textura variada | ✅ | Block JSON + Components | - | - | Alta |
| Soul Campfires | `vsas:campfires/*_soul` | Blocos com comportamento soul | ✅ | Block JSON + Components | - | - | Alta |
| Afiações variantes | `vsas:grindstones/*` | Blocos com textura variada | ✅ | Block JSON | - | Interface não customizável | Média |
| Escadas variantes | `vsas:ladders/*` | Blocos com textura variada | ✅ | Block JSON | - | - | Alta |
| Alavancas variantes | `vsas:levers/*` | Blocos com textura variada | ✅ | Block JSON + Components | - | - | Alta |
| Trilhos variantes | `vsas:rails/*` | Blocos com textura variada | ✅ | Block JSON | - | Conexão com minecarts | Alta |
| Powered Rails | `vsas:rails/*_powered` | Trilhos energizados | ✅ | Block JSON + Components | - | - | Alta |
| Detector Rails | `vsas:rails/*_detector` | Trilhos detectores | ✅ | Block JSON + Components | - | - | Alta |
| Activator Rails | `vsas:rails/*_activator` | Trilhos ativadores | ✅ | Block JSON + Components | - | - | Alta |
| Tochas variantes | `vsas:torches/*` | Blocos com textura variada | ✅ | Block JSON | - | - | Alta |
| Soul Torches | `vsas:torches/*_soul` | Tochas soul | ✅ | Block JSON | - | - | Alta |
| Redstone Torches | `vsas:torches/*_redstone` | Tochas de redstone | ✅ | Block JSON + Components | - | - | Alta |
| Wall Torches | `vsas:torches/*_wall` | Tochas de parede | ✅ | Block JSON | - | - | Alta |

#### 9.2.6 Entidades

| Funcionalidade | Origem | Comportamento | Bedrock | JSON/Componentes | Script API | Limitações | Prioridade |
|---------------|--------|---------------|---------|------------------|-------------|-------------|------------|
| Flechas variantes | `vsas:{wood}_arrow` | Entidades com textura variada | 🟡 | Entity JSON | 🔧 | Renderização customizada | Alta |

#### 9.2.7 Comportamentos Especiais

| Funcionalidade | Origem | Comportamento | Bedrock | JSON/Componentes | Script API | Limitações | Prioridade |
|---------------|--------|---------------|---------|------------------|-------------|-------------|------------|
| Minecart em rails variantes | Mixin | Permite minecarts usarem rails | ✅ | - | - | Testar compatibilidade | Alta |
| Strider com sticks | Mixin | Striders usam sticks como bastão | ❌ | - | - | Não há striders no Bedrock? | Baixa |
| Pig com saddle | Mixin | Possível interação | ❌ | - | - | Não aplicável | Baixa |
| Villager Trades | VillagerTrades.class | Villagers vendem itens VSAS | 🟡 | - | 🔧 | Requer Script API | Média |
| Loot Table Modifiers | LootTableModifiers.class | Modifica loot tables | ✅ | Loot Table JSON | - | - | Média |
| Grindstone Interface | Mixin | Interface customizada | ❌ | - | - | Não customizável no Bedrock | Baixa |

#### 9.2.8 Receitas

| Funcionalidade | Origem | Comportamento | Bedrock | JSON/Componentes | Script API | Limitações | Prioridade |
|---------------|--------|---------------|---------|------------------|-------------|-------------|------------|
| Receitas de crafting | RecipeGenerator | Receitas de crafting | ✅ | Recipe JSON | - | - | Alta |
| Receitas smithing | RecipeGenerator | Upgrade para netherite | ✅ | Recipe JSON | - | - | Alta |
| Receitas swap | RecipeGenerator | Conversão entre sticks | ✅ | Recipe JSON | - | - | Média |
| Override spectral_arrow | compat/minecraft | Usa tag vsas:arrows | ✅ | Recipe JSON | - | - | Alta |

#### 9.2.9 Texturas e Modelos

| Funcionalidade | Origem | Comportamento | Bedrock | JSON/Componentes | Script API | Limitações | Prioridade |
|---------------|--------|---------------|---------|------------------|-------------|-------------|------------|
| Texturas de itens | assets/vsas/textures/item/ | Texturas customizadas | ✅ | Texture PNG | - | - | Alta |
| Texturas de blocos | assets/vsas/textures/block/ | Texturas customizadas | ✅ | Texture PNG | - | - | Alta |
| Texturas de entidades | assets/vsas/textures/entity/ | Texturas de flechas | ✅ | Texture PNG | - | - | Alta |
| Modelos de itens | assets/vsas/models/item/ | Modelos 3D | ✅ | Model JSON | - | Converter para formato Bedrock | Alta |
| Modelos de blocos | assets/vsas/models/block/ | Modelos 3D | ✅ | Model JSON | - | Converter para formato Bedrock | Alta |
| Blockstates | assets/vsas/blockstates/ | Estados de bloco | ✅ | - | - | Usar permutations no Bedrock | Alta |
| Override texturas vanilla | assets/minecraft/ | Sobrescreve texturas | ❌ | - | - | Não aplicável no Bedrock | Baixa |

#### 9.2.10 Traduções

| Funcionalidade | Origem | Comportamento | Bedrock | JSON/Componentes | Script API | Limitações | Prioridade |
|---------------|--------|---------------|---------|------------------|-------------|-------------|------------|
| Traduções en_us | assets/vsas/lang/en_us.json | Nomes de itens/blocos | ✅ | Language JSON | - | - | Alta |

#### 9.2.11 Tags

| Funcionalidade | Origem | Comportamento | Bedrock | JSON/Componentes | Script API | Limitações | Prioridade |
|---------------|--------|---------------|---------|------------------|-------------|-------------|------------|
| Tags de blocos | data/vsas/tags/blocks/ | Agrupamento de blocos | ✅ | Tag JSON | - | - | Alta |
| Tags de itens | data/vsas/tags/items/ | Agrupamento de itens | ✅ | Tag JSON | - | - | Alta |

#### 9.2.12 Loot Tables

| Funcionalidade | Origem | Comportamento | Bedrock | JSON/Componentes | Script API | Limitações | Prioridade |
|---------------|--------|---------------|---------|------------------|-------------|-------------|------------|
| Loot de blocos | data/vsas/loot_tables/ | Drop de blocos | ✅ | Loot Table JSON | - | - | Alta |

---

## 10. ARQUITETURA PROPOSTA PARA BEDROCK

### 10.1 Estrutura de Pastas

```
vsas-bedrock-addon/
├── LICENSE_vsas (original)
├── README.md
├── CHANGELOG.md
├── Behavior Pack/
│   ├── manifest.json
│   ├── packs/
│   │   └── vsas_behavior/
│   │       ├── entities/
│   │       │   ├── vsas_arrow.json
│   │       │   └── ... (outras entidades se necessárias)
│   │       ├── items/
│   │       │   ├── sticks/
│   │       │   │   ├── vsas_acacia_stick.json
│   │       │   │   ├── vsas_bamboo_stick.json
│   │       │   │   └── ... (todos os sticks)
│   │       │   ├── axes/
│   │       │   │   ├── vsas_acacia_wooden_axe.json
│   │       │   │   └── ...
│   │       │   ├── bows/
│   │       │   ├── crossbows/
│   │       │   ├── brushes/
│   │       │   ├── fishingrods/
│   │       │   ├── hoes/
│   │       │   ├── onastick/
│   │       │   ├── pickaxes/
│   │       │   ├── shovels/
│   │       │   ├── swords/
│   │       │   ├── arrows/
│   │       │   ├── campfires/
│   │       │   ├── grindstones/
│   │       │   ├── ladders/
│   │       │   ├── levers/
│   │       │   ├── rails/
│   │       │   └── torches/
│   │       ├── blocks/
│   │       │   ├── campfires/
│   │       │   ├── grindstones/
│   │       │   ├── ladders/
│   │       │   ├── levers/
│   │       │   ├── rails/
│   │       │   └── torches/
│   │       ├── recipes/
│   │       │   ├── sticks/
│   │       │   ├── axes/
│   │       │   ├── bows/
│   │       │   ├── brushes/
│   │       │   ├── campfires/
│   │       │   ├── crossbows/
│   │       │   ├── fishingrods/
│   │       │   ├── grindstones/
│   │       │   ├── hoes/
│   │       │   ├── ladders/
│   │       │   ├── levers/
│   │       │   ├── onastick/
│   │       │   ├── pickaxes/
│   │       │   ├── rails/
│   │       │   ├── shovels/
│   │       │   ├── swords/
│   │       │   ├── torches/
│   │       │   └── compat/
│   │       ├── loot_tables/
│   │       │   ├── blocks/
│   │       │   │   ├── campfires/
│   │       │   │   ├── grindstones/
│   │       │   │   ├── ladders/
│   │       │   │   ├── levers/
│   │       │   │   ├── rails/
│   │       │   │   └── torches/
│   │       ├── tags/
│   │       │   ├── items/
│   │       │   └── blocks/
│   │       └── scripts/
│   │           ├── client/
│   │           │   └── villager_trades.js (se necessário)
│   │           └── server/
│   └── manifest.json
└── Resource Pack/
    ├── manifest.json
    └── packs/
        └── vsas_resource/
            ├── lang/
            │   └── en_US.json
            ├── models/
            │   ├── items/
            │   │   ├── sticks/
            │   │   ├── axes/
            │   │   ├── bows/
            │   │   ├── brushes/
            │   │   ├── crossbows/
            │   │   ├── fishingrods/
            │   │   ├── hoes/
            │   │   ├── onastick/
            │   │   ├── pickaxes/
            │   │   ├── shovels/
            │   │   ├── swords/
            │   │   ├── arrows/
            │   │   ├── campfires/
            │   │   ├── grindstones/
            │   │   ├── ladders/
            │   │   ├── levers/
            │   │   ├── rails/
            │   │   └── torches/
            │   └── blocks/
            │       ├── campfires/
            │       ├── grindstones/
            │       ├── ladders/
            │       ├── levers/
            │       ├── rails/
            │       └── torches/
            ├── textures/
            │   ├── items/
            │   │   ├── sticks/
            │   │   ├── axes/
            │   │   ├── bows/
            │   │   ├── brushes/
            │   │   ├── crossbows/
            │   │   ├── fishingrods/
            │   │   ├── hoes/
            │   │   ├── onastick/
            │   │   ├── pickaxes/
            │   │   ├── shovels/
            │   │   ├── swords/
            │   │   ├── arrows/
            │   │   ├── campfires/
            │   │   ├── grindstones/
            │   │   ├── ladders/
            │   │   ├── levers/
            │   │   ├── rails/
            │   │   └── torches/
            │   ├── blocks/
            │   │   ├── campfires/
            │   │   ├── grindstones/
            │   │   ├── ladders/
            │   │   ├── levers/
            │   │   ├── rails/
            │   │   └── torches/
            │   └── entities/
            │       └── arrows/
            └── sounds/
                └── (se necessário)
```

### 10.2 Nomenclatura de IDs

**Regra**: Remover barras "/" dos IDs originais do Java.

| Java ID | Bedrock ID |
|---------|------------|
| `vsas:sticks/oak_stick` | `vsas:oak_stick` ou `vsas:stick_oak` |
| `vsas:axes/acacia_wooden_axe` | `vsas:acacia_wooden_axe` |
| `vsas:campfires/oak_campfire` | `vsas:oak_campfire` |
| `vsas:torches/spruce_soul_torch` | `vsas:spruce_soul_torch` |

**Padrão recomendado**: `{namespace}:{category}_{wood_type}_{material}_{item_type}`
- Exemplo: `vsas:axe_acacia_wooden` ou `vsas:acacia_wooden_axe`

**Decisão**: Usar o padrão `vsas:{wood_type}_{material}_{item}` para itens e `vsas:{wood_type}_{block}` para blocos, removendo a categoria do path.

### 10.3 Componentes de Itens

#### 10.3.1 Sticks
```json
{
  "format_version": "1.21.0",
  "minecraft:item": {
    "description": {
      "identifier": "vsas:acacia_stick",
      "category": "items"
    },
    "components": {
      "minecraft:icon": "vsas:item/sticks/acacia_stick",
      "minecraft:display_name": "Acacia Stick",
      "minecraft:max_stack_size": 64,
      "minecraft:creative_category": "Construction",
      "minecraft:tags": ["vsas:sticks", "wood_sticks"]
    }
  }
}
```

#### 10.3.2 Ferramentas (exemplo: Machado)
```json
{
  "format_version": "1.21.0",
  "minecraft:item": {
    "description": {
      "identifier": "vsas:acacia_wooden_axe",
      "category": "equipment"
    },
    "components": {
      "minecraft:icon": "vsas:item/axes/acacia_wooden_axe",
      "minecraft:display_name": "Acacia Wooden Axe",
      "minecraft:max_stack_size": 1,
      "minecraft:durability": 59,
      "minecraft:attack_damage": 6,
      "minecraft:attack_speed": -3.2,
      "minecraft:enchantable": {
        "value": 15,
        "slot": "mainhand"
      },
      "minecraft:repairable": {
        "repair_items": ["minecraft:acacia_planks"]
      },
      "minecraft:creative_category": "Equipment",
      "minecraft:tags": ["vsas:wooden_axes", "wooden_axes"]
    }
  }
}
```

#### 10.3.3 Armas (exemplo: Arco)
```json
{
  "format_version": "1.21.0",
  "minecraft:item": {
    "description": {
      "identifier": "vsas:acacia_bow",
      "category": "equipment"
    },
    "components": {
      "minecraft:icon": "vsas:item/bows/acacia_bow",
      "minecraft:display_name": "Acacia Bow",
      "minecraft:max_stack_size": 1,
      "minecraft:durability": 384,
      "minecraft:enchantable": {
        "value": 1,
        "slot": "mainhand"
      },
      "minecraft:repairable": {
        "repair_items": ["minecraft:acacia_planks"]
      },
      "minecraft:creative_category": "Equipment",
      "minecraft:tags": ["vsas:bows", "bows"],
      "minecraft:use_duration": 72000,
      "minecraft:cooldown": {
        "category": "bow",
        "duration": 1.0
      }
    }
  }
}
```

### 10.4 Componentes de Blocos

#### 10.4.1 Fogueira (Campfire)
```json
{
  "format_version": "1.21.0",
  "minecraft:block": {
    "description": {
      "identifier": "vsas:acacia_campfire",
      "register_to_creative_menu": true
    },
    "components": {
      "minecraft:display_name": "Acacia Campfire",
      "minecraft:material_instances": {
        "*": {
          "texture": "vsas:block/campfires/acacia_campfire",
          "render_method": "opaque"
        }
      },
      "minecraft:light_emission": 15,
      "minecraft:light_dampening": 0,
      "minecraft:flammable": {
        "burn_odds": 0,
        "flame_odds": 0
      },
      "minecraft:destructible_by_mining": {
        "seconds_to_destroy": 0.5
      },
      "minecraft:placement_rule": {
        "can_place_on": ["minecraft:solid_block"]
      },
      "minecraft:tags": ["vsas:campfires", "campfire"]
    },
    "permutations": [
      {
        "condition": "q.block_state('lit') == 1b",
        "components": {
          "minecraft:material_instances": {
            "*": {
              "texture": "vsas:block/campfires/acacia_campfire_lit",
              "render_method": "opaque"
            }
          },
          "minecraft:light_emission": 15
        }
      }
    ]
  }
}
```

#### 10.4.2 Trilho (Rail)
```json
{
  "format_version": "1.21.0",
  "minecraft:block": {
    "description": {
      "identifier": "vsas:acacia_rail",
      "register_to_creative_menu": true
    },
    "components": {
      "minecraft:display_name": "Acacia Rail",
      "minecraft:material_instances": {
        "*": {
          "texture": "vsas:block/rails/acacia_rail",
          "render_method": "opaque"
        }
      },
      "minecraft:destructible_by_mining": {
        "seconds_to_destroy": 0.7
      },
      "minecraft:placement_rule": {
        "can_place_on": ["minecraft:solid_block"]
      },
      "minecraft:tags": ["vsas:rails", "rail"]
    }
  }
}
```

### 10.5 Receitas

#### 10.5.1 Receita de Stick
```json
{
  "format_version": "1.21.0",
  "minecraft:recipe_crafting_shaped": {
    "description": {
      "identifier": "vsas:acacia_stick"
    },
    "tags": ["crafting_table", "vsas:sticks"],
    "pattern": [
      ["A"],
      ["A"]
    ],
    "key": {
      "A": {
        "item": "minecraft:acacia_planks"
      }
    },
    "result": {
      "item": "vsas:acacia_stick",
      "count": 4
    }
  }
}
```

#### 10.5.2 Receita de Machado
```json
{
  "format_version": "1.21.0",
  "minecraft:recipe_crafting_shaped": {
    "description": {
      "identifier": "vsas:acacia_wooden_axe"
    },
    "tags": ["crafting_table", "vsas:axes"],
    "pattern": [
      ["AA"],
      ["AB"],
      [" B"]
    ],
    "key": {
      "A": {
        "item": "minecraft:acacia_planks"
      },
      "B": {
        "item": "vsas:acacia_stick"
      }
    },
    "result": {
      "item": "vsas:acacia_wooden_axe",
      "count": 1
    }
  }
}
```

#### 10.5.3 Receita Smithing (Netherite)
```json
{
  "format_version": "1.21.0",
  "minecraft:recipe_smithing": {
    "description": {
      "identifier": "vsas:acacia_diamond_axe_to_netherite"
    },
    "base": {
      "item": "vsas:acacia_diamond_axe"
    },
    "addition": {
      "item": "minecraft:netherite_ingot"
    },
    "result": {
      "item": "vsas:acacia_netherite_axe"
    }
  }
}
```

### 10.6 Loot Tables

#### 10.6.1 Loot de Fogueira
```json
{
  "format_version": "1.21.0",
  "minecraft:loot_table": {
    "description": {
      "identifier": "vsas:blocks/acacia_campfire"
    },
    "pools": [
      {
        "rolls": 1,
        "entries": [
          {
            "type": "minecraft:item",
            "name": "vsas:acacia_campfire",
            "weight": 1,
            "conditions": [
              {
                "condition": "minecraft:block_property",
                "domain": "minecraft:silk_touch",
                "operator": "==",
                "operand": true
              }
            ]
          },
          {
            "type": "minecraft:item",
            "name": "minecraft:charcoal",
            "weight": 1,
            "count": {
              "min": 1,
              "max": 2
            },
            "conditions": [
              {
                "condition": "minecraft:survives_explosion"
              }
            ]
          }
        ]
      }
    ]
  }
}
```

### 10.7 Tags

#### 10.7.1 Tag de Itens (Sticks)
```json
{
  "format_version": "1.21.0",
  "minecraft:tag": {
    "description": {
      "identifier": "vsas:sticks"
    },
    "tags": [
      "vsas:acacia_stick",
      "vsas:bamboo_stick",
      "vsas:birch_stick",
      "vsas:cherry_stick",
      "vsas:crimson_stick",
      "vsas:dark_oak_stick",
      "vsas:jungle_stick",
      "vsas:mangrove_stick",
      "vsas:spruce_stick",
      "vsas:warped_stick"
    ]
  }
}
```

### 10.8 Entidades (Flechas)

```json
{
  "format_version": "1.21.0",
  "minecraft:entity": {
    "description": {
      "identifier": "vsas:acacia_arrow",
      "is_spawnable": false,
      "is_summonable": true,
      "is_experimental": false
    },
    "components": {
      "minecraft:display_name": "Acacia Arrow",
      "minecraft:entity_scale": 1.0,
      "minecraft:projectile": {
        "min_launch_power": 0.1,
        "max_launch_power": 2.5,
        "launch_power_multiplier": 1.0,
        "min_drag": 0.01,
        "max_drag": 0.01,
        "gravity": 0.05,
        "uncertainty_base": 0.0,
        "uncertainty_multiplier": 0.0,
        "shooting_uncertainty": 0.0,
        "inaccuracy": 0.0,
        "power": 2.0,
        "damage": 2.0,
        "destroy_on_hit": true,
        "hit_sound": "bow.hit",
        "launch_sound": "bow.fire"
      },
      "minecraft:collision_box": {
        "width": 0.5,
        "height": 0.5
      }
    },
    "component_groups": {
      "vsas:acacia_arrow": {
        "minecraft:render": {
          "material": "vsas:entity/arrows/acacia_arrow",
          "geometry": "geometry.arrow"
        }
      }
    }
  }
}
```

### 10.9 Villager Trades (Script API)

```javascript
// scripts/server/villager_trades.js
import { world, system } from '@minecraft/server';

// Registrar trades quando o mundo carrega
system.afterEvents.scriptEventReceive.subscribe((event) => {
    if (event.id === 'vsas:register_trades') {
        registerVillagerTrades();
    }
});

function registerVillagerTrades() {
    // Obter todos os villagers
    const villagers = world.getEntities({ type: 'minecraft:villager' });
    
    for (const villager of villagers) {
        // Adicionar trades para ferramentas de madeira
        villager.addTrade({
            buy: { item: 'vsas:oak_stick', count: 16 },
            sell: { item: 'vsas:oak_wooden_axe', count: 1 },
            maxUses: 2,
            rewardExp: true
        });
        
        // Adicionar mais trades conforme necessário
    }
}
```

### 10.10 Modelos 3D (Geometry)

#### 10.10.1 Modelo de Stick
```json
{
  "format_version": "1.12.0",
  "minecraft:geometry": [
    {
      "description": {
        "identifier": "vsas:geometry.stick",
        "texture_width": 16,
        "texture_height": 16,
        "visible_bounds_width": 2,
        "visible_bounds_height": 16,
        "visible_bounds_offset": [0, 0, 0]
      },
      "bones": [
        {
          "name": "stick",
          "pivot": [0, 8, 0],
          "cubes": [
            {
              "origin": [-1, 0, -1],
              "size": [2, 16, 2],
              "uv": [0, 0]
            }
          ]
        }
      ]
    }
  ]
}
```

#### 10.10.2 Modelo de Machado
```json
{
  "format_version": "1.12.0",
  "minecraft:geometry": [
    {
      "description": {
        "identifier": "vsas:geometry.axe",
        "texture_width": 32,
        "texture_height": 32,
        "visible_bounds_width": 4,
        "visible_bounds_height": 4,
        "visible_bounds_offset": [0, 0, 0]
      },
      "bones": [
        {
          "name": "handle",
          "pivot": [0, -8, 0],
          "cubes": [
            {
              "origin": [-1, -16, -1],
              "size": [2, 16, 2],
              "uv": [0, 0]
            }
          ]
        },
        {
          "name": "head",
          "parent": "handle",
          "pivot": [0, -16, 0],
          "cubes": [
            {
              "origin": [-3, -2, -2],
              "size": [6, 2, 4],
              "uv": [0, 16]
            }
          ]
        }
      ]
    }
  ]
}
```

### 10.11 Manifest Files

#### 10.11.1 Behavior Pack Manifest
```json
{
  "format_version": 2,
  "header": {
    "name": "VSAS Behavior Pack",
    "description": "Variant Sticks and Stuff - Behavior Pack",
    "uuid": "XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX",
    "version": [1, 0, 0],
    "min_engine_version": "1.21.0"
  },
  "modules": [
    {
      "description": "VSAS Behavior Module",
      "type": "behavior",
      "uuid": "XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX",
      "version": [1, 0, 0],
      "entry": "packs/vsas_behavior"
    }
  ],
  "dependencies": [],
  "capabilities": [
    "scripts",
    "chemistry"
  ],
  "metadata": {
    "authors": ["Xanthian (Original)", "Enzo Pessoabayma (Bedrock Port)"],
    "license": "MIT",
    "url": "https://github.com/xanthian/vsas"
  }
}
```

#### 10.11.2 Resource Pack Manifest
```json
{
  "format_version": 2,
  "header": {
    "name": "VSAS Resource Pack",
    "description": "Variant Sticks and Stuff - Resource Pack",
    "uuid": "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY",
    "version": [1, 0, 0],
    "min_engine_version": "1.21.0"
  },
  "modules": [
    {
      "description": "VSAS Resource Module",
      "type": "resources",
      "uuid": "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY",
      "version": [1, 0, 0],
      "entry": "packs/vsas_resource"
    }
  ],
  "dependencies": [
    {
      "uuid": "XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX",
      "version": [1, 0, 0]
    }
  ],
  "metadata": {
    "authors": ["Xanthian (Original)", "Enzo Pessoabayma (Bedrock Port)"],
    "license": "MIT",
    "url": "https://github.com/xanthian/vsas"
  }
}
```

---

## 11. PLANO DE IMPLEMENTAÇÃO POR ETAPAS

### 11.1 Fase 1: Preparação (1-2 dias)
- [ ] Verificar versão atual do Minecraft Bedrock e APIs disponíveis
- [ ] Criar estrutura de pastas do Add-On
- [ ] Configurar manifests de Behavior e Resource Packs
- [ ] Criar sistema de versionamento e licença
- [ ] Documentar padrões de nomenclatura de IDs

### 11.2 Fase 2: Itens Básicos (3-5 dias)
- [ ] Implementar todos os Sticks variantes (10 itens)
  - [ ] JSON de itens
  - [ ] Texturas
  - [ ] Modelos
  - [ ] Tags
  - [ ] Receitas normais
  - [ ] Receitas swap
- [ ] Testar funcionamento básico

### 11.3 Fase 3: Ferramentas (5-7 dias)
- [ ] Implementar Machados (90 itens)
- [ ] Implementar Picaretas (90 itens)
- [ ] Implementar Pás (90 itens)
- [ ] Implementar Enxadas (90 itens)
- [ ] Implementar Espadas (90 itens)
  - [ ] JSON de itens com componentes de dano/durabilidade
  - [ ] Texturas
  - [ ] Modelos
  - [ ] Tags por material
  - [ ] Receitas de crafting
  - [ ] Receitas smithing (netherite)
- [ ] Testar balanceamento de ferramentas

### 11.4 Fase 4: Armas (3-4 dias)
- [ ] Implementar Arcos (10 itens)
- [ ] Implementar Bestas (10 itens)
- [ ] Implementar Flechas (10 itens + entidades)
  - [ ] JSON de itens
  - [ ] JSON de entidades
  - [ ] Texturas
  - [ ] Modelos
  - [ ] Tags
  - [ ] Receitas
- [ ] Testar funcionamento de armas

### 11.5 Fase 5: Itens Especiais (2-3 dias)
- [ ] Implementar Escovas (10 itens)
- [ ] Implementar Varas de Pesca (10 itens)
- [ ] Implementar Carrot on a Stick (10 itens)
- [ ] Implementar Warped Fungus on a Stick (10 itens)
  - [ ] JSON de itens
  - [ ] Texturas
  - [ ] Modelos
  - [ ] Tags
  - [ ] Receitas
- [ ] Testar itens especiais

### 11.6 Fase 6: Blocos (5-7 dias)
- [ ] Implementar Fogueiras (20 blocos)
- [ ] Implementar Afiações (10 blocos)
- [ ] Implementar Escadas (10 blocos)
- [ ] Implementar Alavancas (10 blocos)
- [ ] Implementar Trilhos (40 blocos)
- [ ] Implementar Tochas (60 blocos)
  - [ ] JSON de blocos
  - [ ] Blockstates → Permutations
  - [ ] Texturas
  - [ ] Modelos
  - [ ] Tags
  - [ ] Receitas
  - [ ] Loot Tables
- [ ] Testar funcionamento de blocos

### 11.7 Fase 7: Funcionalidades Avançadas (3-5 dias)
- [ ] Implementar Villager Trades (Script API)
- [ ] Implementar Loot Table Modifiers
- [ ] Testar compatibilidade com minecarts
- [ ] Testar interação com redstone
- [ ] Testar funcionamento de fogueiras
- [ ] Testar funcionamento de trilhos

### 11.8 Fase 8: Traduções e Polimento (2-3 dias)
- [ ] Implementar todas as traduções (en_US)
- [ ] Verificar consistência de nomes
- [ ] Validar todos os JSONs
- [ ] Otimizar texturas e modelos
- [ ] Criar ícone do Add-On

### 11.9 Fase 9: Testes Finais (3-5 dias)
- [ ] Testar todas as receitas
- [ ] Testar crafting de todas as ferramentas
- [ ] Testar funcionamento de armas
- [ ] Testar colocação de blocos
- [ ] Testar mineração e drops
- [ ] Testar interação com entidades
- [ ] Testar compatibilidade com outros Add-Ons
- [ ] Corrigir bugs encontrados

### 11.10 Fase 10: Documentação e Entrega (1-2 dias)
- [ ] Criar documentação completa
- [ ] Criar README com instruções
- [ ] Criar CHANGELOG
- [ ] Empacotar Add-On
- [ ] Testar instalação
- [ ] Validar todos os arquivos

---

## 12. ESTIMATIVA DE TEMPO TOTAL

| Fase | Duração Estimada | Complexidade |
|------|------------------|--------------|
| Fase 1: Preparação | 1-2 dias | Baixa |
| Fase 2: Itens Básicos | 3-5 dias | Baixa |
| Fase 3: Ferramentas | 5-7 dias | Média |
| Fase 4: Armas | 3-4 dias | Alta |
| Fase 5: Itens Especiais | 2-3 dias | Baixa |
| Fase 6: Blocos | 5-7 dias | Alta |
| Fase 7: Funcionalidades Avançadas | 3-5 dias | Alta |
| Fase 8: Traduções e Polimento | 2-3 dias | Baixa |
| Fase 9: Testes Finais | 3-5 dias | Média |
| Fase 10: Documentação | 1-2 dias | Baixa |
| **Total** | **26-43 dias** | |

**Estimativa realista**: 4-6 semanas de trabalho contínuo

---

## 13. RECURSOS NECESSÁRIOS

### 13.1 Ferramentas
- [ ] Minecraft Bedrock (versão mais recente)
- [ ] Visual Studio Code ou IDE similar
- [ ] Extensão "Minecraft Bedrock Add-On" para VS Code
- [ ] Ferramenta de validação de JSON
- [ ] Ferramenta de conversão de modelos (Java → Bedrock)
- [ ] Git para versionamento

### 13.2 Conhecimentos Requeridos
- [ ] JSON e estrutura de Add-Ons Bedrock
- [ ] Componentes de itens e blocos
- [ ] Receitas e crafting
- [ ] Modelos 3D (Geometry)
- [ ] Texturas e UV mapping
- [ ] Script API (JavaScript/TypeScript)
- [ ] Tags e loot tables
- [ ] Entidades customizadas

### 13.3 Recursos Externos
- [ ] Documentação oficial do Minecraft Bedrock
- [ ] API Reference (Script API)
- [ ] Exemplos de Add-Ons existentes
- [ ] Comunidade de desenvolvedores Bedrock

---

## 14. RISCOS E DESAFIOS

### 14.1 Riscos Técnicos
1. **Compatibilidade de versões**: Novas versões do Bedrock podem quebrar funcionalidades
2. **Limitações do Script API**: Algumas funcionalidades podem não ser possíveis
3. **Desempenho**: Muitos itens/blocos podem afetar performance
4. **Memória**: Texturas e modelos em grande quantidade
5. **Conflitos de IDs**: Possível conflito com outros Add-Ons

### 14.2 Desafios de Implementação
1. **Conversão de modelos**: Java models → Bedrock geometry
2. **Sistema de tags**: Implementação correta de tags hierárquicas
3. **Villager Trades**: Requer Script API funcional
4. **Flechas customizadas**: Entidades com texturas variantes
5. **Trilhos variantes**: Compatibilidade com minecarts
6. **Fogueiras variantes**: Comportamento de luz e queima

### 14.3 Mitigação de Riscos
1. **Versionamento claro**: Usar versionamento semântico
2. **Testes incrementais**: Testar cada fase antes de prosseguir
3. **Documentação**: Documentar todas as decisões de design
4. **Backup**: Manter backups de todas as versões
5. **Validação**: Validar todos os JSONs antes de testar

---

## 15. RECOMENDAÇÕES FINAIS

### 15.1 Prioridades de Implementação
1. **Itens básicos (Sticks)** - Base para todas as outras receitas
2. **Ferramentas** - Funcionalidade principal do mod
3. **Blocos** - Expande o gameplay
4. **Armas** - Adiciona variedade de combate
5. **Itens especiais** - Funcionalidades únicas
6. **Funcionalidades avançadas** - Polimento final

### 15.2 Decisões de Design
1. **Manter identidade VSAS**: Não simplificar o mod, preservar todas as variantes
2. **Qualidade sobre quantidade**: Implementar corretamente, não rapidamente
3. **Compatibilidade**: Garantir que o Add-On funcione com outros populares
4. **Desempenho**: Otimizar texturas e modelos para bom desempenho
5. **Documentação**: Manter documentação atualizada durante o desenvolvimento

### 15.3 Próximos Passos
1. **Aprovar esta auditoria** - Confirmar que todas as informações estão corretas
2. **Definir escopo final** - Decidir se todas as funcionalidades serão implementadas
3. **Criar timeline** - Definir datas específicas para cada fase
4. **Alocar recursos** - Designar quem será responsável por cada parte
5. **Iniciar implementação** - Começar pela Fase 1

---

## 16. CONCLUSÃO

O VSAS 4.2.6 é um mod complexo e abrangente que adiciona **780+ itens e blocos** ao Minecraft Java, com 10 tipos de madeira e múltiplas variantes de ferramentas, armas, blocos e itens especiais.

A conversão para Bedrock é **VIÁVEL**, mas requer:
- Trabalho significativo de adaptação de JSONs
- Conversão de modelos 3D
- Implementação de Script API para funcionalidades avançadas
- Testes extensivos

**Estimativa**: 4-6 semanas de desenvolvimento dedicado
**Complexidade**: Alta (devido à quantidade de itens e blocos)
**Viabilidade**: 95% (a maioria das funcionalidades pode ser implementada)

**Recomendação**: Proceder com a implementação seguindo o plano de etapas proposto, priorizando a qualidade e a fidelidade ao mod original.

---

*Documento gerado em: 2024*
*Versão: 1.0*
*Autor: Vibe Code (Mistral AI)*
*Auditado por: [Nome do Responsável]*
